# Ernie-Fine-Tune
From PDF to interactive web: seamless OCR to dynamic page deployment
My Journey with PaddleOCR-VL and ERNIE: Building and Fine-Tuning for Real-World Impact
Inspiration
The growing need for automating text extraction from complex PDF layouts and converting them into web-friendly formats inspired my project. Seeing the potential of PaddleOCR-VL's ability to extract both text and layout, combined with ERNIE's powerful language understanding, made me eager to build an end-to-end pipeline that not only extracts content but also generates webpages for easy deployment and sharing.
The rise of fine-tuning pretrained models like ERNIE on domain-specific tasks motivated me to explore optimization techniques using tools like Unsloth and LLaMA-Factory, aiming to push the boundaries of model performance on impactful real-world applications.
What I Learned
	Layout-aware OCR: PaddleOCR-VL excels not only in recognizing text but also preserving the spatial structure, which is crucial for transforming documents into structured Markdown.
	Markdown Generation: Converting extracted layouts into Markdown requires carefully mapping visual elements like headings, paragraphs, lists, and tables into proper Markdown syntax, ensuring readability and retaining meaning.
	Fine-tuning Techniques: Using Unsloth and LLaMA-Factory helped me understand domain adaptation and transfer learning for ERNIE, improving task-specific accuracy.
	End-to-end deployment: Hosting the generated webpages on GitHub Pages taught me how to automate workflows for continuous deployment.
Building the Project
	Extracting from PDFs with PaddleOCR-VL
I processed multiple PDF documents using PaddleOCR-VL to extract detected text blocks along with their layout coordinates. This step resulted in a JSON-like structure representing the document content and spatial information.
	Converting to Markdown
Using the layout metadata, I wrote scripts to:
	Identify headings by font size and position.
	Detect lists and tables.
	Format paragraphs and inline elements.
	The output was clean, well-structured Markdown files ready for further processing.
	Using ERNIE for Webpage Generation
I fine-tuned ERNIE models via:
	Unsloth — for optimizing on informal text generation tasks, improving contextual relevance.
	LLaMA-Factory — for generating polished HTML from Markdown, leveraging ERNIE's text understanding.
	This resulted in fully styled HTML webpages derived from the content.
	Deploying with GitHub Pages
The final HTML outputs were pushed to GitHub repositories configured for GitHub Pages. With continuous integration, every update to the Markdown automatically rebuilt and deployed the webpage.
Challenges Faced
	Complex Layouts: Some PDF layouts included multi-column texts and nested tables, challenging Markdown conversion to maintain content fidelity.
	Fine-tuning Stability: Achieving stable convergence while fine-tuning ERNIE models required careful hyperparameter tuning and regular evaluation.
	Markdown-to-HTML Quality: Ensuring the ERNIE-generated HTML preserved all Markdown semantics and styling was tough, needing iteration on training data and prompts.
	Deployment Automation: Setting up a seamless pipeline from OCR extraction to web deployment required scripting and debugging in GitHub Actions.
Mathematical Note on Fine-tuning
The core optimization during fine-tuning minimizes the loss function
L(θ)=-∑_(i=1)^N▒  log⁡p_θ (y_i |x_i)
where θ are the parameters of ERNIE, x_i the input sequences, and y_i the target outputs, summed over training samples N.
By adjusting θ via gradient descent methods, the model adapts to the specific task domains, improving output quality.
