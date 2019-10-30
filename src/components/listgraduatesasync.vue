<template>
    <div>
        <h1>{{ caption }}</h1>
        <v-card v-if="errored">
            <v-card-title>We are sorry for the inconvenience.</v-card-title>
            <v-card-text>{{graduates}}</v-card-text>
        </v-card>
        <section>
<!--            <section v-if="loading"><p>loading...</p></section>-->
            <section>
                <v-container fluid>
                    <v-row>
                        <v-col>
                            <v-text-field label="Search or filter graduates by name" v-model="search" />
                        </v-col>
                    </v-row>
                    <v-row>
                        <v-col>
                            <v-switch v-model="withAbstract" class="mx-2" label="Have abstract" />
                            <!--
                             <input type="checkbox" name="withAbstract" v-on:click="withAbstract = !withAbstract" /><label for="withAbstract"> Have abstract</label>
                            -->
                        </v-col>
                        <v-col>
                            <v-switch v-model="withStory" class="mx-2" label="Have biography" />
                            <!--
                             <input type="checkbox" name="withStory" v-on:click="withStory = !withStory" /><label for="withStory"> Have story</label>
                            -->
                        </v-col>
                        <v-col>
                            <v-switch v-model="withPhoto" class="mx-2" label="Have photo" />
                            <!--
                             <input type="checkbox" name="withPhoto" v-on:click="withPhoto = !withPhoto" /><label for="withPhoto"> Have photo</label>
                            -->
                        </v-col>
                    </v-row>
                </v-container>
<!--                <v-card v-bind:key="graduate.id" v-for="graduate in filteredGraduates" class="wholecard" outlined>-->
<!--                    <v-card-title style="word-break: break-word;">-->
<!--                        <span hidden>{{graduate.id}}</span>-->
<!--                        <span hidden>[{{ graduate.tag }}]</span>-->
<!--                        {{ graduate.fullName }}{{ graduate.graduatingYear|graduationYear }}-->
<!--                        <graduateachievementasync v-if="graduate.haveAchievement" :graduateName="graduate.fullName" :graduateId="graduate.id" :haveAchievement="graduate.haveAchievement"></graduateachievementasync>-->
<!--                    </v-card-title>-->
<!--                    <v-card-subtitle v-if="graduate.otherSurname != null">{{ graduate.otherSurname|nee }}</v-card-subtitle>-->
<!--                    <v-card-text v-if="graduate.haveStory"><graduatestoryasync :graduateName="graduate.fullName" :graduateId="graduate.id" :haveStory="graduate.haveStory"></graduatestoryasync></v-card-text>-->
<!--                </v-card>-->
            </section>
        </section>
    </div>
</template>

<script>
    // import axios from 'axios';
    // import graduatestoryasync from './graduatestoryasync.vue';
    // import graduateachievementasync from './graduateachievementasync.vue';
    export default {
        name: 'listgraduatesasync',
        props: {
            caption: String
        },
        data: function () {
            return {
                search: '',
                withStory: false,
                withAbstract: false,
                withPhoto: false,
                graduates: null,
                loading: true,
                errored: false
            }
        },
        /*
         await axios.get('http://localhost:7071/api/listGraduates')
         */
        // mounted: async function () {
        //     await axios.get('https://emwonz.azurewebsites.net/api/listGraduates')
        //         .then(response => this.graduates = response.data)
        //         .catch(error => {
        //             this.graduates = "[list]:" + error;
        //             this.errored = true;
        //         })
        //         .finally(() => this.loading = false)
        // },
        // computed: {
        //     filteredGraduates() {
        //         var temp = null;
        //         if (this.withStory && this.withAbstract && this.withPhoto)
        //             temp = this.graduates.filter(grad => { return (grad.haveStory) || (grad.haveAchievement) || (grad.havePhoto) });
        //         else if (this.withStory && this.withAbstract)
        //             temp = this.graduates.filter(grad => { return (grad.haveStory) || (grad.haveAchievement) });
        //         else if (this.withStory && this.withPhoto)
        //             temp = this.graduates.filter(grad => { return (grad.haveStory) || (grad.havePhoto) });
        //         else if (this.withAbstract && this.withPhoto)
        //             temp = this.graduates.filter(grad => { return (grad.haveAchievement) || (grad.havePhoto) });
        //         else if (this.withStory)
        //             temp = this.graduates.filter(grad => { return (grad.haveStory) })
        //         else if (this.withAbstract)
        //             temp = this.graduates.filter(grad => { return (grad.haveAchievement) });
        //         else if (this.withPhoto)
        //             temp = this.graduates.filter(grad => { return (grad.havePhoto) });
        //         else
        //             temp = this.graduates;
        //
        //         return temp.filter(grad => {
        //             return grad.fullName.toLowerCase().includes(this.search.toLowerCase()) || grad.otherSurname.toLowerCase().includes(this.search.toLowerCase()) || grad.graduatingYear.toString().toLowerCase().includes(this.search.toLowerCase())
        //         });
        //     }
        // },
        // filters: {
        //     nee: function (value) {
        //         if (value) {
        //             var names = value.split(";");
        //             var caption = "other known surname";
        //             if (names.length > 1)
        //                 caption += "s";
        //             var last = names.pop();
        //
        //             return caption + ": " + names.join(", ") + ((names.length > 0) ? " and " : "") + last;
        //         }
        //         else {
        //             return '';
        //         }
        //     },
        //     stars: function (value) {
        //         return (!value) ? '' : "**"
        //     },
        //     graduationYear: function (value) {
        //         return (!value) ? '' : " graduated in " + value
        //     }
        // },
        // components: {
        //     graduatestoryasync,
        //     graduateachievementasync
        // }
    }
</script>

<style scoped>
</style>