## 1. Structure a site using semantic HTML to aid accessibility

![Image of the homepage on our agency website, featuring a large image of turquoise 3d abstract ribbon shapes set against a violet background.](/imagery/Homepage.PNG)

```html
<header
    id="section-home" 
    class="header-img section-layout" 
    style="color:white"
    alt="A surrealist 3d image of a turquoise ribbon pattern set against a violet background."
    >
        <nav 
            id="Nav-menu" 
            class="fixed-nav"
            >
            <div class="hamburger-menu">
                <div class="bar"></div>
                <div class="bar"></div>
                <div class="bar"></div>
            </div>
            <ul id="nav-list" class="no-bullets horizontal-flex-layout nav-text "> 
                <li><a href="#section-home">HOME</a></li>
                <li><a href="#section-about">ABOUT</a></li>
                <li><a href="#section-team">THE TEAM</a></li>
                <li><a href="#section-services">SERVICES</a></li>
                <li><a href="#section-contact">CONTACT</a></li>
            </ul>
        </nav>
    <div 
        id="header-text" 
        class="position-text-right margin-top-xl text-right-margin"
        >
            <h1 class="text-xl">You need a good partner</h1>
            <p class="text-m">Let us help you realise your true potential</p>
    </div>
</header>
```

Within our our agency website project, we made strong use of semantic HTML elements in order to improve accessibility on our page as well as code readability. Visible in the screenshot are the `nav` and `header` elements, which contained our site navigation, text and imagery for the topmost section of our page. 

## 2. Ensure a web page is readable for screen readers

In addition to our use of semantic HTML, we included descriptive alt text in every instance we could to ensure screen readers would capture all image elements of our site correctly. We made use of Microsoft Narrator to go over each area of the page which helped us make decisions to further improve webpage readability.

## 3. Ensure our UI has sufficient colour contrast so that everyone can perceive it comfortably

![Image of our 'About Us' section, showing contrasted black text against grey and white backgrounds.](/imagery/Contrast.PNG)

Our site was built with clear black text in sans serif, and we made use of this across all elements on the page (nav, header, section and footer). `h1`, `h2` and `h3` elements, along with the rest of the text were set against highly contrasted backdrops to ensure maximum readability.

## 4. Use various tools to check that our website meets accessibility criteria

![Image showing our 'Meet The Team' section, displaying next to a window pane with our Google Chrome Lighthouse accessibility score of 100.](/imagery/AccessTools.PNG)

Using Lighthouse within the developer tools for Google Chrome, we tested our site regularly for its accessibility, achieving scores of 100. Lighthouse aided us in improving contrast for certain sections of our website, as well as adding alt text to each element which required it. Moving forwards in my work I would like to implement more extensive usage of accessibility tools alongside like Axe and WAVE, helping to identify any areas for improvement which other tools miss.

## 5. Use CSS media queries to ensure our content is always presented effectively on screens of different sizes

We made use of CSS media queries which displayed our web content suitably on varied screen sizes. In addition, editing our nav bar once screen size was below 700 pixels to display as a toggle hamburger menu ensured smooth browsing and navigation on the page could continue, and made our UI less cluttered.

## 6. Demonstrate a mobile-first approach to building a website

## 7. Use CSS variables to apply repeated colours to HTML elements

## 8. Use CSS Flexbox to style children in a single-direction layout (ie a row or a column)

## 9. Use CSS Grid to style children in two-direction layout

## 10. Ensure our Git commit history tells a coherent story

## 11. Use the appropriate input types in HTML forms for gathering different types of information
