# Formio


# Configuration Notes

## href Links to other pages

The formio form is loaded in a iframe for various capability and control purposes.

When `href` is required in a form, you typically want to redirect the parent window and not the iframe.

To do this, ensure that your `href` has the attribute `target="_top"`; this will ensure that the parent window is redirected whene the user selects the `href` link.

![formio config for href link of parent window]("resources/href-link.png")
