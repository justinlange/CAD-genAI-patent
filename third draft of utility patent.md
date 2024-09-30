# System and Method for Automated Training Data Generation for AI-Assisted Design Using Object Groupings, Semantic Labeling, and Form Isolation through Systematic Variation

---

## Abstract

The present invention introduces a novel system and method for automating the generation of training data for artificial intelligence (AI)-assisted design applications. It leverages object groupings within computer-aided design (CAD) models to represent design principles and element hierarchies. The system systematically generates variations of the CAD model by altering visual properties, camera viewpoints, lighting conditions, and backgrounds while maintaining the core design form. This approach isolates the form as the constant element, enabling the AI model to learn and understand the form itself without overfitting to specific styles or visual attributes. Semantic labels are generated based on the object groupings and applied variations. The resulting dataset of images and semantic labels is used to train a text-to-image AI model, enabling designers to generate new renderings through natural language prompts that adjust properties like color, material, and finish (CMF) while preserving the original design form. This innovation streamlines the CAD-to-render process, reduces manual effort, and enhances the incorporation of design principles into AI-generated outputs, offering a unique approach to AI-assisted design that maintains designer intent and control.

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

1. **Object Grouping in CAD Models**: Designers utilize existing functionalities within CAD software (such as layers, groups, or tags) to organize objects according to design principles or element hierarchies (e.g., legs, seat, backrest). This labeling facilitates semantic understanding of the design components.

2. **Form Isolation through Systematic Variation**: The system automatically generates variations of the CAD model by systematically altering visual properties (colors, textures, materials), manipulating camera viewpoints (angles, focal lengths), adjusting lighting conditions, and changing backgrounds, while maintaining the core design form as the constant element. This prevents the AI model from overfitting to specific visual attributes and allows it to focus on learning the form itself.

3. **Semantic Label Generation**: For each variation, the system generates semantic labels (text descriptions) based on the object groupings and the specific variations applied. These labels are grammatically correct and descriptive, capturing the essential attributes of each image, including the design hierarchy and visual properties.

4. **Training of AI Model**: The generated dataset of images and corresponding semantic labels is used to train a text-to-image AI model. This model can be based on pre-trained architectures (e.g., Stable Diffusion) and fine-tuned using techniques like Low-Rank Adaptation (LoRA). The training process focuses on enabling the model to learn the core form while being robust to variations in other visual attributes.

5. **AI-Assisted Design Interface**: Designers interact with the trained AI model through a user interface, providing text prompts to generate new renderings that adjust properties like color, material, and finish (CMF) while preserving the original design form.

By automating the data generation process, explicitly focusing on form isolation, and employing systematic variation, the invention enhances the efficiency of the design workflow and the quality of AI-generated outputs. It maintains the designer's control over the core form and enables rapid rendering of design variations in terms of visual properties, streamlining the CAD-to-render process.

---

## Brief Description of the Drawings

1. **Figure 1: System Overview Diagram**

   Illustrates the interaction between the CAD system, the automated data generation module, the AI model training module, and the user interface for AI-assisted design.

2. **Figure 2: CAD Model with Object Groupings**

   Depicts a sample CAD model (e.g., a chair) with visual representations of object groupings, highlighting components such as legs, seat, and backrest.

3. **Figure 3: Form Isolation through Systematic Variation Flowchart**

   Shows the steps involved in systematically generating variations of the CAD model while maintaining the core form, including altering visual properties, camera angles, lighting conditions, and backgrounds.

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

1. **Define Attribute Ranges**: Establish ranges for colors, textures, and materials for each object grouping.

2. **Random Selection**: For each object grouping, randomly select visual attributes from the defined ranges.

3. **Combination Generation**: Generate combinations of visual attributes across object groupings to create diverse variations.

4. **Application**: Apply the selected attributes to the CAD model to create a new variation.

5. **Repeat**: Iterate the process to produce a large dataset of variations.

**Example:**

- For the "legs" component, colors might range from light to dark hues, materials from metal to wood textures.

- For the "seat" component, textures might vary between leather, fabric, or plastic.

By systematically varying these properties, the system ensures a wide representation of visual attributes without emphasizing any particular style.

**b. Camera Viewpoints:**

- **Angles**: Adjusting the camera position to capture the model from multiple perspectives, ensuring comprehensive coverage without over-representing any specific angle.

- **Focal Lengths**: Varying the camera lens settings to simulate different levels of zoom or field of view, capturing the form in various contexts.

**Methods for Creating Different Perspectives:**

1. **Define Camera Positions**: Establish a set of camera positions around the model at various azimuths (0° to 360°) and elevations (0° to 90°).

2. **Systematic Sampling**: Use systematic increments (e.g., every 45° in azimuth and every 15° in elevation) to cover the spherical space around the model.

3. **Focal Length Variation**: Select a range of focal lengths (e.g., 24mm, 35mm, 50mm, 85mm) to vary the field of view.

4. **Application**: Position the camera at each defined point and render the model.

5. **Repeat**: Iterate to capture all combinations of camera positions and focal lengths.

**Example:**

- Capturing images from front, side, back, and isometric views at different elevations ensures the AI model learns the form from all angles.

**c. Lighting Conditions:**

**Algorithm for Varying Lighting:**

1. **Lighting Types**: Utilize different types of lights available in the CAD software, such as ambient light, directional light (e.g., sun), point lights, and spotlights.

2. **Sun Position Variation**:

   - **Azimuth**: Vary the horizontal angle of the sun from 0° to 360° in increments (e.g., every 45°).

   - **Altitude**: Adjust the vertical angle of the sun from 0° (horizon) to 90° (overhead) in increments (e.g., every 15°).

3. **Intensity Modulation**: Change the brightness of the light source using a range of values (e.g., 0.5x to 1.5x the default intensity).

4. **Color Temperature**: Vary the color temperature of the lighting to simulate different times of day (e.g., warm tones for sunrise/sunset, cool tones for midday).

5. **Multiple Light Sources**: Introduce additional lights with varying positions, colors, and intensities to simulate complex lighting environments.

6. **Programmatic Control**: Use scripting capabilities of the CAD software (e.g., Python scripting in Rhinoceros 3D) to automate the adjustments.

**Example Implementations:**

- **Sun Lighting Variation**:

  - Render the model under sunlight at azimuth angles of 0°, 90°, 180°, and 270°, each at altitudes of 15°, 45°, and 75°.

  - Adjust the sun's intensity to simulate different brightness levels.

- **Multiple Light Sources**:

  - Create a three-point lighting setup with key, fill, and rim lights at specified angles and intensities.

- **Time-of-Day Simulations**:

  - Simulate morning light with warm tones and low sun angles.

  - Simulate midday light with neutral tones and high sun positions.

**Corresponding Semantic Labels:**

- "3D render of a chair under bright sunlight, sun positioned at 90° azimuth and 45° altitude."

- "Visualization of the table with soft ambient lighting, key light from the front left, and fill light from the right."

By varying the lighting conditions extensively, the AI model learns to recognize the form under different illumination scenarios, enhancing its robustness.

**d. Backgrounds:**

- **Solid Colors**: Use a range of solid background colors, avoiding over-representation of any particular color.

- **Textures and Patterns**: Apply different textures or patterns to the background, such as gradients, wood grain, or fabric textures.

- **Environmental Contexts**: Include simple environmental backgrounds like indoor rooms or outdoor scenes, ensuring they are varied.

**Algorithm for Varying Backgrounds:**

1. **Define Background Options**: Create a library of background colors, textures, and images.

2. **Random Selection**: For each variation, randomly select a background from the library.

3. **Application**: Apply the background to the scene during rendering.

**Example:**

- Alternate between neutral backgrounds (white, gray) and colored backgrounds (blue, green) to prevent the model from associating the form with a specific background.

#### 3. Semantic Label Generation

For each generated variation, the system creates a semantic label—a text description that encapsulates the key attributes of the image.

**Process of Generating Semantic Labels:**

1. **Extract Object Groupings**: Identify components such as "legs," "seat," "backrest" from the CAD model's metadata.

2. **Record Applied Variations**: Note the specific visual properties, camera settings, lighting conditions, and background used.

3. **Formulate Descriptive Sentences**: Combine the information into a grammatically correct description.

**Examples of Semantic Labels:**

- "A 3D render of a chair with red wooden legs and a black leather seat, viewed from the front at eye level under soft ambient lighting, with a light gray background."

- "An isometric view of a table with metal legs and a glass top, captured under bright sunlight at 270° azimuth and 30° altitude, against a neutral background."

**Label Structure:**

- **Component Descriptions**: Mention materials and colors of each component.

- **Viewpoint Details**: Include camera angle, position, and focal length.

- **Lighting Conditions**: Describe the type of lighting and its parameters.

- **Background Information**: Specify the background color or texture.

#### 4. Training of AI Model

The AI model training module uses the dataset of images and semantic labels to train a text-to-image AI model, focusing on learning the core form while avoiding overfitting to specific visual attributes.

**Training Process:**

1. **Data Preparation**: Organize images and labels, ensuring uniform distribution of variations.

2. **Model Selection**: Use a pre-trained text-to-image model (e.g., Stable Diffusion).

3. **Fine-Tuning with LoRA**:

   - Apply Low-Rank Adaptation to fine-tune the model on the new dataset.

   - LoRA allows efficient fine-tuning by adjusting a small number of parameters.

4. **Training Parameters**:

   - Set appropriate learning rates, batch sizes, and epochs.

   - Monitor training to prevent overfitting.

5. **Validation**:

   - Test the model's ability to generate accurate renderings of the form based on textual prompts.

   - Ensure that the model focuses on the form and correctly applies CMF adjustments.

**Outcome:**

- The AI model learns to associate textual descriptions with the core design form.

- It can generate new renderings that preserve the form while allowing CMF properties to be adjusted through text prompts.

#### 5. AI-Assisted Design Interface

Designers interact with the trained AI model through a user-friendly interface.

**Features of the Interface:**

- **Text Prompt Input**: Designers input natural language descriptions specifying CMF properties and other visual attributes.

- **Real-Time Generation**: The AI model generates renderings based on the prompts.

- **Customization Options**: Options to adjust lighting, camera angles, and backgrounds.

- **Preview and Selection**: Ability to view multiple generated images and select preferred ones.

- **Export Options**: Save high-resolution images or integrate with other design tools.

**Example Interaction:**

- Designer inputs: "Render the chair with chrome metal legs and a white leather seat, viewed from a 45-degree angle under warm indoor lighting."

- The AI model generates the image accordingly, preserving the chair's form.

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

   The system of claim 1, wherein the visual properties comprise at least color, texture, and material properties of the objects, and the systematic alteration is performed using predefined ranges and random selection to prevent overfitting of the AI model to specific visual attributes.

3. **Dependent Claim 3:**

   The system of claim 1, wherein the camera viewpoints comprise variations in camera angle, position, orientation, and focal length, systematically sampled to provide comprehensive coverage of the design form from multiple perspectives.

4. **Dependent Claim 4:**

   The system of claim 1, wherein the lighting conditions include variations in light intensity, direction, color temperature, and type of lighting, applied using algorithmic adjustments and programmatic control to prevent the AI model from associating the form with specific lighting styles.

5. **Dependent Claim 5:**

   The system of claim 1, wherein the backgrounds include variations in background color, texture, pattern, and environmental context, selected from a predefined library to diversify the training data and prevent overfitting.

6. **Dependent Claim 6:**

   The system of claim 1, wherein the semantic labels are generated by combining information from the object groupings and applied variations into descriptive sentences that capture the essential attributes of each image, including component materials, colors, viewpoint details, lighting conditions, and background information.

7. **Dependent Claim 7:**

   The system of claim 1, further comprising an AI model training module configured to:

   - receive the training dataset; and

   - train a text-to-image AI model using the variations and corresponding semantic labels, focusing on learning the core design form while avoiding overfitting to specific visual attributes, by employing techniques such as Low-Rank Adaptation (LoRA).

8. **Dependent Claim 8:**

   The system of claim 7, wherein the AI model training module adjusts training parameters to ensure balanced learning and prevent overfitting, including setting learning rates, batch sizes, and monitoring training progress.

9. **Dependent Claim 9:**

   The system of claim 1, wherein the CAD module allows designers to organize objects using layers, groups, or tags that correspond to the design components, facilitating semantic labeling and systematic variation.

10. **Dependent Claim 10:**

    The system of claim 1, wherein the data generation module uses programmatic control within the CAD software to automate the generation of variations, including scripting capabilities to adjust lighting parameters, camera settings, and apply visual property changes.

11. **Independent Claim 11:**

    A method for generating training data for an artificial intelligence (AI) model for use in design, the method comprising:

    - receiving a CAD model comprising objects grouped according to at least one design principle or hierarchy, wherein the groupings represent components of the design form;

    - generating a plurality of variations of the CAD model by systematically altering visual properties, camera viewpoints, lighting conditions, and backgrounds of the objects in the CAD model while maintaining the core design form as a constant element;

    - generating semantic labels for each variation of the CAD model, the semantic labels comprising text descriptions based on the object groupings and the altered properties of the variations; and

    - outputting a training dataset comprising the variations of the CAD model and the semantic labels.

12. **Dependent Claim 12:**

    The method of claim 11, further comprising training a text-to-image AI model using the training dataset, focusing on enabling the model to learn the core design form while avoiding overfitting to specific visual attributes, by employing fine-tuning techniques such as Low-Rank Adaptation (LoRA).

13. **Dependent Claim 13:**

    The method of claim 11, wherein generating variations includes:

    - Defining attribute ranges for visual properties;

    - Systematically sampling camera viewpoints and lighting conditions;

    - Using programmatic control to automate adjustments;

    - Ensuring comprehensive coverage of variations while maintaining the core design form.

14. **Dependent Claim 14:**

    The method of claim 11, wherein generating semantic labels includes:

    - Extracting component information from object groupings;

    - Recording applied visual properties, camera settings, lighting conditions, and backgrounds;

    - Formulating descriptive sentences that encapsulate the key attributes of each variation.

15. **Dependent Claim 15:**

    The method of claim 11, further comprising providing an AI-assisted design interface configured to:

    - Receive natural language prompts from designers specifying adjustments to visual properties of the design components;

    - Generate rendered images that preserve the core design form while applying the specified adjustments;

    - Allow designers to interactively refine and select generated images.

16. **Dependent Claim 16:**

    The method of claim 11, wherein the variations in visual properties, camera viewpoints, lighting conditions, and backgrounds are designed to prevent the AI model from overfitting to specific attributes and to focus learning on the core design form.

17. **Dependent Claim 17:**

    The system of claim 1, wherein the AI-assisted design interface includes features for adjusting rendering parameters, previewing results, and exporting images, integrating seamlessly into the designer's workflow.

18. **Dependent Claim 18:**

    The method of claim 11, wherein the CAD model comprises annotations or metadata that facilitate the organization of objects according to design components and the generation of semantic labels.

19. **Dependent Claim 19:**

    The system of claim 1, wherein the training dataset enhances the AI model's ability to produce outputs that align with specific designer intents, maintain the integrity of the original design form, and allow for accurate adjustments of CMF properties through natural language prompts.

20. **Dependent Claim 20:**

    The method of claim 11, further comprising validating the AI model's performance by generating test renderings based on sample prompts and comparing them to expected outputs to ensure accuracy and consistency.

---

## Conclusion

The present invention provides a novel system and method for automating the generation of training data for AI-assisted design applications. By leveraging object groupings within CAD models and automating the creation of variations while maintaining the core design form, the invention addresses the limitations of manual data generation and enhances the incorporation of design principles into AI models. This innovation streamlines the CAD-to-render process, reduces manual effort, and maintains the designer's control over the form and visual properties, offering a unique approach to AI-assisted design that aligns with professional design workflows.

---

**Note:** This revised patent draft incorporates detailed explanations and examples throughout, particularly in the sections on varying lighting conditions, visual properties, camera viewpoints, and semantic label generation. The algorithms and methods are specified with step-by-step processes, and examples are provided to illustrate the implementation. The claims have been expanded and detailed to cover the specific aspects of the invention, ensuring comprehensive protection and clarity.

If you require further adjustments or additional details in any specific section, please let me know, and I'll be happy to refine the draft accordingly.