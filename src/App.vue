<template>
  <div id="app">
    <Header />
    <Main />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data: {
    "page": 1,
    "results": [
      {
        "adult": false,
        "backdrop_path": "/yizL4cEKsVvl17Wc1mGEIrQtM2F.jpg",
        "genre_ids": [
            28,
            878
        ],
        "id": 588228,
        "original_language": "en",
        "original_title": "The Tomorrow War",
        "overview": "The world is stunned when a group of time travelers arrive from the year 2051 to deliver an urgent message: Thirty years in the future, mankind is losing a global war against a deadly alien species. The only hope for survival is for soldiers and civilians from the present to be transported to the future and join the fight. Among those recruited is high school teacher and family man Dan Forester. Determined to save the world for his young daughter, Dan teams up with a brilliant scientist and his estranged father in a desperate quest to rewrite the fate of the planet.",
        "popularity": 4299.876,
        "poster_path": "/34nDCQZwaEvsy4CFO5hkGRFDCVU.jpg",
        "release_date": "2021-06-30",
        "title": "The Tomorrow War",
        "video": false,
        "vote_average": 8.3,
        "vote_count": 2405
      },
      {
        "adult": false,
        "backdrop_path": "/lmZFxXgJE3vgrciwuDib0N8CfQo.jpg",
        "genre_ids": [
            12,
            28,
            878
        ],
        "id": 299536,
        "original_language": "en",
        "original_title": "Avengers: Infinity War",
        "overview": "As the Avengers and their allies have continued to protect the world from threats too large for any one hero to handle, a new danger has emerged from the cosmic shadows: Thanos. A despot of intergalactic infamy, his goal is to collect all six Infinity Stones, artifacts of unimaginable power, and use them to inflict his twisted will on all of reality. Everything the Avengers have fought for has led up to this moment - the fate of Earth and existence itself has never been more uncertain.",
        "popularity": 337.939,
        "poster_path": "/7WsyChQLEftFiDOVTGkv3hFpyyt.jpg",
        "release_date": "2018-04-25",
        "title": "Avengers: Infinity War",
        "video": false,
        "vote_average": 8.3,
        "vote_count": 22191
      },
      {
        "adult": false,
        "backdrop_path": "/8LHSDyRizQ4kQz5rEHPKyXPvMG3.jpg",
        "genre_ids": [
            16,
            10752,
            878
        ],
        "id": 736069,
        "original_language": "en",
        "original_title": "Justice Society: World War II",
        "overview": "When the Flash finds himself dropped into the middle of World War II, he joins forces with Wonder Woman and her top-secret team known as the Justice Society of America.",
        "popularity": 276.46,
        "poster_path": "/e4REOC6CZW8J6FslA4nRvdQXFXR.jpg",
        "release_date": "2021-04-27",
        "title": "Justice Society: World War II",
        "video": false,
        "vote_average": 7.8,
        "vote_count": 273
      },
      {
        "adult": false,
        "backdrop_path": "/ebaQIQ0Uj60Rb9qcXaz0wF5B77I.jpg",
        "genre_ids": [
            36,
            14,
            18
        ],
        "id": 584044,
        "original_language": "en",
        "original_title": "The Viking War",
        "overview": "Ingrid and her siblings are on the run from the Beserkers who have begun invading the villages, taking over, savagely using the residents on a game where they vs a Beserker, and if they win, they get to survive - only, no one ever wins. The siblings are trying to escape the Beserkers after they violently murdered and took over their town. However, the Beserkers are on their trail, and want to put them in the game.",
        "popularity": 101.923,
        "poster_path": "/7BEY3dAb6ZVHzND1Ewmw2PTAl76.jpg",
        "release_date": "2019-10-15",
        "title": "The Viking War",
        "video": false,
        "vote_average": 5.4,
        "vote_count": 24
      },
      {
        "adult": false,
        "backdrop_path": "/kvRT3GwcnqGHzPjXIVrVPhUix7Z.jpg",
        "genre_ids": [
            12,
            28,
            878
        ],
        "id": 271110,
        "original_language": "en",
        "original_title": "Captain America: Civil War",
        "overview": "Following the events of Age of Ultron, the collective governments of the world pass an act designed to regulate all superhuman activity. This polarizes opinion amongst the Avengers, causing two factions to side with Iron Man or Captain America, which causes an epic battle between former allies.",
        "popularity": 111.776,
        "poster_path": "/rAGiXaUfPzY7CDEyNKUofk3Kw2e.jpg",
        "release_date": "2016-04-27",
        "title": "Captain America: Civil War",
        "video": false,
        "vote_average": 7.4,
        "vote_count": 18289
      },
      {
        "adult": false,
        "backdrop_path": "/upsk7nfUjf8ZSYuokwa5U5YXERm.jpg",
        "genre_ids": [
            28,
            18,
            27,
            878,
            53
        ],
        "id": 72190,
        "original_language": "en",
        "original_title": "World War Z",
        "overview": "Life for former United Nations investigator Gerry Lane and his family seems content. Suddenly, the world is plagued by a mysterious infection turning whole human populations into rampaging mindless zombies. After barely escaping the chaos, Lane is persuaded to go on a mission to investigate this disease. What follows is a perilous trek around the world where Lane must brave horrific dangers and long odds to find answers before human civilization falls.",
        "popularity": 61.529,
        "poster_path": "/1SWBSYJsnyhdNRfLI1T6RsCxAQ4.jpg",
        "release_date": "2013-06-20",
        "title": "World War Z",
        "video": false,
        "vote_average": 6.8,
        "vote_count": 12146
      },
      {
        "adult": false,
        "backdrop_path": "/dTFJlBGWSqW6rMiawQidMPxleTd.jpg",
        "genre_ids": [
            35,
            80,
            18
        ],
        "id": 308266,
        "original_language": "en",
        "original_title": "War Dogs",
        "overview": "Based on the true story of two young men, David Packouz and Efraim Diveroli, who won a $300 million contract from the Pentagon to arm America's allies in Afghanistan.",
        "popularity": 30.437,
        "poster_path": "/mDcPRjZC1bb6LavFU3gwsWdVfCM.jpg",
        "release_date": "2016-08-17",
        "title": "War Dogs",
        "video": false,
        "vote_average": 6.9,
        "vote_count": 3481
      },
      {
        "adult": false,
        "backdrop_path": "/oCCvZEbqCCcALQtah8HJm9Ja4HT.jpg",
        "genre_ids": [
            18,
            10749
        ],
        "id": 323272,
        "original_language": "en",
        "original_title": "War Room",
        "overview": "The family-friendly movie explores the transformational role prayer plays in the lives of the Jordan family. Tony and Elizabeth Jordan, a middle-class couple who seemingly have it all – great jobs, a beautiful daughter, their dream home. But appearances can be deceiving. In reality, the Jordan’s marriage has become a war zone and their daughter is collateral damage. With the help of Miss Clara, an older, wiser woman, Elizabeth discovers she can start fighting for her family instead of against them. Through a newly energized faith, Elizabeth and Tony’s real enemy doesn’t have a prayer.",
        "popularity": 28.247,
        "poster_path": "/unxQeVUi5DH01r7ZNvAHwpvX7UK.jpg",
        "release_date": "2015-08-28",
        "title": "War Room",
        "video": false,
        "vote_average": 7.9,
        "vote_count": 298
      },
      {
        "adult": false,
        "backdrop_path": "/3oyA4yN1xv4bwc5bGTfBJAqQDNy.jpg",
        "genre_ids": [
            10752,
            18
        ],
        "id": 475132,
        "original_language": "en",
        "original_title": "A Private War",
        "overview": "One of the most celebrated war correspondents of our time, Marie Colvin is an utterly fearless and rebellious spirit, driven to the frontlines of conflicts across the globe to give voice to the voiceless.",
        "popularity": 43.042,
        "poster_path": "/pAh6uDR9bBznybiJCVYZNJmjg63.jpg",
        "release_date": "2018-11-16",
        "title": "A Private War",
        "video": false,
        "vote_average": 6.8,
        "vote_count": 351
      },
      {
        "adult": false,
        "backdrop_path": "/v7irtTi2wGS7bgzZimwkDHEOIbY.jpg",
        "genre_ids": [
            28,
            12,
            18
        ],
        "id": 290595,
        "original_language": "en",
        "original_title": "The Huntsman: Winter's War",
        "overview": "As two evil sisters prepare to conquer the land, two renegades—Eric the Huntsman, who aided Snow White in defeating Ravenna in Snowwhite and the Huntsman, and his forbidden lover, Sara—set out to stop them.",
        "popularity": 30.691,
        "poster_path": "/ci1QXfBSUBVpLuzxi9A208uwUVi.jpg",
        "release_date": "2016-04-06",
        "title": "The Huntsman: Winter's War",
        "video": false,
        "vote_average": 6.3,
        "vote_count": 3937
      },
      {
        "adult": false,
        "backdrop_path": "/z5LhR3cqKIL0atMcNd16s4IP2kQ.jpg",
        "genre_ids": [
            80,
            18,
            53
        ],
        "id": 1830,
        "original_language": "en",
        "original_title": "Lord of War",
        "overview": "Yuri Orlov is a globetrotting arms dealer and, through some of the deadliest war zones, he struggles to stay one step ahead of a relentless Interpol agent, his business rivals and even some of his customers who include many of the world's most notorious dictators. Finally, he must also face his own conscience.",
        "popularity": 27.244,
        "poster_path": "/xEdwdFZRwrNAvTDx0fAV3MAInaA.jpg",
        "release_date": "2005-09-16",
        "title": "Lord of War",
        "video": false,
        "vote_average": 7.3,
        "vote_count": 3333
      },
      {
        "adult": false,
        "backdrop_path": "/64YOcrslrijllDRCpQvXkSKvXQV.jpg",
        "genre_ids": [
            18,
            10752,
            28
        ],
        "id": 57212,
        "original_language": "en",
        "original_title": "War Horse",
        "overview": "Follows a young man named Albert and his horse, Joey, and how their bond is broken when Joey is sold to the cavalry and sent to the trenches of World War One. Despite being too young to enlist, Albert heads to France to save his friend.",
        "popularity": 19.87,
        "poster_path": "/7KHz6JlJhrFAPesmUkgdnLrSr8Y.jpg",
        "release_date": "2011-12-25",
        "title": "War Horse",
        "video": false,
        "vote_average": 7.3,
        "vote_count": 2619
      },
      {
        "adult": false,
        "backdrop_path": "/1kBFmH1QdduqwyU5nhw8mH6sF7y.jpg",
        "genre_ids": [
            16,
            28
        ],
        "id": 217993,
        "original_language": "en",
        "original_title": "Justice League: War",
        "overview": "The world is under attack by an alien armada led by the powerful Apokoliptian, Darkseid. A group of superheroes consisting of Superman, Batman, Wonder Woman, The Flash, Green Lantern, Cyborg, and Shazam must set aside their differences and gather together to defend Earth.",
        "popularity": 26.381,
        "poster_path": "/eu6zEhpt9QVgZk8T4FJCwKCbJkq.jpg",
        "release_date": "2014-02-02",
        "title": "Justice League: War",
        "video": false,
        "vote_average": 7.5,
        "vote_count": 738
      },
      {
        "adult": false,
        "backdrop_path": "/n7vA2SiG8YQGOZt2WYzgNdHsfC3.jpg",
        "genre_ids": [
            28,
            53
        ],
        "id": 10431,
        "original_language": "en",
        "original_title": "War",
        "overview": "FBI agent Jack Crawford is out for revenge when his partner is killed and all clues point to the mysterious assassin Rogue. But when Rogue turns up years later to take care of some unfinished business, he triggers a violent clash of rival gangs. Will the truth come out before it's too late? And when the dust settles, who will remain standing?",
        "popularity": 12.604,
        "poster_path": "/pBwU58L6qR4dwbFSJSWXIeDGePp.jpg",
        "release_date": "2007-08-24",
        "title": "War",
        "video": false,
        "vote_average": 6.3,
        "vote_count": 1176
      },
      {
        "adult": false,
        "backdrop_path": "/8LI4OEQGY2DIBTQQeRjYVKfL9Dl.jpg",
        "genre_ids": [
            27,
            53,
            10752,
            14
        ],
        "id": 608195,
        "original_language": "en",
        "original_title": "Ghosts of War",
        "overview": "A group of World War II American soldiers encounter a supernatural enemy as they occupy a French castle previously under Nazi control.",
        "popularity": 24.845,
        "poster_path": "/jBeL6pPUPo0wnyTmiuxPegcibPf.jpg",
        "release_date": "2020-07-03",
        "title": "Ghosts of War",
        "video": false,
        "vote_average": 6,
        "vote_count": 229
      },
      {
        "adult": false,
        "backdrop_path": "/vwCc9PP6xkSjnYsSl9lzTABhexe.jpg",
        "genre_ids": [
            12,
            53,
            878
        ],
        "id": 74,
        "original_language": "en",
        "original_title": "War of the Worlds",
        "overview": "Ray Ferrier is a divorced dockworker and less-than-perfect father. Soon after his ex-wife and her new husband drop off his teenage son and young daughter for a rare weekend visit, a strange and powerful lightning storm touches down.",
        "popularity": 33.984,
        "poster_path": "/6Biy7R9LfumYshur3YKhpj56MpB.jpg",
        "release_date": "2005-06-28",
        "title": "War of the Worlds",
        "video": false,
        "vote_average": 6.5,
        "vote_count": 6305
      },
      {
        "adult": false,
        "backdrop_path": "/sQkRiQo3nLrQYMXZodDjNUJKHZV.jpg",
        "genre_ids": [
            16,
            28,
            12,
            14,
            878
        ],
        "id": 618344,
        "original_language": "en",
        "original_title": "Justice League Dark: Apokolips War",
        "overview": "Earth is decimated after intergalactic tyrant Darkseid has devastated the Justice League in a poorly executed war by the DC Super Heroes. Now the remaining bastions of good – the Justice League, Teen Titans, Suicide Squad and assorted others – must regroup, strategize and take the war to Darkseid in order to save the planet and its surviving inhabitants.",
        "popularity": 41.609,
        "poster_path": "/c01Y4suApJ1Wic2xLmaq1QYcfoZ.jpg",
        "release_date": "2020-05-05",
        "title": "Justice League Dark: Apokolips War",
        "video": false,
        "vote_average": 8.4,
        "vote_count": 1003
      },
      {
        "adult": false,
        "backdrop_path": "/z9BwMdHqKhVhRi2s5BcihGiqWWZ.jpg",
        "genre_ids": [
            18,
            10752
        ],
        "id": 10592,
        "original_language": "en",
        "original_title": "Hart's War",
        "overview": "Fourth-generation Army Col. William McNamara is imprisoned in a brutal German POW camp. Still, as the senior-ranking American officer, he commands his fellow inmates, keeping a sense of honor alive in a place where honor is easy to destroy, all under the dangerous eye of the Luftwafe vetran Col. Wilhelm Visser. Never giving up the fight to win the war, McNamara is silently planning, waiting for his moment to strike back at the enemy. A murder in the camp gives him the chance to set a risky plan in motion. With a court martial to keep Visser and the Germans distracted, McNamara orchestrates a cunning scheme to escape and destroy a nearby munitions plant, enlisting the unwitting help of young Lt. Tommy Hart. Together with his men, McNamara uses a hero's resolve to carry out his mission, ultimately forced to weigh the value of his life against the good of his country.",
        "popularity": 10.081,
        "poster_path": "/yRUhSU7vzs5ePa72LNPcKKCCMZ5.jpg",
        "release_date": "2002-02-15",
        "title": "Hart's War",
        "video": false,
        "vote_average": 6.3,
        "vote_count": 670
      },
      {
        "adult": false,
        "backdrop_path": "/zmnSIyqMB9jG0QqTDJbJxUDgROt.jpg",
        "genre_ids": [
            28,
            80
        ],
        "id": 13056,
        "original_language": "en",
        "original_title": "Punisher: War Zone",
        "overview": "Waging his one-man war on the world of organized crime, ruthless vigilante-hero Frank Castle sets his sights on overeager mob boss Billy Russoti. After Russoti is left horribly disfigured by Castle, he sets out for vengeance under his new alias: Jigsaw. With the \"Punisher Task Force\" hot on his trail and the FBI unable to take Jigsaw in, Frank must stand up to the formidable army that Jigsaw has recruited before more of his evil deeds go unpunished.",
        "popularity": 18.602,
        "poster_path": "/oOvKJgYUIpfswGHAdW6159bPbvM.jpg",
        "release_date": "2008-12-05",
        "title": "Punisher: War Zone",
        "video": false,
        "vote_average": 5.7,
        "vote_count": 777
      },
      {
        "adult": false,
        "backdrop_path": "/a9jZrU7LJk6mAUjmkbEmTiC52l0.jpg",
        "genre_ids": [
            35,
            10751,
            18
        ],
        "id": 425001,
        "original_language": "en",
        "original_title": "The War with Grandpa",
        "overview": "Peter is thrilled that his Grandpa is coming to live with his family. That is, until Grandpa moves into Peter's room, forcing him upstairs into the creepy attic. And though he loves his Grandpa, he wants his room back - so he has no choice but to declare war.",
        "popularity": 23.177,
        "poster_path": "/ltyARDw2EFXZ2H2ERnlEctXPioP.jpg",
        "release_date": "2020-08-27",
        "title": "The War with Grandpa",
        "video": false,
        "vote_average": 6.4,
        "vote_count": 575
      }
    ],
    "total_pages": 260,
    "total_results": 5189
  } 
}
</script>

<style lang="scss">

</style>