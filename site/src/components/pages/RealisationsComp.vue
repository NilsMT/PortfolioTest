<template>
    <div id="realisations">
        <TitreSectionComp titre="Réalisations" />

        <h2 v-if="Object.keys(dico_real_jv).length>0">Jeux-vidéos</h2>

        <div class="real_cont">
            <RealComp v-for="(real, key) in dico_real_jv" :key="key" 
                :imgName="real.imgName" 
                :titre="key" 
                :desc="real.desc" 
                :destination="real.destination"
            />
        </div>

        <h2 v-if="Object.keys(dico_real_web).length>0">Applications web</h2>

        <div class="real_cont">
            <RealComp v-for="(real, key) in dico_real_web" :key="key" 
                :imgName="real.imgName" 
                :titre="key" 
                :desc="real.desc" 
                :destination="real.destination"
            />
        </div>

        <h2 v-if="Object.keys(dico_real_other).length>0">Autres Réalisations</h2>

        <div class="real_cont">
            <RealComp v-for="(real, key) in dico_real_other" :key="key" 
                :imgName="real.imgName" 
                :titre="key" 
                :desc="real.desc" 
                :destination="real.destination"
            />
        </div>
    </div>
</template>

<style scoped>
.real_cont {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: var(--gap);
}

#final_real_cont {
    padding-top: var(--padding);
    margin-top: calc(var(--padding) * 2);
    border-top: solid 1px var(--text);
}
</style>

<script>
import TitreSectionComp from '../TitreSectionComp.vue'
import RealComp from '../RealComp.vue'
import { ref } from 'vue'

const dico_real_web = ref({})

const dico_real_jv = ref({})

const dico_real_other = ref({})

const dico_real_final = ref({})

dico_real_jv.value = {
    "Just Flick It !": {
        "imgName": "flickit.png",
        "desc": "4<sup>ème</sup> jeu vidéo réalisé seul sur Unity.<br> en développement.",
        "destination": "/JustFlickIt"
    },
    "A.I.P.R": {
        "imgName": "aipr.png",
        "desc": "3<sup>ème</sup> jeu vidéo réalisé seul sur Roblox.<br> en seulement trois jours.",
        "destination": "/AIPR"
    },
    "A.R.C.H": {
        "imgName": "arch.png",
        "desc": "2<sup>ème</sup> jeu vidéo réalisé seul sur Roblox.<br> en développement.",
        "destination": "/ARCH"
    },
    "Z.R.C": {
        "imgName": "zrc.png",
        "desc": "1<sup>er</sup> jeu vidéo réalisé sur Roblox avec 2 personnes.<br>Développement terminé en 2024.",
        "destination": "/ZRC"
    },
    "Pastek": {
        "imgName": "pastek.png",
        "desc": "Jeu Scratch réalisé au collège puis republié en mars 2023.",
        "destination": "/Pastek"
    },
}

dico_real_web.value = {
    "La Chasse Au Trésor": {
        "imgName": "chasseautresor.png",
        "desc": "Site réalisé pour une animation de chasse au trésor.",
        "destination": "/ChasseAuTresor"
    },
    "EclExt": {
        "imgName": "eclext.png",
        "desc": "Outil de standardisation de données.<br> réalisé pendant mon stage de 2<sup>ème</sup> année de BUT.",
        "destination": "/EclExt"
    },
    "NewsRadar": {
        "imgName": "newsradar.png",
        "desc": "Site de recherche géalocalisée d'articles de presse .<br> Projet de fin de 2<sup>ème</sup> année de BUT.",
        "destination": "/NewsRadar"
    },
    "Antoine Factory": {
        "imgName": "antoinefactory.png",
        "desc": "Site d'e-shopping pour un client réel.<br> Projet de début de 2<sup>ème</sup> année de BUT.",
        "destination": "/AntoineFactory"
    },
    "RGB Stuffs": {
        "imgName": "rgb.png",
        "desc": "Site qui regroupe des outils concernants les couleurs.",
        "destination": "/RGBStuffs"
    },
    "ATLAS": {
        "imgName": "atlas.png",
        "desc": "Site ayant pour thème l'espace.<br> Projet d'une matière en de 1<sup>ère</sup> année de BUT.",
        "destination": "/ATLAS"
    },
    "Anime List": {
        "imgName": "animelist.png",
        "desc": "Liste d'anime réalisée en no-code en utilisant le site softr.",
        "destination": "/AnimeList"
    },
    "Portfolio": {
        "imgName": "portoflio.png",
        "desc": "Eh oui ! Ce portfolio est réalisé des mes propres main pour qu'il me corresponde à 100%.",
        "destination": ""
    }
}

dico_real_other.value = {
    
}

export default {
    name: 'RealisationsComp',
    components: {
        TitreSectionComp,
        RealComp
    },
    setup() {
        return { 
            dico_real_jv,
            dico_real_web,
            dico_real_other,
            dico_real_final
        }
    }
}
</script>
