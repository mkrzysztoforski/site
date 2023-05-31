<script lang="ts">
  import '../style.css'

  let isDarkMode = false;

  function toggleDarkMode() {
    isDarkMode = !isDarkMode;
    const theme = isDarkMode ? 'dark' : 'light';
    document.documentElement.setAttribute('data-theme', theme);
  }
</script>

<div class="main">
  <div class="wrap">
    <h1 class="name">maciej krzysztoforski</h1>
    <span class="line"></span>  
  </div>
  <a class="links" target="_blank" href="https://www.linkedin.com/in/mkrzysztoforski/">(linkedin)</a>
	<a class="links" target="_blank" href="https://github.com/mkrzysztoforski">(github)</a>

  <button class='button' on:click={toggleDarkMode}>COLOR<sup>1</sup></button>
  <span class="span">1. Button for theme toggle.</span>
</div>

<style>
  .button {
    position: absolute;
    padding-left: 10px;
    background: none;
    border: none;
    color: var(--text-color);
    bottom: 30px;
  }

  .button:hover {
    cursor: pointer;
  }

  .span {
    position: absolute;
    color: var(--text-color);
    bottom: 8px;
    font-size: 8px;
  }

  .name {
    position: relative;
		color: var(--text-color);
		font-weight: 200;
    font-size: 30px;
  }

  .wrap {
		width: 280px;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-flow: column;
	}

	.main {
    background-color: var(--background-color);
    color: var(--text-color);
		width: 100%;
		height: 100vh;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-flow: column;
		font-family: 'Roboto', sans-serif;
	}

	.line {
		display: block;
		height: 1px;
		width: 96px;
		background-color: #7f7f88;
		animation: animateLine 5s infinite;
		margin: 0px 0 25px 0;
	}

	.links {
		color: var(--text-color);
		margin-top: 15px;
		letter-spacing: .5px;
		font-weight: 300;
		text-decoration: none;
    position: relative;

	}

  .links:hover {
    color: var(--text-color);
  }

  .links::before {
    content: "";
    position: absolute;
    display: block;
    width: 100%;
    height: 1px;
    bottom: 0;
    left: 0;
    background-color: var(--text-color);
    transform: scaleX(0);
    transition: transform 0.3s ease;
  }

  .links:hover::before {
    transform: scaleX(1);
  }

	@keyframes animateLine {
		0% {
			width: 0;
		}
		25% {
			width: 100%;
			margin-left: 0;
		}
		75% {
			width: 100%;
			margin-left: 0;
		}
		100% {
			margin-left: 100%;
			width: 0;
		}
	}

  :root {
    --background-color: #ded9d3;
    --text-color: #1e1f1f;
  }

  :root[data-theme='dark'] {
    --background-color: #13151a;
    --text-color: #f8f8f8;
  }

</style>
