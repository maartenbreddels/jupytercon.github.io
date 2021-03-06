<template>
    <div>
        <BlockHeaderPlain title="Our Sponsors">
            <template  v-slot:side-content>
            </template>
        </BlockHeaderPlain>
        <div class="main">
            <h1 id="Sponsoring">Sponsoring</h1>
            <p>
                JupyterCon provides many unique opportunities for sponsors. On the one hand, the conference
                is certainly the best in-person event in the world in which to engage the community that sustains
                and evolves Project Jupyter. Join us and become a participant in that dialogue. One the other
                hand, the conference provides access to a breadth of communities that leverage Project
                Jupyter:
                <ul>
                    <li>as standard tooling for research worldwide</li>
                    <li>widespread use cases throughout education</li>
                    <li>emerging use cases for interactive content in publishing</li>
                    <li>integration points for enterprise data infrastructure, and enterprise concerns:
                        collaboration, compliance, privacy, security, reproducibility, and so on</li>
                    <li>a place to reach practitioners, such as in data science</li>
                </ul>
                JupyterCon as a forum is pro-active on many important shared goals. To paraphrase from the
                <a href="https://sustainabledevelopment.un.org/?menu=1300">UN 2030 Agenda for Sustainable Development</a>,
                which many organizations have begun to adopt,
                Jupyter plays a growing role in resilient infrastructure (“Build resilient infrastructure, promote
                inclusive and sustainable industrialization and foster innovation”) and in education (“Ensure
                inclusive and equitable quality education and promote lifelong learning opportunities for all”).
                Moreover, the conference is committed to promoting exemplary practices for diversity and
                inclusion, gender equality, as well as innovating on sustainability practices in conferences. We
                welcome sponsors who can help our community support and demonstrate these practices
                through the event.
            </p>
            <p>
                If you are interested in sponsoring JupyterCon, email us at <a href="">jupytercon-sponsor@numfocus.org</a>
                to receive a prospectus.
            </p>
            <h1 id="Sponsors" class="sponsors-title">Sponsors</h1>
            <div class="grid-container sponsors">
                <div class="grid-y">
                    <div class="cell sponsor-row" v-for="sponsor in sponsors">
                        <div class="grid-x">
                            <div class="cell small-4"><img class="sponsor-image" :src="sponsor.image"></div>
                            <div class="cell auto sponsor-text-plain">
                                <p>
                                    <a :href=sponsor.link>{{ sponsor.link }}</a>
                                </p>
                                <p>
                                    {{ sponsor.description }}
                                </p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <h1 id="Community Sponsors" class="sponsors-title">Community Sponsors</h1>
            <div class="grid-container sponsors">
                <div class="grid-y">
                    <div class="cell sponsor-row" v-for="sponsor in community_sponsors">
                        <div class="grid-x">
                            <div class="cell small-4"><img class="sponsor-image" :src="sponsor.image"></div>
                            <div class="cell auto sponsor-text-plain">
                                <p>
                                    <a :href=sponsor.link>{{ sponsor.link }}</a>
                                </p>
                                <p>
                                    {{ sponsor.description }}
                                </p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <DesktopFooter />
    </div>
</template>

<script>
    import BlockHeaderPlain from "../components/BlockHeaderPlain";
    import DesktopFooter from "../components/DesktopFooter";

    export default {
        name: "proposals",
        components: {DesktopFooter, BlockHeaderPlain},
        data() {
            return {
                sponsors: [
                    {
                        link: "https://numfocus.org/",
                        description: "The mission of NumFOCUS is to promote open practices in research, data, and scientific computing by serving as a fiscal sponsor for open source projects and organizing community-driven educational programs.",
                        image: require("~/assets/images/sponsors/NumFocus.png")
                    }
                ],
                community_sponsors: [
                    {
                        link: "https://womeninanalytics.com",
                        description: "Women in Analytics is a global organization that brings together an international community of industry leaders, technical experts, entrepreneurs, and academia. Our mission is to provide visibility to the women making an impact in the analytics space and furnish a platform for them to lead the conversation around the advancements of analytical research, development, and application. WIA aims to be an extremely inclusive organization and welcomes participation from all genders.",
                        image: require("~/assets/images/sponsors/WIA-Secondary-RGB.png")
                    },
                    {
                        link: "https://berlin.pydata.org/",
                        description: "PyData is an educational program of NumFOCUS. We provide a forum for the international community of users and developers of data analysis tools to share ideas and learn from each other. The global PyData network promotes discussion of best practices, new approaches, and emerging technologies for data management, processing, analytics, and visualization.",
                        image: require("~/assets/images/sponsors/pydata.png")
                    },
                    {
                        link: "https://www.meetup.com/Python-Users-Berlin-PUB",
                        description: "Python Users Berlin is the oldest Python community in Berlin. We host monthly events with presentations and discussions about Python and Python-related software development.",
                        image: require("~/assets/images/sponsors/pub.jpeg")
                    },
                    {
                        link: "https://www.womenwhocode.com",
                        description: "Women Who Code is the largest and most active community of engineers dedicated to inspiring women to excel in technology careers. We provide an avenue into tech, empower women with skills needed for professional advancement, and provide environments where networking and mentorship are valued.",
                        image: require("~/assets/images/sponsors/wwcode_Final Logo.svg")
                    },
                ]
            }
        },
    }
</script>

<style scoped lang="scss">
    @import 'assets/scss/settings';
    .menubar {
        position: relative;
        z-index: 1;
    }
    h1 {
        font-size: 36px;
    }
    h2 {
        font-size: 24px;
    }
    h1, h2 {
        color: $figma-orange;
    }
    .main {
        background-color: $figma-grey3;
        padding: 100px;
    }
    .sponsors-title {
        margin-top: 60px;
        margin-bottom: 30px;
    }
    .sponsors {
        background-color: white;
    }
    .sponsor-row {
        margin-top: 10px;
        margin-bottom: 10px;
    }
    .sponsor-image {
        margin: 10%;
        width: 80%;
    }
    .sponsor-text-plain {
        margin: 30px;
    }
</style>
