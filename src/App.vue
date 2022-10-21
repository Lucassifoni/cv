<script setup lang="ts">
import { onMounted, ref } from "vue";
const shownMail = ref("░░░░░░░░░░");

let trigger = () => {
  shownMail.value = '@';
  setTimeout(() => {
    if (shownMail.value.length === 1) {
      shownMail.value += (['info', '.', 'lucassifoni'].reverse().join(''))
    }
  }, 16);
  window.removeEventListener('mousemove', trigger);
  window.removeEventListener('touchstart', trigger);
};

onMounted(() => {
  window.addEventListener('mousemove', trigger);
  window.addEventListener('touchstart', trigger);
});
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
</script>

<template>
  <div class="cv">
    <h2>Lucas Sifoni</h2>
    <header class="columns">
      <div class="header-left">
        <p>Développe et gère des projets d'outils numériques en indépendant depuis 2015.<br><br>Je conçois avec mes
          clients
          des sites et outils internes expressifs, efficaces et ergonomiques, visant toujours à fournir un gain de temps
          à
          leurs utilisateurs.</p>
      </div>
      <div class="header-right">
        <p>contact<span>{{ shownMail }}</span></p>
      </div>
    </header>
    <div class="columns">
      <main>
        <h3>Collaborations et équipes</h3>
        <p>
        <ul class="dates">
          <li>
            2020 &mdash; présent : autour du SIGL libre <a href="https://abelujo.cc">Abelujo</a>
            <p class="small">avec P. Singer et V. Dardel, augmentation des capacités web du logiciel</p>
          </li>
          <li>2018 &mdash; 2022 : avec l'<a href="https://documents.design">Atelier Documents</a>
            <p class="small">gestion, conception et développement de projets web & outils internes, en proche
              collaboration avec A. Lemarchand, L. Savignac et N. Santos, designers.</p>
          </li>
          <li>
            2015 &mdash; présent : collaborations variées
            <p class="small">avec un réseau d'indépendants dans les domaines de la
              typographie, du design graphique, de la programmation, du réseau</p>
          </li>
        </ul>
        </p>

        <h3>Projets choisis</h3>
        <p class="small">La technique est pour beaucoup de structures un mal nécessaire.<br>Dans mes projets favoris, la
          technique simplifie des processus métier laborieux.</p>
        <h4 class="year">2022</h4>
        <ul class="project-list">
          <li>
            <strong>AbjProxy</strong>, monitoring, indexation, proxy API, gestion à distance de
            fonctions web de plusieurs instances du logiciel Abelujo.
            <span class="tags">
              <div class="tag wip">En cours</div>
              <div class="tag elixir">Elixir</div>
              <div class="tag vue">Vue.js</div>
            </span>
          </li>
          <li>
            <strong>Xyver</strong>, API de normalisation de données bibliographiques multi-sources.
            <span class="tags">
              <div class="tag elixir">Elixir</div>
            </span>
          </li>
          <li>pour <strong>AMM</strong>, outil de mise en page & composition accélérée de documents d'appel d'offre pour
            l'agence d'architecture.
            <div class="tags">
              <div class="tag vue">Vue.js</div>
              <div class="tag elixir">Elixir</div>
              <div class="tag maintain">Maintenance / extension</div>
              <div class="tag w2p">Automatisation process</div>
            </div>
          </li>
          <li><strong>Audioskop</strong>, (<a href="https://audioskop.fr">https://audioskop.fr</a>), webapp libre &
            open-source d'exploration de corpus audio avec A. Delinotte et L. Savignac.
            <span class="tags">
              <div class="tag elixir">Elixir</div>
              <div class="tag vue">Vue.js</div>
            </span>
          </li>
        </ul>
        <h4 class="year">2021</h4>
        <ul class="project-list">
          <li>pour <strong>Execo</strong>, outil de génération semi-automatique de dossiers d'appel d'offre
            pour cette agence d'économie de la construction.
            <div class="tags">
              <div class="tag vue">Vue</div>
              <div class="tag kirby">CMS Kirby</div>
              <tag class="tag elixir">Elixir</tag>
              <div class="tag w2p">Automatisation process</div>
            </div>
          </li>
        </ul>
        <ul class="project-list">
          <li>pour <strong>Scalène</strong>, site web stateless puisant ses données d'un ERP développé pour l'agence
            en 2019.
            <div class="tags">
              <div class="tag vue">Vue</div>
              <tag class="tag elixir">Elixir</tag>
            </div>
          </li>
        </ul>
        <h4 class="year">2020</h4>
        <ul class="project-list">
          <li>pour le <strong>Musée des Tissus de Lyon</strong>, gestion du projet de constitution d'une base de données
            normalisée avec les équipes, design & développement back-office, réimplémentation du site web à l'origine
            sous Wordpress.
            <div class="tags">
              <div class="tag vue">Vue</div>
              <div class="tag elixir">Elixir</div>
              <div class="tag etl">ETL</div>
            </div>
          </li>

        </ul>
        <h4 class="year">2019</h4>

        <ul class="project-list">
          <li>pour l'<strong>Orchestre National d'Île-de-France</strong>, développement d'une API privée & publique, design & développement back-office et outils de gestion internes, par dessus la base de donnée historique de l'institution (15 ans).
            <div class="tags">
              <div class="tag vue">Vue / Nuxt</div>
              <div class="tag node">Node</div>
              <div class="tag laravel">Laravel</div>
            </div>
          </li>
          <li>pour le <strong>Musée des Tissus de Lyon</strong>, développement du site web, gateway API unifiant des
            fournisseurs tiers, billetterie temps-réel avec yield management et utilitaire de scan de billets.
            <div class="tags">
              <div class="tag laravel">Vue</div>
              <div class="tag elixir">API Elixir</div>
              <div class="tag wp">Wordpress</div>
            </div>
          </li>
          <li>pour <strong>Scalène</strong>, conception et développement d'un ERP modélisant les process administratifs
            de l'agence, ses données historiques, outils automatisant des sorties de supports métier, et API consommée
            par d'autres outils.
            <div class="tags">
              <div class="tag laravel">Laravel</div>
              <div class="tag etl">ETL</div>
              <div class="tag vue">Vue</div>
              <div class="tag w2p">Automatisation process</div>
            </div>
          </li>
        </ul>
        <h4 class="year">2018</h4>
        <ul class="project-list">
          <li>pour <strong>lab212</strong>, site web multi-tenant / multi-site reprenant l'historique du travail du
            collectif. Design & développement back-office, outils de production de documents normalisés.
            <div class="tags">
              <div class="tag laravel">Laravel</div>
              <div class="tag vue">Vue / Nuxt</div>
              <div class="tag node">Node</div>
              <div class="tag w2p">Automatisation production documents</div>
              <div class="tag rust">Rust</div>
            </div>
          </li>
        </ul>
        <h4 class="year">2017</h4>
        <ul class="project-list">
          <li>pour <strong>Scalène</strong>, projet de R&D visant au design & développement d'outils de travail
            collaboratifs. Applications mobile progressives, scan d'objets & QR Codes, annotation & impression en
            direct, indexation de documents.
            <div class="tags">
              <div class="tag laravel">Laravel</div>
              <div class="tag vue">Vue</div>
              <div class="tag rust">Rust</div>
              <div class="tag w2p">Automatisation process</div>
            </div>
          </li>
          <li>pour <strong>PPA architectures</strong>, design & développement web & back-office. Outils de
            classification de contenus.
            <div class="tags">
              <div class="tag laravel">Laravel</div>
              <div class="tag vue">Vue</div>
            </div>
          </li>
        </ul>
        <h4 class="year">2016</h4>
        <ul class="project-list">
          <li>pour <strong>A+B, designers</strong>, site web incluant une caméra allSky, outil d'automatisation de
            dossiers allant de 3 à 300 pages et aux compositions et contenus variés
            <div class="tags">
              <div class="tag php">PHP</div>
              <div class="tag iot">Raspi + Arduino + caméra</div>
              <div class="tag w2p">Automatisation process</div>
            </div>
          </li>
          <li>pour <strong>l'Heure du Brunch</strong>, site web + flux de commandes, design back-office mobile et
            gestion du site en déplacement via un chatbot SMS liant API twilio et API du site.
            <div class="tags">
              <div class="tag laravel">Laravel</div>
              <div class="tag node">Node</div>
              <div class="tag vue">Vue</div>
            </div>
          </li>
        </ul>
        <h4 class="year">2015</h4>
        <ul class="project-list">
          <li>pour <strong>AMM</strong>, site web générant des documents administratifs à la volée.
            <div class="tags">
              <div class="tag php">PHP</div>
              <div class="tag w2p">Automatisation process</div>
            </div>
          </li>
        </ul>
      </main>
      <aside>
        <h3>Technologies</h3>
        <p>Ma stack usuelle dans un cadre professionnel est la suivante à ce jour :</p>
        <ul>
          <li>
            Backend, domaine métier : Elixir (+ Phoenix)
          </li>
          <li>
            Frontend & UIs : Typescript (+ Vue.js)
          </li>
          <li>
            Data : ETS, sqlite3, PostgreSQL selon besoins
          </li>
          <li>
            CI/CD : Github Actions ou Gitlab CI + Docker
          </li>
          <li>
            Infra : VPSs debian
          </li>
        </ul>
        <p>Dans des projets personnels :</p>
        <ul>
          <li>Haskell (ouvert à l'utiliser quotidiennement)</li>
          <li>Elm (DX excellente)</li>
          <li>Rust (interop. Elixir)</li>
        </ul>
        <h3>Formation</h3>
        <ul class="dates">
          <li>
            2013 &mdash; 2015 : DSAA Design Graphique
            <p class="small">
              Diplôme : système de veille et d’ingestion automatisée d'articles de presse, logiciel d’édition de revues.
            </p>
          </li>
          <li>
            2011 &mdash; 2016 : BTS Design Graphique
            <p class="small">
              Diplôme : conception d’interfaces de navigation gestuelles pour consulter la presse Française.</p>
          </li>
          <li>
            2010 &mdash; 2011 : ManAA
            <p class="small">Redirection vers le milieu du design.</p>
          </li>
          <li>
            2008 &mdash; 2010 : Bac STI Génie Électronique
            <p class="small">Conception d'un système d'orientation de panneaux solaires pour van, programmation de
              microcontrolleurs.</p>
          </li>
          <li>
            2007 &mdash; &infin; : Formation à l'informatique
            <p class="small">
              Informatique théorique, langages de programmation, sans relâche depuis ma rencontre avec Linux en 2007.
            </p>
          </li>
        </ul>
        <h3>Open-Source</h3>
        <p>Mise à disposition open-source de librairies (licence MIT) développées pour certains projets</p>
        <ul>
          <li>
            <a href="https://github.com/documents-org/morris">morris</a>, normalisation de texte sur le web.
          </li>
          <li>
            <a href="https://github.com/documents-org/to_pdf">to_pdf</a>, serveur d'impression multi-moteur
          </li>
          <li><a href="https://github.com/documents-org/buche">buche</a>, éditeur de blocs récursif pour Vue.js</li>
          <li><a href="https://github.com/Lucassifoni/imago">imago</a>, fingerprinting d'image en Elixir + Rust</li>
        </ul>
        <h3>Vers les étoiles</h3>
        <p>Depuis 2019, je construis des téléscopes sur mon
          temps libre et ai acquis des notions d'optique.<br>Interférométrie d'un miroir de téléscope du commerce, puis
          amélioration par mes soins : <a
            href="https://github.com/Lucassifoni/hyperbolic-200mm-f3.5-/">hyperbolic-200mm-f3.5- sur
            github</a>.</p>
      </aside>
    </div>
  </div>
</template>

<style lang="scss">
#app {
  max-width: 1080px;
  margin: auto;
}

.cv {
  width: 100%;
  padding: 1em;

  p {
    max-width: 70ch;

    &.small {
      font-size: .85em;
      font-style: italic;
      margin-top: 0;
    }
  }

  h4.year {
    margin-top: 0;
    margin-bottom: 0;
    font-family: 'Times New Roman', Times, serif;
    font-weight: 400;
    text-align: left;
    max-width: 70ch;
    margin-bottom: .5em;
    &+ul {
      margin-top: 0;
    }
  }

  ul {
    margin-left: 0;
    padding-left: 0;
    list-style-type: none;

    li {
      &::first-letter {
        margin-left: -1em;
      }

      &::before {
        content: "- "
      }

    }
    &.dates {
      li::before {
        display: none;
      }
      li::first-letter {
        margin: 0;
      }
    }
  }

  ul.project-list {
    strong {
      font-family: Arial, Helvetica, sans-serif;
      font-size: .9em;
    }

    li {
      max-width: 70ch;
      margin-bottom: .5em;

      &::first-letter {
        margin-left: -1em;
      }
    }
  }

  .tags {
    display: flex;

    .tag {
      margin: 3px;
      border-radius: 10px;
      font-family: Arial, Helvetica, sans-serif;
      font-size: .75em;
      padding: 2px 6px;
      opacity: .5;

      &.elixir {
        background: rgb(205, 136, 205);
      }

      &.wip {
        background: rgb(179, 215, 240);
      }

      &.vue {
        background: rgb(163, 225, 163);
      }

      &.maintain {
        background: rgb(212, 211, 211);
      }

      &.laravel {
        background: rgb(236, 91, 115);
        color: white;
      }

      &.rust {
        background: chocolate;
      }

      &.iot {
        background: lightblue;
      }

      &.php {
        background: darkblue;
        color: white;
      }

      &.node {
        background: green;
        color: white;
      }

      &.w2p,
      &.etl {
        background: rgb(128, 126, 126);
        color: white;
      }

      &.kirby {
        background: lightpink;
      }
    }
  }

  .columns {
    display: flex;
    width: 100%;
  }

  main,
  .header-left {
    flex: 0 0 calc(100% - 40ch - 1em);
    position: relative;
  }

  aside,
  .header-right {
    flex: 0 0 40ch;
    margin-left: 1rem;
  }
}
</style>
