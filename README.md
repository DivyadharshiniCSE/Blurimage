import cv2

def blur_image(input_image_path, output_image_path, blur_strength):
    # Read the image
    image = cv2.imread(input_image_path)

    # Check if the image is loaded properly
    if image is None:
        print(f"Error: Unable to read the image from {input_image_path}")
        return

    # Apply the blur operation
    blurred_image = cv2.GaussianBlur(image, (blur_strength, blur_strength), 0)

    # Save the blurred image
    cv2.imwrite(output_image_path, blurred_image)

    print(f"Blurred image saved to {output_image_path}")

# Example usage
input_image_path = "input_image.jpg"  # Replace with the path of your input image
output_image_path = "blurred_image.jpg"  # Replace with the desired output path
blur_strength = 5  # Adjust this value to control the blur strength, e.g., higher value for more blur

blur_image(input_image_path, output_image_path, blur_strength)
# Blurimage
