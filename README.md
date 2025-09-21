# Generative Showdown: A Comparative Study of GANs and Diffusion Models

This repository documents a deep learning project that conducts a comparative analysis of various generative models. It explores the capabilities and shortcomings of classic Generative Adversarial Networks (Vanilla GAN and DCGAN) and contrasts them with the state-of-the-art performance of Stable Diffusion. The project's goal is to demonstrate the evolution of generative AI and highlight why diffusion models represent a significant leap forward in generating high-fidelity, coherent images.

## **Project Motivation**

The demand for unique, high-quality visual content is ever-increasing across creative and technical fields. While traditional content creation is resource-intensive, generative models offer a transformative solution. This project investigates different architectures to understand their practical effectiveness, training stability, and the quality of their generated outputs, culminating in a demonstration of Stable Diffusion's superior capabilities.

## **Models Explored**

This project implements and evaluates three distinct generative architectures.

### **1. Vanilla GAN**

The foundational Generative Adversarial Network. This model implements the original GAN concept where a generator and a discriminator are trained in a competitive setting. While revolutionary, it is often plagued by training instability and mode collapse.
* **Implementation**: See the `vanilla_GAN/` directory.

### **2. Deep Convolutional GAN (DCGAN)**

An evolution of the Vanilla GAN, the DCGAN incorporates deep convolutional layers, which stabilizes training and allows the model to learn more complex image features. It represents a significant improvement but can still suffer from issues like discriminator dominance.
* **Implementation**: See the `DC_GAN/` directory.

### **3. Stable Diffusion**

A state-of-the-art text-to-image model based on a diffusion process. Instead of generating an image in a single step, it iteratively refines a random noise tensor, removing noise according to text prompts to produce a final, coherent image. This method results in significantly higher photorealism and structural integrity.
* **Implementation**: See the `STABLE_DIFFUSION/` directory.

## **Project Findings and Results**

Our analysis, summarized in the project poster below, reveals a clear hierarchy in performance. While GANs are foundational, they exhibit significant flaws that are overcome by the diffusion architecture.

![Project Poster](POSTER/[POSTER]%20Group%204%20Final%20Project%20_%20Deep%20Learning%20LB09.png)

### **Key Takeaways:**

* **GAN Instability**: Both the **Vanilla GAN** and **DCGAN** suffered from severe training instability. The discriminator often overpowered the generator, leading to a failure to converge and produce diverse, high-quality images. This is confirmed by their high Fréchet Inception Distance (FID) scores (**Vanilla GAN: 282.96**, **DCGAN: 158.92**).
* **Mode Collapse**: The GAN models frequently experienced mode collapse, where the generator produces a very limited variety of outputs, regardless of the input noise.
* **Diffusion Superiority**: The **Stable Diffusion** model consistently produced images with vastly superior photorealism, detail, and structural coherence. Its iterative denoising process proves to be a more robust and effective approach for high-fidelity image synthesis, effectively addressing the failures of older GAN architectures.

## **Deployment**

To provide an interactive demonstration of the GAN models, a web application was built using Streamlit. This app allows users to load the pre-trained Vanilla GAN and DCGAN generator models and generate new images on demand.

* **Deployment Code**: The application and pre-trained model weights (`.h5` files) are located in the `DEPLOY_VANILLA_DC_GAN_MODEL/` directory.

## **How to Use This Repository**

Each model is contained within its own directory, complete with its own set of dependencies.

1.  **Clone the repository:**
    ```sh
    git clone [https://github.com/your_username/Generative-Showdown-GANs-vs-Diffusion-Models.git](https://github.com/your_username/Generative-Showdown-GANs-vs-Diffusion-Models.git)
    ```
2.  **Navigate to a model's directory:**
    ```sh
    cd vanilla_GAN  # Or DC_GAN, STABLE_DIFFUSION, etc.
    ```
3.  **Install the required packages:**
    ```sh
    pip install -r requirements.txt
    ```
4.  **Run the notebooks or applications** as described within each folder. For the deployment app, run:
    ```sh
    streamlit run DEPLOY_VANILLA_DC_GAN_MODEL/app.py
    ```

## **Acknowledgements and Citations**

The implementation of the Stable Diffusion model in this project was heavily guided by external resources. We extend our gratitude and credit to the following sources for their invaluable contributions to the field and our understanding:

* **Primary Tutorial**: The core structure of our Stable Diffusion code is adapted from the comprehensive tutorial by **AI PPRENTICE** on YouTube.
    * **Video**: [Stable Diffusion from Scratch - All the math and code](https://youtu.be/ZBKpAp_6TGI?si=oLSO6ujfDgbJNNB9)

* **Foundational Research Papers**: Our work is built upon the pioneering research detailed in the following papers:
    * Ho, J., & Salimans, T. (2022). **Classifier-Free Diffusion Guidance**. *arXiv preprint arXiv:2207.12598*.
    * Ho, J., Jain, A., & Abbeel, P. (2020). **Denoising Diffusion Probabilistic Models**. *Advances in Neural Information Processing Systems, 33*, 6840-6851.
