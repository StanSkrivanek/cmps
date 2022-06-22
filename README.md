# Custom CSS Spacing System Generator

This applicalin allow user to create custom spacing system for padding and margin. Build with Svelte.

## SYSTEM

This option offer to choose from

`Custom` - add your own sizes in `SIZE` input

`8pt system` - populate basic sizes in steps from `0` to `160`

`10pt system` - populate basic sizes in steps from `0` to `100`

Both predefined options are editable to be able add and/or remove sizes

## SEAPARATOR

You can set custom separator between prefix _(class name)_ and number that identify size. predefined value is `-`

## UNITS

Choose from two units `px` ot `rem`.


`px` - when code will be generated sizes from `SIZE` input will be used as values in `px`

`rem` - when code will be generated sizes from `SIZE` input will be used as initial values to be recalcluated to `rem` units based on `root size`.

`root size` - set custom font `root size` to calculate `px` to `rem`s. Predefined value is `16`

## CODE PREVIEW

Visual feedback for **seaparator** and **units**.

---

## PREFIX

Input fields for to fill custom prefixes.

`prepoulate` - prepoulate basic prefixes inspred by Tailwind. You can prepoulate for insipiratio and/or **edit** these values.

`Clear All` - will clear all prefixes fields

`show visual` - Visual feeback for prefixes

---

## GENERATE CODE

When you are done trigering button will generate all data into clipborad.

**NOTE:** Generated code will include **negative** margins for `top`, `left`, `bottom` and `right`. these will have letter `n` before prefix.

```css
.nmv-24 {
  margin-top: 1.5rem
  margin-bottom:1.5rem;
 }
```
