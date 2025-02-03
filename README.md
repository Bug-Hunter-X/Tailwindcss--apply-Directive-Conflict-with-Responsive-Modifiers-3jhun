# Tailwindcss @apply Directive Conflict with Responsive Modifiers

This repository demonstrates a bug related to Tailwind's `@apply` directive when used with responsive modifiers within a parent component that also uses responsive directives. The bug causes unexpected styling behavior where styles are not applied correctly or are overridden.

## Bug Description
When `@apply` is used with a class containing responsive modifiers (e.g., `md:p-4`) inside a component that has its own responsive directives (e.g., `md:container`), there can be conflicts in how Tailwind processes these directives leading to incorrect styling.  This is due to the order of operations during compilation.

## Reproduction
1. Clone this repository.
2. Run `npm install` (or `yarn install`).
3. Run `npm run build` (or `yarn build`).
4. Observe the unexpected styling in the `bug.html` file.  The button padding should only be applied on medium screens and larger, but it might not apply correctly due to the conflict.

## Solution
The solution involves adjusting either the parent component's styles or using more specific selectors in your `@apply` classes to avoid conflicts.  See `bugSolution.html` for a corrected version.