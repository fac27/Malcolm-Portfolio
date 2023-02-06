## 1. Structure a site using semantic HTML to aid accessibility
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

<section 
    class="section-layout center-items padding-form vertical-flex-layout" 
    id="section-contact"
    >
         <h2 class="vertical-space-lg text-l">Leave us a comment</h2>

        <form id="contact-form">

            <label for="name" class="vertical-stack">NAME</label>
            <input class="input vertical-stack" type="text" id="name" name="name" required>

            <label for="email" class="vertical-stack">EMAIL</label>
            <input class="input vertical-stack" type="email" id="email" name="email" required>

            <label for="comment" class="vertical-stack">YOUR MESSAGE</label>
            <textarea class="input vertical-stack" name="comment" id="comment" rows="10" cols="30" minlength="10" maxlength="150" required></textarea>

            <button type="submit" id="submit" value="Submit">Submit</button>
        </form>
</section>

<footer 
    class="footer horizontal-flex-layout justify-space-between" 
    id="footer"
    >
    <div id="Menu" class="center-items">
        <h3 class="text-s">Menu</h3>
            <p><a href="#section-home">HOME</a></p>
            <p><a href="#section-about">ABOUT</a></p>
            <p><a href="#section-team">THE TEAM</a></p>
            <p><a href="#section-services">SERVICES</a></p>
            <p><a href="#section-contact">CONTACT</a></p>
        </ul>
    </div>

    <div id="address" class="center-items">
        <h3 class="text-s">Address</h3>
            <p>12 Yellow Building</p>
            <p>Orange Avenue</p>
            <p>West Red</p>
            <p>M7 6XU</p>
    </div>

    <div id="contact" class="center-items">
        <h3 class="text-s">Contact</h3>
            <p>E: info(at)youragency.com</p>
            <p>T: +44 800 123 456</p>
            <p>F: +44 800 123 400</p>
    </div>
</footer>
```
- Within our first project, our agency website, we made substantial use of semantic HTML elements as can be seen from the code snippet above (header, nav, section, footer), in order to improve accessibility on our page as well as code readability.

## 2. Ensure a web page is readable for screen readers

## 3. Ensure our UI has sufficient colour contrast so that everyone can perceive it comfortably

## 4. Use various tools to check that our website meets accessibility criteria

## 5. Use CSS media queries to ensure our content is always presented effectively on screens of different sizes

## 6. Demonstrate a mobile-first approach to building a website

## 7. Use CSS variables to apply repeated colours to HTML elements

## 8. Use CSS Flexbox to style children in a single-direction layout (ie a row or a column)

## 9. Use CSS Grid to style children in two-direction layout

## 10. Ensure our Git commit history tells a coherent story

## 11. Use the appropriate input types in HTML forms for gathering different types of information
