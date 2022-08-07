<script>
  import About from "./components/About.svelte";
  import ButtonCount from "./components/ButtonCount.svelte";
  import Input from "./components/Input.svelte";
  import Person from "./components/Person.svelte";
  import Photos from "./components/Photos.svelte";
  import Skills from "./components/Skills.svelte";
  import Text from "./components/Text.svelte";
  export let name;
  export let lastName;
  let svelteLogo = "https://arepa.s3.amazonaws.com/svelte-logo.png";

  const data = {
    name: "arepa",
    lastName: "svelte",
    age: 31,
  };
</script>

<main>
  <h1>Hello {name} {lastName}!</h1>
  <p>
    Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn
    how to build Svelte apps.
  </p>
  <About />
  <Text anotherText="Hola" />
  <Text />
  <Person name={data.name} lastName={data.lastName} age={data.age} />
  <Person {...data} />
  <Skills />
  <Input />
  <ButtonCount />
  <Photos />
  <img src={svelteLogo} alt="Svelte" />
</main>

<style>
  :global(body) {
    background-color: #f2eee2;
    color: #0084f6;
  }

  :global(:root) {
    --theme-color: purple;
    font-size: 22px;
  }

  :global(body.dark-mode) {
    background-color: #1d3040;
    color: #bfc2c7;
  }

  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  main img {
    width: 30%;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
