## Audio, Video, and Images

# Explain how the ability to use video and audio on the web has evolved since the early 2000s.

# It first started with a with flash and silverlight but over time sites like youtube, dailymotion and vimeo started to surfaces around the 2000's. 

# Describe the use of the src and controls attributes in the <video> element.

# In the same way as for the <img> element, the src (source) attribute contains a path to the video you want to embed. It works in exactly the same way.

#  You must either use the controls attribute to include the browser's own control interface, or build your interface using the appropriate JavaScript API. 

# Why is it important to have fallback content inside the <video> element?

# This will be displayed if the browser accessing the page doesn't support the <video> element, allowing us to provide a fallback for older browsers. This can be anything you like; in this case, we've provided a direct link to the video file, so the user can at least access it some way regardless of what browser they are using.

# Write a very short story where <audio> and <video> are characters.

# Once upon a time, Audio and Video were two inseparable friends in a world of digital technology. They went everywhere together, creating beautiful and immersive experiences for all those who encountered them. One day, they stumbled upon a group of devils who were wreaking havoc on the web. In a quick-thinking effort, Audio played a catchy tune that distracted the devils while Video used its mesmerizing visuals to lull them into a deep sleep. Together, they defeated the devils and saved the internet from their destructive ways. From that day on, Audio and Video became known as the dynamic duo of the digital world, using their powers to create amazing content and protect the internet from any harm that came its way.

# How does Grid layout differ from Flex?

# Grid layout and flexbox are two CSS layout models that differ in their approach and functionality. Flexbox is designed for one-dimensional layouts and allows  you to distribute and align elements along a single axis.

# Grid container, grid item, and grid line are a few important terms to understand when using Grid. Please describe these terms in a few sentences.

# The element on which display: grid is applied. It’s the direct parent of all the grid items. In this example container is the grid container.
# The dividing lines that make up the structure of the grid. They can be either vertical (“column grid lines”) or horizontal (“row grid lines”) and reside on either side of a row or column.
# The children (i.e. direct descendants) of the grid container. Here the item elements are grid items, but sub-item isn’t.

# Besides making a site visually appealing across different screen sizes, why should developers make images responsive?

# It improves user's experience, faster loading times, optimized search engine and reduces the amount of bandwidth usage. 

# Define the following <img> attributes srcset and sizes. Write an example of how they are used.

# srcset defines the set of images we will allow the browser to choose between, and what size each image is. Each set of image information is separated from the previous one by a comma.

# sizes defines a set of media conditions (e.g. screen widths) and indicates what image size would be best to choose, when certain media conditions are true — these are the hints we talked about earlier. 

# How is srcset more helpful for responsive images than CSS or JavaScript?

# That mechanism is useful in general for reducing page load times, but it is not helpful for responsive images — hence the need to implement solutions like srcset.