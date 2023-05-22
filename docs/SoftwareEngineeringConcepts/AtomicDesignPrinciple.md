---
sidebar_position: 2
---

# Atomic Design Principle

Atomic design principles are a methodology for designing and structuring user interfaces (UI) in a modular and reusable way. It was introduced by Brad Frost and emphasizes breaking down UI components into smaller, independent building blocks. These building blocks are classified into five distinct levels: atoms, molecules, organisms, templates, and pages. Each level represents a different level of complexity and abstraction.

1. Atoms: Atoms are the smallest and simplest UI elements, such as buttons, input fields, or labels. They are the building blocks of all other components and are typically not composed of any other UI elements.

2. Molecules: Molecules are combinations of atoms that form more complex and functional UI components. For example, a form input field with a label and a button can be considered a molecule.

3. Organisms: Organisms are groups of molecules and/or atoms combined together to form a larger and more distinct UI component. They represent sections or modules of a user interface that are composed of multiple molecules and atoms, such as a header, sidebar, or a product card.

4. Templates: Templates define the overall layout and composition of a page by arranging organisms and other components. They establish the structure and provide a framework for the UI content, such as a grid system or a specific arrangement of header, content, and footer.

5. Pages: Pages represent the final UI screens or views seen by the users. They consist of specific instances of templates with actual content.

## How is this principle used in React Js Development?

The atomic design principles can be applied to React development by structuring components in a hierarchical manner that aligns with the atomic design levels. Atoms, molecules, and organisms can be represented as individual React components, which can be composed together to form more complex components. Templates can define the layout and composition of these components, while pages can render specific instances of templates with actual data.

Using atomic design in React encourages component reusability, modularity, and maintainability. It allows for the separation of concerns, making it easier to manage and update UI elements. Developers can build UI components at different atomic levels and assemble them in a consistent and systematic manner. Additionally, it promotes a more scalable and collaborative approach to UI development, as different team members can work on different levels of components concurrently.

Overall, atomic design principles provide a structured approach to UI development in React, resulting in more efficient and manageable codebases.

### Case Study:

![Alt Text](../../src/Assets/instagram-atomic.png)
* Atoms: This screen of Instagram’s UI consists of a handful of icons, some text-level elements, and two image types: the primary image and the user’s avatar image.
Molecules: Several icons form simple utilitarian components like the bottom navigation bar and the photo actions bar where users can like or comment on a photo. Also, simple combinations of text and/or images form relatively simple components.
* Organisms: Here we can see the photo organism take shape, which consists of the user’s information, time stamp, the photo itself, actions around that photo, and information about the photo including like count and caption. This organism becomes the cornerstone of the entire Instagram experience as it is stacked repeatedly in a never-ending stream of user-generated photos.
* Templates: We get to see our components come together in the context of a layout. Also, it’s here where we see the exposed content skeleton of the Instagram experience, highlighting dynamic content such as the user’s handle, avatar, photo, like count, and caption.
* Pages: And finally we see the final product, complete with real content poured into it, which helps ensure the underlying design system comes together to form a beautiful and functional UI.

Reference: https://atomicdesign.bradfrost.com/chapter-2/