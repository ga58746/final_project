# final_project
import matplotlib.pyplot as plt
from PIL import Image, ImageDraw, ImageFont

# Load an image from file
def load_image(file_path):
    return Image.open(file_path)

# Display the image with matplotlib
def display_image(image):
    plt.imshow(image)
    plt.axis('off')  # Hide axes
    plt.show()

# Add text annotations to the image
def annotate_image(image, text, position, font_size=20, color='red'):
    draw = ImageDraw.Draw(image)
    try:
        # Load a font
        font = ImageFont.truetype("arial.ttf", font_size)
    except IOError:
        # If the specific font is not available, use the default font
        font = ImageFont.load_default()
    draw.text(position, text, font=font, fill=color)

# Save the annotated image
def save_image(image, file_path):
    image.save(file_path)

# Main function
if __name__ == "__main__":
    # Path to the image file
    input_image_path = 'input_image.jpg'  # Replace with your image file path
    output_image_path = 'annotated_image.jpg'

    # Load
