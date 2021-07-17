<template>
  <div id="app">
    <Header />
    <Main :movies="results"/>
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
  data() {
    return {
      "page": 1,
    "results": [
      {
        "adult": false,
        "backdrop_path": "/AcZjBskxs7NioQOVj6DQaMbet34.jpg",
        "genre_ids": [
          27,
          878
        ],
        "id": 48311,
        "original_language": "en",
        "original_title": "Parasite",
        "overview": "Paul Dean has created a deadly parasite that is now attached to his stomach. He and his female companion, Patricia Welles, must find a way to destroy it while also trying to avoid Ricus, his rednecks, and an evil government agent named Merchant.",
        "popularity": 5.082,
        "poster_path": "/6EM7Jm3veKSW9ELMajSSxslYWDa.jpg",
        "release_date": "1982-03-12",
        "title": "Parasite",
        "video": false,
        "vote_average": 4.8,
        "vote_count": 35
      },
      {
        "adult": false,
        "backdrop_path": null,
        "genre_ids": [
          27
        ],
        "id": 291545,
        "original_language": "en",
        "original_title": "Parasite",
        "overview": "An abandoned oil rig in the middle of the North Sea. Dr. Christine Hansen is charged with the task of testing an experimental cleaning fluid which could revolutionize the oil industry. Hired to carry out the tests is Jacob Rasmussen and his rough and ready crew of deconstruction engineers. But within hours one of them is missing under suspicious circumstances. Things go from bad to worse when environmental activist Mickey Hennessey and his hard-bitten associates seize control of the rig, taking everybody on board hostage. But very soon oil workers and environmentalists will be compelled to join forces in an evolutionary battle for survival. For a savage new life-form has made its home on the rig. And it is hungry.",
        "popularity": 1.705,
        "poster_path": "/lDsUWvTHbSsI62u63S8B6Jjgztb.jpg",
        "release_date": "2004-01-01",
        "title": "Parasite",
        "video": false,
        "vote_average": 5.6,
        "vote_count": 12
      },
      {
        "adult": false,
        "backdrop_path": "/TU9NIjwzjoKPwQHoHshkFcQUCG.jpg",
        "genre_ids": [
          35,
          53,
          18
        ],
        "id": 496243,
        "original_language": "ko",
        "original_title": "기생충",
        "overview": "All unemployed, Ki-taek's family takes peculiar interest in the wealthy and glamorous Parks for their livelihood until they get entangled in an unexpected incident.",
        "popularity": 104.151,
        "poster_path": "/7IiTTgloJzvGI1TAYymCfbfl3vT.jpg",
        "release_date": "2019-05-30",
        "title": "Parasite",
        "video": false,
        "vote_average": 8.5,
        "vote_count": 11719
      },
      {
        "adult": false,
        "backdrop_path": null,
        "genre_ids": [],
        "id": 629162,
        "original_language": "en",
        "original_title": "Parasite",
        "overview": "Wherever there is human development, somewhere nature is getting the shorter end of the stick. Every time someone struggles to rise, another barren spot is left behind. Grabbing hands struggle to grasp the beauty that exists in the world. Darkness is always on the other side.",
        "popularity": 0.6,
        "poster_path": "/i81BSTjXnrozgR3oTmAD8JueC0N.jpg",
        "release_date": "",
        "title": "Parasite",
        "video": false,
        "vote_average": 10,
        "vote_count": 1
      },
      {
        "adult": false,
        "backdrop_path": null,
        "genre_ids": [
          27
        ],
        "id": 671137,
        "original_language": "en",
        "original_title": "Parasite",
        "overview": "Young couple gets together with friends for a barbeque, but something in the sink has other plans for tonight...",
        "popularity": 0.6,
        "poster_path": "/pAjExpwZRibYxkRadqd3WdpsLB.jpg",
        "release_date": "2015-08-13",
        "title": "Parasite",
        "video": false,
        "vote_average": 3.5,
        "vote_count": 1
      },
      {
        "adult": false,
        "backdrop_path": "/6uJoEILU61tIzOXRPkC3Rn6bxC3.jpg",
        "genre_ids": [
          27,
          10749
        ],
        "id": 540545,
        "original_language": "en",
        "original_title": "The Parasite",
        "overview": "A young couple is terrorized by a seductive psychic woman. A David Lynch Master's in Film thesis, based on the novelette by Sir Arthur Conan Doyle.",
        "popularity": 0.664,
        "poster_path": "/k6XRlpuSLQjeKfik4tP1vyUhtVb.jpg",
        "release_date": "2015-11-21",
        "title": "The Parasite",
        "video": false,
        "vote_average": 8,
        "vote_count": 1
      },
      {
        "adult": false,
        "backdrop_path": null,
        "genre_ids": [],
        "id": 227625,
        "original_language": "en",
        "original_title": "The Parasite",
        "overview": "A skeptical professor falls under the spell of a powerful hypnotist.",
        "popularity": 0.6,
        "poster_path": "/yMMm5KcfV3WaPmWLgABZDXdMcL2.jpg",
        "release_date": "1997-01-01",
        "title": "The Parasite",
        "video": false,
        "vote_average": 5,
        "vote_count": 1
      },
      {
        "adult": false,
        "backdrop_path": "/wYWNrUfYftKA4Z8xPcmzo90VXUt.jpg",
        "genre_ids": [
          878
        ],
        "id": 825440,
        "original_language": "en",
        "original_title": "The Parasite",
        "overview": "A parasite in a plastic world escapes from its containment field into a futuristic Legoland.",
        "popularity": 0.6,
        "poster_path": "/iWbQejWicvqb37ZqrjmAXssjGc9.jpg",
        "release_date": "1994-03-10",
        "title": "The Parasite",
        "video": false,
        "vote_average": 0,
        "vote_count": 0
      },
      {
        "adult": false,
        "backdrop_path": null,
        "genre_ids": [],
        "id": 830270,
        "original_language": "en",
        "original_title": "Alien Parasite",
        "overview": "After an alien spaceship crash-lands in the middle of the desert, the town starts to fall victim to a parasite that is spreading faster than it can be contained, turning the residents into deadly killing machines. Soon the town must fight back and face something out of this world before it.",
        "popularity": 0.6,
        "poster_path": "/hV1U3mXhSODBZmX1sldiKqVcw7e.jpg",
        "release_date": "2020-08-17",
        "title": "Alien Parasite",
        "video": false,
        "vote_average": 6,
        "vote_count": 1
      },
      {
        "adult": false,
        "backdrop_path": null,
        "genre_ids": [],
        "id": 404280,
        "original_language": "en",
        "original_title": "Parasite Memories: The Making of 'Shivers'",
        "overview": "\"Parasite Memories\" is a brand new retrospective piece on the film produced by High Rising Productions with lively contribution from effects artist Joe Blasco, actresses Lynn Lowry and Barbara Steele, actor Allan Kolman, and Canadian critic Kier La-Janisse.",
        "popularity": 0.6,
        "poster_path": "/AmOcdupFtwrZnkdLoZgYWT2gIcS.jpg",
        "release_date": "2014-10-13",
        "title": "Parasite Memories: The Making of 'Shivers'",
        "video": false,
        "vote_average": 5.5,
        "vote_count": 1
      },
      {
        "adult": false,
        "backdrop_path": "/irMPnAiYRb6Ku4jdnRjQG5g6cqO.jpg",
        "genre_ids": [
          878,
          53
        ],
        "id": 252944,
        "original_language": "ja",
        "original_title": "寄性獣医・鈴音 EVOLUTION",
        "overview": "Set within a city where parasites rage, the parasites settled into their human hosts and increases their power and sexual desires. Dr. Suzune is a parasite expert who works daily to kill the parasites. A sinister demon organization exists behind the parasites. Dr. Suzune also realizes that her father, who went missing when she was a young child, is somehow connected with the group. Violence and madness awaits for her ...",
        "popularity": 2.863,
        "poster_path": "/jVuUlrigERm896IMxSDhDrPcl23.jpg",
        "release_date": "2011-12-04",
        "title": "The Parasite Doctor Suzune: Evolution",
        "video": false,
        "vote_average": 3,
        "vote_count": 3
      },
      {
        "adult": false,
        "backdrop_path": "/oDHhUBssn28vQwSmdrMerfriaOh.jpg",
        "genre_ids": [
          28,
          16,
          878,
          53
        ],
        "id": 80089,
        "original_language": "ja",
        "original_title": "パラサイトドールズ",
        "overview": "Beauty is only skin deep, but when you can’t see beneath the skin, how can you know what you’re really dealing with? In a world where perfect androids called Boomers have infiltrated every aspect of society, it’s the job of Branch to maintain peace between the people and the plastic. Unfortunately, not all boomers are created perfect, and when boomers go bad, people die. The thin blue line that separates man from machine is about to meet its most horrifying test in Parasite Dolls.",
        "popularity": 3.471,
        "poster_path": "/bCDVdpjhqbfMsSg0TlNeGMdg2el.jpg",
        "release_date": "2003-05-22",
        "title": "Parasite Dolls",
        "video": false,
        "vote_average": 5.6,
        "vote_count": 19
      },
      {
        "adult": false,
        "backdrop_path": "/ynYT4ohuJnbkYdb1OYmvD5AiG3A.jpg",
        "genre_ids": [
          10749,
          27,
          878,
          53,
          18
        ],
        "id": 33045,
        "original_language": "ja",
        "original_title": "パラサイト・イヴ",
        "overview": "Toshiaki Nagashima is a biologist who is doing major research on mitochondria. When his beautiful young wife is tragically involved in a car accident which leaves her brain dead, in desperation he steals her liver from her body in order to recieve the mitochondria from it to resurrect his wife from the dead. The killer mitochondria takes the form of his assistant.",
        "popularity": 2.212,
        "poster_path": "/dzQ2VhOLr7UgktlXR4SFTH4VQev.jpg",
        "release_date": "1997-02-01",
        "title": "Parasite Eve",
        "video": false,
        "vote_average": 6.3,
        "vote_count": 15
      },
      {
        "adult": false,
        "backdrop_path": "/aXT34YFLNYAmqfwupO5TjILucTN.jpg",
        "genre_ids": [
          53,
          878
        ],
        "id": 260015,
        "original_language": "ja",
        "original_title": "寄性獣医・鈴音 GENESIS",
        "overview": "The city is infested with mysterious parasites that bore into their human hosts to increase their host's power and sexual desires. A beautiful girl, Suzune Arizono is a vet with a specialty in parasites, and who fights daily to end the plague. Before long, she learns that an evil organization, the Kito Zaibatsu, is behind the explosive growth of this ferocious parasite. She also learns that her long-missing father, Dr. Arizono, is also involved. In order to crush the Kito Zaibatsu's ambition and to see her father again, Suzune takes on the fight without regard to the danger involved.",
        "popularity": 1.425,
        "poster_path": "/knSucdnqvqmOcj32CjVQwmZNqTV.jpg",
        "release_date": "2011-11-26",
        "title": "The Parasite Doctor Suzune: Genesis",
        "video": false,
        "vote_average": 4.8,
        "vote_count": 4
      }
    ],
    "total_pages": 3,
    "total_results": 47
    }
  }
}
</script>

<style lang="scss">
@import "./style/app.scss";
</style>