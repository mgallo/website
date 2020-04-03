<script>
  import Square from "../components/Square.svelte";
  import Icon from "svelte-awesome/components/Icon.svelte";
  import { github, twitter } from "svelte-awesome/icons";

  let showingTechnology = 0;
  const technologies = [
    "JavaScript",
    "NodeJS",
    "Ruby",
    "ReactJS",
    "AWS",
    "Flutter",
    "Cordova",
    "Couchbase",
    "MongoDB",
    "PostgresSQL",
    "CSS"
  ];

  const salutations = [
    "Ciao",
    "Hello",
    "Hallo",
    "Namaste",
    "Konnichiwa",
    "Salut",
    "Hola",
    "Olá",
    "Hey",
    "Grüß dich",
    "გამარჯობათ!"
  ];

  const salutation =
    salutations[Math.floor(Math.random() * Math.floor(salutations.length))];
</script>

<style>
  .content {
    max-width: 45rem;
    padding: 1.5em 1em;
    margin: auto;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
  }

  .about {
    font-size: 0.875em;
    animation-name: fadeIn;
    animation-duration: 2s;
    animation-delay: 2.5s;
    animation-fill-mode: both;
    color: #706f70;
  }

  a {
    font-weight: bold;
    color: #ffffff;
  }

  .technologies,
  .hobbies {
    color: #ffff;
    font-weight: bold;
    transition: width 1s;
  }

  #hi * {
    font-size: 2.25em;
    animation-name: fadeIn;
    animation-duration: 2s;
    animation-delay: 2.5s;
    animation-fill-mode: both;
    margin: 0;
    margin-bottom: 0.3em;
  }

  #about-intro {
    font-size: 0.875em;
  }

  #about-intro,
  #about-work,
  #about-hobbies {
    padding-bottom: 1em;
  }

  @keyframes fadeIn {
    from {
      opacity: 0;
    }

    to {
      opacity: 1;
    }
  }
  .about-wrapper {
    display: flex;
    flex-direction: column;
    animation-name: fadeIn;
    animation-duration: 0.3s;
    animation-fill-mode: both;
    transition: opacity 1s;
    z-index: 2;
    text-align: center;
    justify-content: center;
    align-items: center;
  }

  #about-email {
    color: #ffffff;
    font-weight: bold;
  }

  #about-social {
    display: flex;
    flex-direction: row;
    padding-top: 0.3em;
  }

  #about-social a {
    padding: 0.3em;
    color: #706f70;
    transition: color 0.5s;
  }

  #about-social a:hover {
    color: #fff;
  }
</style>

<svelte:head>
  <title>Marco Gallo - Personal Website</title>
</svelte:head>

<div class="content">
  <div class="about-wrapper">
    <Square />
    <div id="hi">
      <h2>{salutation}!</h2>
    </div>
    <div class="about" id="about-intro">
      I'm Marco, a Full-Stack dev from Pavia/Italy.
    </div>
    <div class="about" id="about-work">
      <div>
        I work with
        <b class="technologies">{technologies[showingTechnology]}</b>
      </div>
      <div>to create great solutions for browsers and mobile devices</div>
    </div>
    <div class="about" id="about-hobbies">
      <div>
        Outside of programming, I like
        <b class="hobbies">Synthesizers</b>
      </div>
      <div class="about">
        You can download my resume
        <a href="test">here</a>
      </div>
    </div>
    <div class="about" id="about-email">> mgallo[at]linux[dot]com</div>
    <div class="about" id="about-social">
      <a href="https://github.com/mgallo" rel="noopener" target="_blank">
        <Icon data={github} scale="1.5" />
      </a>
      <a href="https://twitter.com/mgallo_" rel="noopener" ` target="_blank">
        <Icon data={twitter} scale="1.5" />
      </a>
    </div>
  </div>

</div>
