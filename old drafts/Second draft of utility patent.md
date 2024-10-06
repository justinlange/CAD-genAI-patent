# System and Method for Automated Training Data Generation for AI-Assisted Design Using Object Groupings, Semantic Labeling, and Form Isolation through Systematic Variation

---

## Abstract

The present invention introduces a novel system and method for automating the generation of training data for artificial intelligence (AI)-assisted design applications. It leverages object groupings within computer-aided design (CAD) models to represent design principles and element hierarchies. The system systematically generates variations of the CAD model by altering visual properties, camera viewpoints, lighting, and backgrounds while maintaining the core design form. This approach isolates the form as the constant element, enabling the AI model to learn and understand the form itself without being overfitted to specific styles or visual attributes. Semantic labels are generated based on the object groupings and applied variations. The resulting dataset of images and semantic labels is used to train a text-to-image AI model, enabling designers to generate new renderings through natural language prompts that adjust properties like color, material, and finish (CMF) while preserving the original design form. This innovation streamlines the CAD-to-render process, reduces manual effort, and enhances the incorporation of design principles into AI-generated outputs, offering a unique approach to AI-assisted design that maintains designer intent and control.

---

## Background of the Invention

### Field of the Invention

The present invention relates to the fields of artificial intelligence (AI)-assisted design, computer-aided design (CAD), computer graphics, and machine learning. It specifically focuses on automating the creation of training datasets for AI models used in design applications by leveraging object groupings, semantic labeling, and form isolation through systematic variation within CAD models.

### Description of the Related Art

Traditionally, the design and rendering process in industrial and product design is labor-intensive and time-consuming. Designers manually create 3D models using CAD software and then proceed to render these models, adjusting materials, textures, lighting, and camera angles to produce high-quality images. This process requires specialized skills and significant time investment, often limiting the ability to explore multiple design variations rapidly.

Existing AI-based design tools have attempted to alleviate some of these challenges by generating designs or renderings based on pre-trained models. However, these models often rely on manually created training data that may not explicitly incorporate specific design principles or hierarchies. Consequently, the AI-generated outputs may lack the desired level of control, precision, and alignment with the designer's intent.

Several patents and publications have addressed related aspects of AI training data generation and image processing:

1. **US20190156487A1** describes a method for automated generation of pre-labeled training data for machine learning models, focusing on image segmentation and masking techniques.

2. **US20220215145A1** presents a system for machine learning in rapid automatic computer-aided engineering modeling, emphasizing mesh generation for engineering analysis.

3. **US11308357B2** discusses training data generation for automated driving systems, utilizing sensor data from vehicles.

While these patents offer valuable contributions to their respective fields, they do not address the specific challenges of AI-assisted design in CAD contexts, nor do they employ the unique approach of form isolation through systematic variation of all other elements to prevent overfitting and preserve the integrity of the designer's original form.

### Problems to be Solved by the Invention

1. **Automation of Training Data Generation**: There is a need for a system that automates the creation of training datasets for AI models in design contexts, reducing manual effort and accelerating the design process.

2. **Form Isolation for AI Learning**: Current approaches lack a method to isolate the core design form as the constant element while varying all other aspects, limiting the AI's ability to understand and generate design forms effectively.

3. **Avoiding Overfitting in AI Models**: AI models may become overfitted to specific styles, visual properties, or perspectives if training data is not sufficiently varied, hindering their ability to generalize and adapt to different contexts.

4. **Integration of CAD and AI**: There is a gap in seamlessly integrating CAD workflows with AI-assisted design tools, hindering the adoption of AI in professional design processes.

5. **Maintaining Designer Control**: Existing AI-assisted design tools often lack the ability to incorporate specific design intents and principles, limiting designer control over the outputs, especially in adjusting CMF properties without altering the core form.

---

## Summary of the Invention

The present invention addresses the aforementioned problems by providing a system and method for automating the generation of training data for AI-assisted design applications. The key aspects of the invention include:

1. **Object Grouping in CAD Models**: Designers utilize existing functionalities within CAD software (such as layers, groups, or tags) to organize objects according to design principles or element hierarchies (e.g., dominant, subdominant, subordinate elements). This labeling facilitates semantic understanding of the design components.

2. **Form Isolation through Systematic Variation**: The system automatically generates variations of the CAD model by systematically altering visual properties (colors, textures, materials), manipulating camera viewpoints (angles, focal lengths), adjusting lighting conditions, and changing backgrounds, while maintaining the core design form as the constant element. This prevents the AI model from overfitting to specific visual attributes and allows it to focus on learning the form itself.

3. **Semantic Label Generation**: For each variation, the system generates semantic labels (text descriptions) based on the object groupings and the specific variations applied. These labels are grammatically correct and descriptive, capturing the essential attributes of each image, including the design hierarchy and visual properties.

4. **Training of AI Model**: The generated dataset of images and corresponding semantic labels is used to train a text-to-image AI model. This model can be based on pre-trained architectures (e.g., Stable Diffusion) and fine-tuned using techniques like Low-Rank Adaptation (LoRA). The training process focuses on enabling the model to learn the core form while being robust to variations in other visual attributes.

5. **AI-Assisted Design Interface**: Designers interact with the trained AI model through a user interface, providing text prompts to generate new renderings. The AI model leverages its understanding of the form to produce outputs that align with the designer's intent, allowing adjustments to properties like color, material, and finish (CMF) through natural language, without altering the core form.

By automating the data generation process, explicitly focusing on form isolation, and employing systematic variation, the invention enhances the efficiency of the design workflow and the quality of AI-generated outputs. It maintains the designer's control over the core form and enables rapid rendering of design variations in terms of visual properties, streamlining the CAD-to-render process.

---

## Brief Description of the Drawings

1. **Figure 1: System Overview Diagram**

   Illustrates the interaction between the CAD system, the automated data generation module, the AI model training module, and the user interface for AI-assisted design.

2. **Figure 2: CAD Model with Object Groupings**

   Depicts a sample CAD model (e.g., a chair) with visual representations of object groupings, highlighting dominant, subdominant, and subordinate elements.

3. **Figure 3: Form Isolation through Systematic Variation Flowchart**

   Shows the steps involved in systematically generating variations of the CAD model while maintaining the core form, including altering visual properties, camera angles, lighting, and backgrounds.

4. **Figure 4: Semantic Label Generation Diagram**

   Demonstrates how semantic labels are generated and associated with each variation based on object groupings and applied changes.

5. **Figure 5: AI Model Training Process**

   Illustrates the process of training the text-to-image AI model using the generated dataset of images and semantic labels, emphasizing the isolation of the form and prevention of overfitting.

6. **Figure 6: AI-Assisted Design Interface Mockup**

   Provides a visual representation of the user interface where designers interact with the trained AI model using text prompts to generate new renderings that adjust CMF properties while preserving the core form.

---

## Detailed Description of the Invention

### System Components

The invention comprises the following main components:

1. **CAD System**: A computer-aided design software platform used to create and manipulate 3D models. It provides functionalities for organizing objects within the model using layers, groups, tags, or similar mechanisms to represent design principles and hierarchies.

2. **Automated Data Generation Module**: A software module that interfaces with the CAD system to perform the following functions:

   - **Identification of Object Groupings**: Recognizes the organization of objects within the CAD model based on layers, groups, or tags that represent design principles or hierarchies.

   - **Generation of Variations**: Automatically produces multiple variations of the CAD model by systematically altering visual properties, camera viewpoints, lighting conditions, and backgrounds while maintaining the core design form.

   - **Semantic Labeling**: Generates descriptive text labels for each variation, capturing the essential attributes of each image, including object groupings and applied variations.

3. **AI Model Training Module**: A component responsible for training a text-to-image AI model using the generated dataset. It utilizes pre-trained models and applies fine-tuning techniques, such as Low-Rank Adaptation (LoRA), to adapt the model to the specific design data while focusing on the core form.

4. **AI-Assisted Design Interface**: A user interface that allows designers to interact with the trained AI model, providing text prompts to generate new renderings that adjust CMF properties while preserving the core form.

### Process Steps

#### 1. Object Grouping in CAD Model

Designers create 3D models using the CAD system and organize objects according to specific design principles or hierarchies. This organization is achieved using existing CAD functionalities:

- **Layers**: Objects are assigned to different layers representing their role in the design (e.g., legs, seat, backrest).

- **Groups**: Objects are grouped together based on functional or aesthetic categories.

- **Tags**: Metadata tags are attached to objects to indicate their characteristics or relationships.

**Examples of Design Principles:**

- **Component Identification**: Categorizing elements based on their function within the design.

- **Functional Groupings**: Grouping objects based on their functional roles (e.g., structural supports, surfaces, connectors).

- **Aesthetic Categories**: Organizing elements by aesthetic attributes such as color schemes, textures, or materials.

#### 2. Form Isolation through Systematic Variation

The automated data generation module produces multiple variations of the CAD model by systematically altering specific parameters while maintaining the core form. This approach isolates the design form as the constant element, enabling the AI model to learn about the form itself without overfitting to specific styles or visual attributes.

**a. Visual Properties:**

- **Colors**: Systematic changes to the color of objects, ensuring coverage of different color palettes while preventing overfitting to specific colors.

- **Textures**: Applying various texture maps to surfaces to simulate materials like wood, metal, fabric, etc., without establishing a bias toward any particular texture.

- **Materials**: Changing material properties such as glossiness, reflectivity, transparency, ensuring the model does not associate the form with specific material attributes.

**Algorithm for Varying Visual Properties:**

- Iterate over object groupings.

- For each grouping, randomly select visual attributes from a predefined set.

- Apply combinations of attributes to generate distinct variations, ensuring that no single visual property becomes dominant in the training data.

**b. Camera Viewpoints:**

- **Angles**: Adjusting the camera position to capture the model from multiple perspectives, ensuring comprehensive coverage without over-representing any specific angle.

- **Focal Lengths**: Varying the camera lens settings to simulate different levels of zoom or field of view, capturing the form in various contexts.

**Methods for Creating Different Perspectives:**

- Define a set of camera positions relative to the model's bounding box, covering all sides and angles.

- Systematically select camera positions and orientations to ensure uniform distribution across the dataset.

- Focus on capturing the entire form within the frame to utilize the full pixel resolution for the form itself, given the limitations of image size in the training set.

**c. Lighting Conditions:**

- **Intensity**: Modulating the brightness of the lighting setup to prevent the model from associating the form with specific lighting conditions.

- **Direction**: Changing the angle of light sources to create different shadow effects, providing depth cues and perspective context.

- **Color**: Altering the color temperature or hue of the lights to vary the lighting conditions.

**Algorithm for Varying Lighting:**

- Use a combination of ambient, directional, point, and spotlights.

- Randomly adjust lighting parameters within predefined ranges. 

- Ensure that the lighting variations are sufficient to prevent overfitting to specific lighting styles.

For example, in a CAD software like Rhinoceros 3D, we can utilize the properties of the 'Sun' lighting element to algorithmically manipulate the rendered look of the various images in the corpus of training images:

1. Azimuth: Systematically vary the horizontal angle of the sun from 0 to 360 degrees in predetermined increments (e.g., every 45 degrees).
2. Altitude: Adjust the vertical angle of the sun from 0 (horizon) to 90 degrees (directly overhead) in set increments (e.g., every 15 degrees).
3. Intensity: Modulate the brightness of the sun using a range of values (e.g., from 0.5 to 1.5 times the default intensity).

These parameters can be programmatically adjusted using Rhino's scripting capabilities (e.g., Python or Grasshopper) to generate a diverse set of lighting conditions. 

Correspondingly, the system can automatically generate accurate text labels for each variation, such as:

"3D render of [object] under bright sunlight, sun position: 45 degrees east of south, 30 degrees above horizon"
"[Object] visualization with soft afternoon lighting, sun at 270 degrees azimuth, 15 degrees altitude"

This approach ensures a wide range of lighting scenarios while maintaining precise control and documentation of the lighting conditions used in each training image.

Additionally, we can expand our lighting variations to include more complex scenarios:

1. Multiple Light Sources: Introduce multiple light sources with varying intensities and colors to simulate complex lighting environments. For example:
   - "Chair render with warm key light from the left and cool fill light from the right"
   - "Table visualization under three-point lighting setup: key light at 45 degrees, fill light at -45 degrees, and rim light at 180 degrees"

2. Time-of-Day Simulations: Create lighting presets that mimic different times of day:
   - "Outdoor bench model at golden hour, with low-angle warm sunlight and long shadows"
   - "Street lamp design under simulated moonlight with soft, cool ambient illumination"

3. Weather-Based Lighting: Incorporate lighting variations that suggest different weather conditions:
   - "Product render on a cloudy day with diffused, even lighting from all directions"
   - "Outdoor furniture set visualized during a stormy scene with dramatic, high-contrast lighting"

4. Interior Lighting Scenarios: For products designed for indoor use, simulate various interior lighting conditions:
   - "Office chair model under fluorescent ceiling lights with subtle shadows"
   - "Dining table render with warm, low-hanging pendant lights and candle accents"

5. Industry-Specific Lighting: Tailor lighting setups to specific use cases or industries:
   - "Medical device visualization under bright, neutral operating room lighting"
   - "Automotive interior render with dashboard illumination and ambient LED accent lighting"

By incorporating these additional lighting scenarios, we further enhance the AI model's ability to understand and generate designs under a wide array of lighting conditions, making it more versatile and applicable across various design contexts.

**d. Backgrounds:**

- **Colors**: Using solid color backgrounds with varying hues to prevent the model from associating the form with a particular background color.

- **Textures**: Applying different background textures or patterns.

- **Images**: Including various environmental contexts, if appropriate, to diversify the background settings.

#### 3. Semantic Label Generation

For each generated variation, the system creates a semantic label—a text description that encapsulates the key attributes of the image.

**Process of Generating Semantic Labels:**

- **Extract Information from Object Groupings**: Identify the roles and characteristics of objects based on their groupings (e.g., "legs", "backrest", "seat").

- **Describe Applied Variations**: Note the specific visual properties, camera settings, lighting conditions, and background used in the variation (e.g., "blue plastic legs", "viewed from a 45-degree angle", "soft ambient lighting").

- **Formulate Descriptive Sentences**: Combine the extracted information into grammatically correct sentences or captions (e.g., "A 3D render of a chair with blue plastic legs and a red wooden seat, viewed from the front under soft ambient lighting").

**Examples of Semantic Labels:**

- "A 3D render of a chair with metal legs and a leather seat, viewed from the side at eye level under bright studio lighting with a neutral gray background."

- "An isometric view of a table with glass top and wooden legs, captured under warm ambient lighting, against a textured backdrop."

#### 4. Training of AI Model

The AI model training module uses the dataset of images and semantic labels to train a text-to-image AI model, focusing on learning the core form while avoiding overfitting to specific visual attributes.

**Training Process:**

- **Data Preparation**: Organize the images and corresponding labels into a format suitable for training, ensuring that variations are evenly distributed.

- **Model Selection**: Choose a pre-trained text-to-image model (e.g., Stable Diffusion) as the foundation.

- **Fine-Tuning Techniques**: Apply methods like Low-Rank Adaptation (LoRA) to fine-tune the model on the specific dataset, allowing efficient adaptation while keeping the majority of the model's parameters fixed.

- **Avoiding Overfitting**: By varying all visual attributes except the form, the training process ensures that the model focuses on learning the form itself.

- **Validation**: Evaluate the model's ability to generate images that accurately reflect the original form when provided with appropriate text prompts, adjusting training parameters as necessary.

**Outcomes of Training:**

- The AI model learns to associate textual descriptions with the design form, allowing for accurate rendering of the form in response to natural language prompts.

- The model becomes robust to variations in visual properties, lighting, and backgrounds, enabling it to generate images that preserve the core form while allowing adjustments in CMF properties.

#### 5. AI-Assisted Design Interface

Designers interact with the trained AI model through a user-friendly interface.

**Features of the Interface:**

- **Text Prompt Input**: Designers input natural language descriptions of the desired rendering, specifying adjustments to CMF properties (e.g., "render the chair with cherry wood legs and a black leather seat").

- **Real-Time Generation**: The AI model generates visual outputs based on the input prompts, preserving the core form and applying the specified CMF adjustments.

- **Customization Options**: Users can adjust parameters such as materials, colors, lighting styles within the interface.

- **Iteration and Refinement**: Designers can refine their prompts or select preferred outputs for further development.

**Benefits:**

- Accelerates the rendering process by allowing rapid generation of high-quality images without manual adjustments in rendering software.

- Provides a collaborative tool that enhances creativity while maintaining designer control over the form and visual properties.

- Enables designers to explore different CMF variations quickly, aiding in decision-making and presentation.

---

## Claims

### **What is claimed is:**

1. **Independent Claim 1:**

   A system for generating training data for an artificial intelligence (AI) model for use in design, the system comprising:

   - **a computer-aided design (CAD) module** configured to:

     - receive a CAD model comprising objects grouped according to at least one design principle or hierarchy, wherein the groupings represent components of the design form; and

     - generate a plurality of variations of the CAD model by systematically altering visual properties, camera viewpoints, lighting conditions, and backgrounds of the objects in the CAD model while maintaining the core design form as a constant element; and

   - **a data generation module** configured to:

     - generate semantic labels for each variation of the CAD model, the semantic labels comprising text descriptions based on the object groupings and the altered properties of the variations; and

     - output a training dataset comprising the variations of the CAD model and the semantic labels.

2. **Dependent Claim 2:**

   The system of claim 1, wherein the visual properties comprise at least one of color, texture, and material properties of the objects, and the systematic alteration is performed to prevent overfitting of the AI model to specific visual attributes.

3. **Dependent Claim 3:**

   The system of claim 1, wherein the camera viewpoints comprise variations in at least one of camera angle, position, orientation, and focal length, selected to provide comprehensive coverage of the design form from multiple perspectives.

4. **Dependent Claim 4:**

   The system of claim 1, wherein the lighting conditions include variations in at least one of light intensity, direction, color temperature, and type of lighting, applied to prevent the AI model from associating the form with specific lighting styles.

5. **Dependent Claim 5:**

   The system of claim 1, wherein the backgrounds include variations in at least one of background color, texture, pattern, and environmental context, selected to diversify the training data and prevent overfitting.

6. **Dependent Claim 6:**

   The system of claim 1, wherein the semantic labels are generated by combining information from the object groupings and applied variations into descriptive sentences that capture the essential attributes of each image.

7. **Dependent Claim 7:**

   The system of claim 1, further comprising an AI model training module configured to:

   - receive the training dataset; and

   - train a text-to-image AI model using the variations and corresponding semantic labels, focusing on learning the core design form while avoiding overfitting to specific visual attributes.

8. **Dependent Claim 8:**

   The system of claim 7, wherein the AI model training module utilizes a pre-trained text-to-image model and fine-tunes it using techniques including Low-Rank Adaptation (LoRA).

9. **Dependent Claim 9:**

   The system of claim 1, wherein the CAD module is further configured to:

   - allow designers to organize objects using layers, groups, or tags that correspond to the design components, facilitating semantic labeling.

10. **Dependent Claim 10:**

    The system of claim 1, wherein the data generation module is further configured to:

    - systematically vary visual properties, camera viewpoints, lighting conditions, and backgrounds in a manner that ensures no single attribute becomes dominant in the training data.

11. **Independent Claim 11:**

    A method for generating training data for an artificial intelligence (AI) model for use in design, the method comprising:

    - receiving a CAD model comprising objects grouped according to at least one design principle or hierarchy, wherein the groupings represent components of the design form;

    - generating a plurality of variations of the CAD model by systematically altering visual properties, camera viewpoints, lighting conditions, and backgrounds of the objects in the CAD model while maintaining the core design form as a constant element;

    - generating semantic labels for each variation of the CAD model, the semantic labels comprising text descriptions based on the object groupings and the altered properties of the variations; and

    - outputting a training dataset comprising the variations of the CAD model and the semantic labels.

12. **Dependent Claim 12:**

    The method of claim 11, further comprising training a text-to-image AI model using the training dataset, focusing on enabling the model to learn the core design form while avoiding overfitting to specific visual attributes.

13. **Dependent Claim 13:**

    The method of claim 12, wherein the training includes fine-tuning a pre-trained AI model using Low-Rank Adaptation (LoRA) techniques.

14. **Dependent Claim 14:**

    The method of claim 11, wherein generating variations includes systematically altering parameters within predefined ranges to ensure comprehensive coverage of diverse representations while maintaining the core design form.

15. **Dependent Claim 15:**

    The method of claim 11, wherein the semantic labels are used to enhance the explainability and interpretability of the AI model's outputs by linking visual characteristics to specific design components.

16. **Dependent Claim 16:**

    The method of claim 11, further comprising providing an interface for designers to interact with the trained AI model using text prompts to generate new renderings that adjust color, material, and finish properties while preserving the core design form.

17. **Dependent Claim 17:**

    The method of claim 11, wherein the variations in visual properties, camera viewpoints, lighting conditions, and backgrounds are designed to prevent the AI model from overfitting to specific attributes and to focus learning on the core design form.

18. **Dependent Claim 18:**

    The system of claim 1, wherein the AI-assisted design interface is configured to:

    - receive natural language prompts from designers specifying adjustments to visual properties of the design components; and

    - generate rendered images that preserve the core design form while applying the specified adjustments.

19. **Dependent Claim 19:**

    The method of claim 11, wherein the CAD model comprises annotations or metadata that facilitate the generation of semantic labels and the organization of objects according to design components.

20. **Dependent Claim 20:**

    The system of claim 1, wherein the training dataset enhances the AI model's ability to produce outputs that align with specific designer intents and maintain the integrity of the original design form.

---

## Conclusion

The present invention provides a novel system and method for automating the generation of training data for AI-assisted design applications. By leveraging object groupings within CAD models and automating the creation of variations while maintaining the core design form, the invention addresses the limitations of manual data generation and enhances the incorporation of design principles into AI models. This innovation streamlines the CAD-to-render process, reduces manual effort, and maintains the designer's control over the form and visual properties, offering a unique approach to AI-assisted design that aligns with professional design workflows.

---

**Note:** This patent draft has been tailored to reflect your specific requirements, emphasizing the preservation of the core design form, the purpose of systematic variation in preventing overfitting, and the ability for designers to adjust CMF properties through natural language prompts. It integrates relevant design principles where appropriate, focusing on object groupings and design hierarchies without altering the core form. The claims have been crafted to cover the key aspects of the invention, providing comprehensive protection while aligning with your research objectives.

If you have any further feedback or need additional revisions, please let me know, and I'll be happy to assist.