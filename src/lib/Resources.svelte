<script>
    import List, { Item, Graphic, Separator, Text } from '@smui/list';
import { dynasty } from './utils/helper';

    const today = new Date();
    const resources = [
        {
            name: "KeepTradeCut Dynasty Football Trade Calculator",
            url: "https://keeptradecut.com/trade-calculator",
            icon: "assessment",
            separator: true,
            dynastyOnly: true,
        },
        {
            name: "FantasyPros Superflex PPR Dynasty Rankings",
            url: "https://www.fantasypros.com/nfl/rankings/dynasty-superflex",
            icon: "insights",
            premium: false,
            separator: true,
            dynastyOnly: false,
        },
        {
            name: "FantasyPros Dynasty Trade Value Chart",
            url: "https://www.fantasypros.com/2023/9/fantasy-football-rankings-dynasty-trade-value-chart-september-2023-update/",
            icon: "assessment",
            premium: false,
            separator: true,
            dynastyOnly: true,
        },
        {
            name: "Reddit - Dynasty Fantasy Football",
            url: "https://www.reddit.com/r/DynastyFF/",
            icon: "article",
            premium: false,
            separator: true,
            dynastyOnly: true,
        },
        {
            name: "Reddit - Fantasy Football Advice",
            url: "https://www.reddit.com/r/fantasyfootballadvice/",
            icon: "article",
            premium: false,
            separator: true,
            redraftOnly: true,
        },
        {
            name: "Sleeper Dynasty Rankings Comparison",
            url: "https://www.dynastysuperflex.com/",
            icon: "insights",
            premium: false,
            separator: true,
            dynastyOnly: true,
        },
        {
            name: "Dynasty Fantasy Rankings and Trade Calculator",
            url: "https://www.fantasycalc.com/dynasty-rankings/",
            icon: "insights",
            premium: false,
            separator: true,
            dynastyOnly: true,
        },
        {
            name: "KeepTradeCut Development (College) Player Rankings",
            url: "https://keeptradecut.com/devy-rankings",
            icon: "assessment",
            premium: false,
            separator: true,
            dynastyOnly: true,
        },
    ];
</script>

<style>
    .pageBody {
        position: relative;
        z-index: 1;
    }

    :global(.list) {
        width: 90%;
        max-width: 800px;
        border: 1px solid
        var(--mdc-theme-text-hint-on-background, var(--d7d7d7));
        margin: 15px auto;
        padding: 0 !important;
        box-shadow: 0px 3px 3px -2px var(--boxShadowOne), 0px 3px 4px 0px var(--boxShadowTwo), 0px 1px 8px 0px var(--boxShadowThree);
    }


    :global(.linkText) {
        font-size: 1.1em;
    }

    a {
        color: var(--g555);
        font-size: 1.1em;
        text-decoration: none;
    }

    h4 {
        text-align: center;
    }

    .disclaimer {
        color: #888;
        text-align: center;
    }
</style>

<div class="pageBody">
    <div class="banner">
        <h4>Dynasty References and Resources</h4>
    </div>

    <List class="list" dense>
        {#each resources as resource}
            {#if resource.dynastyOnly && dynasty}
                <a target="_blank" href="{resource.url}">
                    <Item>
                        {#if resource.icon}
                            <Graphic class="material-icons">{resource.icon}</Graphic>
                        {/if}
                        <Text class="linkText">{resource.name}{resource.premium ? "*" : ""}</Text>
                    </Item>
                    {#if resource.separator}
                        <Separator />
                    {/if}
                </a>
            {:else if resource.redraftOnly && !dynasty}
                <a target="_blank" href="{resource.url}">
                    <Item>
                        {#if resource.icon}
                            <Graphic class="material-icons">{resource.icon}</Graphic>
                        {/if}
                        <Text class="linkText">{resource.name}{resource.premium ? "*" : ""}</Text>
                    </Item>
                    {#if resource.separator}
                        <Separator />
                    {/if}
                </a>
            {:else if !resource.redraftOnly && !resource.dynastyOnly}
                <a target="_blank" href="{resource.url}">
                    <Item>
                        {#if resource.icon}
                            <Graphic class="material-icons">{resource.icon}</Graphic>
                        {/if}
                        <Text class="linkText">{resource.name}{resource.premium ? "*" : ""}</Text>
                    </Item>
                    {#if resource.separator}
                        <Separator />
                    {/if}
                </a>
            {/if}
        {/each}
    </List>
    <p class="disclaimer">*There are plenty of resources, these are just a few suggestions.</p>
</div>
