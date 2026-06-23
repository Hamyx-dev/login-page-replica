# Login Page with HTML and CSS

This is what I built after getting an assignment to recreate a login page design using only HTML and CSS, no JavaScript and no AI generated code.

## What I Built

I built a login page that has a username field, a password field, a remember me checkbox, a login button and a log in via section with social icons. The card has a white and purple diagonal background made from layered shapes, not a plain rectangle.

## The HTML Structure

I started by planning out the structure before writing any code. The page has a section that holds a container, the container holds the card, and the card holds two things, the card content and the card background. The card content holds the form and the social login part, and the card background holds four span elements that I use to make the diagonal shapes.

For the form I used a div for each field, with an icon, a label and an input inside. I learnt that the label and the input have to use matching for and id attributes so they are properly connected, and that the input should not be nested inside the label, they should be siblings if you want to control them separately in CSS.

I used type="password" for the password field so the browser hides what you type, and type="checkbox" for remember me. The button uses type="submit" so it behaves like a real form button.

## The CSS

### Centering

I used flexbox on the container to center the card on the page, with justify-content and align-items both set to center. I also had to set height on html and body, because percentage heights do not work unless the parent has a height too.

### The background gradient

I used a linear-gradient on the section for the page background, going from a light purple to a darker purple.

### The diagonal shapes

This was the hardest part. Instead of just using one gradient on the card, I made four separate absolutely positioned shapes inside a card-background div and rotated them with transform rotate to get the white diagonal cutting across the purple card. I had to keep adjusting the top, left, right, bottom and rotation values until the shapes lined up close to the screenshot I was given. I learnt that position absolute only works properly if a parent element has position relative, otherwise the shape positions itself relative to the wrong element.

### Icons

I used img tags for the user icon and the lock icon instead of an icon font, and gave them a fixed width and height in CSS.

### The button

I gave the button a border radius big enough to make it look like a pill shape, a white background with purple text, and a hover effect using transform scale so it grows slightly when you hover over it. I added transition on the normal button state, not on the hover state, because the transition has to be there before the change happens for it to animate both ways.

### Social login icons

I used Font Awesome icons inside circular links for the social login section. I had to remember to add the Font Awesome stylesheet link in the head, because without it the icons just showed as broken symbols instead of actual icons.

## Mistakes I Made and Fixed

1. I closed my div tags in the wrong order a few times. I learnt that whatever tag you open last has to be the one you close first.
2. I nested my input inside my label by mistake instead of making them siblings, which made my labels show no text at all.
3. I forgot units on a few CSS values like top and right, for example writing top: 10 instead of top: 10px. The browser just ignores the whole line when that happens, it does not show an error.
4. I wrote box-shadow with only a color and no offset or blur values, which is not valid, box-shadow needs offset-x, offset-y, blur and then the color.
5. I had a typo in my own code, I wrote 4oopx instead of 400px, which looked correct at first glance because o and 0 look similar.
6. My social login section was getting clipped at the bottom of the card because the card had overflow hidden and not enough height for all the content. I fixed it by setting overflow to visible first to see how much space I was missing, then adjusting my spacing and padding to fit.
7. My input icons were not lining up properly because I mixed two different approaches, one where the icon sits on top of the input and one where the icon sits beside it. I had to pick one and remove the leftover CSS from the other.

## What I Learnt

Building this taught me that getting the HTML structure right first makes the CSS part a lot easier, because if your divs are not nested properly everything you try to style afterward behaves strangely. I also learnt that small CSS mistakes like a missing comma or a missing unit do not throw an error, the browser just silently ignores that line, so you have to check your work carefully in the browser after every change.