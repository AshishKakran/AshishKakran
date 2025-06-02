<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Project Title</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    @layer reset, theme, base, layout, modules, utilities;
   @layer reset {
    *,
    *::before,
    *::after {
        box-sizing: border-box;
    }
    body {
        margin: unset;
    }
    button,
    input,
    textarea,
    select {
        font: inherit;
    }
    img,
    picture,
    svg
    {
        display: block;
        max-inline-size: 100%;
        height: auto;
        aspect-ratio: auto;
        object-fit: contain;
        object-position: center;
    }
    a {
        text-decoration: none;
        color: inherit;
    }
    @media (prefers-reduced-motion: reduce){
        *,
        *::before,
        *::after {
            animation-duration: 0s !important;
            animation-iteration-count: 1 !important;
            transition-duration: 0s !important;
            scroll-behavior: auto !important;
        }
    }
}
    @layer theme {
        :root {
        --primary-color-1: #1A237E;      /* Deep Indigo */
        --primary-color-2: #FFB300;      /* Vivid Amber */
        --secondary-color-1: #E3F2FD;    /* Light Blue */
        --secondary-color-2: #90CAF9;    /* Medium Blue */
        --highlight-color-1: #212121;    /* Almost Black */
        --highlight-color-2: #FFFFFF;    /* White */
        --font-family: 'Inter', 'Segoe UI', 'Roboto', 'Helvetica Neue', Arial, sans-serif;
        --font-family-heading: 'Merriweather', 'Georgia', 'Times New Roman', Times, serif;
        --font-size-base: 16px;
        --font-size-heading: 2rem;
        --font-size-small: 0.875rem;
        --font-size-large: 1.25rem;
        --line-height-base: 1.5;
        --line-height-heading: 1.2;
        --border-radius: 0.25rem;
        --box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }
    }
    @layer base {
    :root {
        font-size: clamp(--var(--font-size-base), 1vw + 1rem, var(--font-size-large));
    }
    body {
        font-family: var(--font-family);
        line-height: var(--line-height-base);
        color: var(--highlight-color-1);
        background-color: var(--highlight-color-2);
    }
    a:any-link {
        color: var(--highlight-color-1);
        text-decoration: none;
        transition: var(--transition);
    }
    h1 {
        font-family: var(--font-family-heading);
        font-size: var(--font-size-heading);
        line-height: var(--line-height-heading);
        color: var(--primary-color-1);
        margin: 0;
        text-align: center;
    }
    h2 {
        font-family: var(--font-family-heading);
        font-size: calc(var(--font-size-heading) * 0.8);
        line-height: var(--line-height-heading);
        color: var(--primary-color-1);
        margin: 0;
    }
    @media (min-width: 768px) {
        body {
            font-size: calc(var(--font-size-base) * 1.125);
        }
        h1 {
            font-size: calc(var(--font-size-heading) * 1.125);
        }
        h2 {
            font-size: calc(var(--font-size-heading) * 0.9);
        }
    }
    @media (min-width: 1024px) {
        body {
            font-size: calc(var(--font-size-base) * 1.25);
        }
        h1 {
            font-size: calc(var(--font-size-heading) * 1.25);
        }
        h2 {
            font-size: calc(var(--font-size-heading) * 1);
        }
    }
    @media (min-width: 1440px) {
        body {
            font-size: calc(var(--font-size-base) * 1.5);
        }
        h1 {
            font-size: calc(var(--font-size-heading) * 1.5);
        }
        h2 {
            font-size: calc(var(--font-size-heading) * 1.125);
        }
    }
    p {
        font-size: var(--font-size-base);
        line-height: var(--line-height-base);
        margin: 0 0 1rem;
    }
    ul, ol {
        margin: 0 0 1rem 1.5rem;
        padding: 0;
        list-style: none;
        font-size: var(--font-size-base);
        line-height: var(--line-height-base);
    }
    li {
        margin-bottom: 0.5rem;
    }
    img {
        max-width: 100%;
        height: auto;
        display: block;
    }
    button {
        font-family: inherit;
        font-size: inherit;
        line-height: inherit;
        color: inherit;
        background-color: transparent;
        border: none;
        cursor: pointer;
        transition: var(--transition);
    }
    button:hover,
    button:focus {
        color: var(--primary-color-2);
        background-color: var(--secondary-color-1);
        box-shadow: var(--box-shadow);
        transform: scale(1.02);
    }
    input,
    textarea,
    select {
        font-family: inherit;
        font-size: inherit;
        line-height: inherit;
        color: inherit;
        background-color: var(--highlight-color-2);
        border: 1px solid var(--primary-color-1);
        border-radius: var(--border-radius);
        padding: 0.5rem;
        transition: var(--transition);
    }
    input:focus,
    textarea:focus,
    select:focus {
        border-color: var(--primary-color-2);
        outline: none;
        box-shadow: 0 0 0 3px rgba(244, 206, 20, 0.3);
    }
}
@layer layout {
    .container {
        display: grid;
        grid-template-columns: 1fr;
        grid-auto-rows: auto;
        gap: 2rem;
        max-width: 900px;
        margin: 0 auto;
        padding: 2rem 1rem;
    }
    @layer modules {
    .button {
        display: inline-block;
        padding: 0.5rem 1rem;
        font-size: var(--font-size-base);
        font-family: var(--font-family);
        color: var(--highlight-color-2);
        background-color: var(--primary-color-2);
        border: none;
        border-radius: var(--border-radius);
        box-shadow: var(--box-shadow);
        cursor: pointer;
        transition: var(--transition);
        &:hover {
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            transform: translateY(-2px);
        }
        &:active {  
            box-shadow: none;
            transform: translateY(0);
        }
    }
    ul {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
        gap: 1rem;
        padding: 0;
        list-style: none;
        margin: 0;   
    }
    ul li {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: flex-start;
        gap: 0.5rem;
        width: 280px;
        min-height: 220px;
        margin-bottom: 1rem;
        padding: 1rem;
        background-color: var(--secondary-color-1);
        border-radius: var(--border-radius);
        box-shadow: var(--box-shadow);
        transition: background-color 0.3s ease;
        text-align: left;
        &:hover {
            background-color: var(--secondary-color-2);
        }
        img {
            align-self: center;
            margin-bottom: 0.5rem;
        }
        .button {
            align-self: stretch;
            margin-bottom: 0.5rem;
        }
        .description {
            flex: 1;
        }
        a {
            color: var(--highlight-color-1);
            font-weight: bold;
            text-decoration: underline;
        }
    }
}

  </style>
</head>
<body>
<div class="container"> 
<h1> Hello there 👋 </h1>
<main class="main-content">

<section class="projects frontend">
<h2>Frontend Projects</h2>
<ul>
<li>
    <img src="./code_icon.svg" alt="project image"/> 
    <button class="button"> 
        <a href="https://github.com/AshishKakran/mangata-gallo">Mangata Gallery</a>
    </button> 
    <p class="description">A gallery website showcasing images with a clean, responsive and modern design using Vanilla CSS and Javascript.</p>
</li>
<li>
    <img src="./code_icon.svg" alt="project image"/> 
    <button class="button">
     <a href="https://github.com/AshishKakran/littlelemon">Little Lemon</a>
    </button>
    <p class="description"> A restaurant website built with React, featuring a menu, reservation system, and customer reviews.</p>

</li>
</ul>
</section>

<section class="projects backend">
<h2>Backend Projects</h2>
<ul>
<li>
    <img src="./code_icon.svg" alt="project image"/> 
   <button class="button">
        <a href="https://github.com/AshishKakran/backend-capstone/tree/main/api"> Little Lemon API</a>
    </button>
    <p class="description"> A RESTful API for the Little Lemon restaurant, built with Django, django-rest-framework, MySql and djoser, providing endpoints for login and reservations.</p>
</li>
<li>
    <img src="./code_icon.svg" alt="project image"/> 
    <button class="button">
        <a href="https://github.com/AshishKakran/MyCloud">MyCloud</a>
        </button>
    <p class="description">A mockup of cloud storage service API, allowing users to upload, download, and manage files securely. This was developed during internship at one.com in 2019.</p>
</ul>


<section class="projects challenges">
<h2>Challenges</h2>
</section>
<ul>
<li>
    <img src="./code_icon.svg" alt="project image"/> 
    <button class="button">
        <a href="https://github.com/AshishKakran/Shopify-challenge">Shopify Challenge</a>
    </button>
    <p class="description"> Fall 2022 Data science intern hiring challenge at spotify</p>
</li>
<li>
    <img src="./code_icon.svg" alt="project image"/> 
    <button class="button">
        <a href="https://github.com/AshishKakran/british-airways-grad-challenge">British Airways Grad Challenge</a>
    </button>
    <p class="description"> Jan 2023 Data science graduate program hiring challenge at British Airways</p>
</li>
<li>
    <img src="./code_icon.svg" alt="project image"/> 
    <button class="button">
        <a href="https://github.com/AshishKakran/90day-coding-streak-challenge">90 Day Coding Streak Challenge</a>
    </button>
    <p class="description"> A personal challenge to code every day for 90 days, building the coding habits again</p>
</li>
<li>
    <img src="./code_icon.svg" alt="project image"/> 
    <button class="button">
        <a href="https://github.com/AshishKakran/nao-internship-challenge">Nao Internship Challenge</a>
    </button>
    <p class="description"> A data science internship challenge for hiring at National Audit Office, UK</p>
</li>
</ul>
</section>
<section class="projects learning">
<h2>Learning repos (active)</h2>
<ul>
<li>
    <img src="./code_icon.svg" alt="project image"/> 
    <button class="button">
        <a href="https://github.com/AshishKakran/learn-web">Learn Web</a>
    </button>
    <p class="description"> A personal project to learn full stack web development, covering HTML, CSS, JavaScript, and React.</p>
    </li>  
<li>
    <img src="./code_icon.svg" alt="project image"/> 
    <button class="button">
        <a href="https://github.com/AshishKakran/learn-ML">Learn ML</a>
    </button>
    <p class="description"> A personal project to learn machine learning, covering Python, Pandas, NumPy, Scikit-learn, and TensorFlow.</p>
</ul>
</section>

</main>

</div>
</body>
</html>