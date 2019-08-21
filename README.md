# Neural-Style-Transfer
Transferring style to content images

Neural Style transfer using TensorFlow

Import and configure modules

Getting the Content and Style Images Path

Visualize the input

Define content and style representations

Now load a VGG19 without the classification head, and list the layer names

Choose intermediate layers from the network to represent the style and content of the image

Build the model

And to create the model:

Calculate style

Extract style and content

When called on an image, this model returns the gram matrix (style) of the style_layers and content of the content_layers:

Run gradient descent

Define a tf.Variable to contain the image to optimize. To make this quick, initialize it with the content image (the tf.Variable must be 
the same shape as the content image):

Since this is a float image, define a function to keep the pixel values between 0 and 1:

Create an optimizer. The paper recommends LBFGS, but Adam works okay, too:

Use tf.GradientTape to update the image.

Since it's working, perform a longer optimization:

Total variation loss

The regularization loss asociated with this is the sum of the squares of the values:

Re-run the optimization

Thus we have the styled image
