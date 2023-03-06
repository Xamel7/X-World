## CSS Layout

# Flexbox is designed for one-dimensional content. Explain what this means.

# It excels at taking a bunch of items which have different sizes, and returning the best layout for those items.This is the ideal layout model for this sidebar pattern. Flexbox not only helps lay the sidebar and content out inline, but where there's not enough space remaining, the sidebar will break onto a new line. Instead of setting rigid dimensions for the browser to follow, with flexbox, you can instead provide flexible boundaries to hint how the content could display.

# Explain the difference between the main axis and cross axis.

# Flex items move as a group on the main axis. Remember: we've got a bunch of things and we are trying to get the best layout for them as a group.The cross axis runs in the other direction to the main axis, so if flex-direction is row the cross axis runs along the column.

## How can using certain properties of flexbox negatively impact accessibility?

# You should be cautious when using any properties that reorder the visual display away from how things are ordered in the HTML document, as it can negatively impact accessibility. The row-reverse and column-reverse values are a good example of this. The reordering only happens for the visual order, not the logical order. This is important to understand as the logical order is the order that a screen reader will read out the content, and anyone navigating using the keyboard will follow.

# What are some advantages of using flexbox over float?

# Vertically centering a block of content inside its parent.
# Making all the children of a container take up an equal amount of the available width/height, regardless of how much width/height is available.
# Making all columns in a multiple-column layout adopt the same height even if they contain a different amount of content.

# How does this topic connect with your long term goals?

# Mastering CSS Flexbox can help you work more efficiently, create more consistent and responsive layouts, and future-proof your skills as a web designer or developer. It is an essential skill that can help you achieve your long-term goals in the field of web design.