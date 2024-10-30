# Office of the Chief Data Officer (OCDO) - Data Science Team

Welcome to the GitHub organization of the **Data Science Team** within the **Office of the Chief Data Officer (OCDO)** at **Health Canada**. We operate under the **Digital Transformation Branch (DTB)**.

---

## Table of Contents

- [About Us](#about-us)
- [Our Projects and Repositories](#our-projects-and-repositories)
  - [Key Projects](#key-projects)
    - [File-Processing Suite of Python Libraries](#file-processing-suite-of-python-libraries)
    - [Other Repositories](#other-repositories)
- [Repository Versioning Protocol](#repository-versioning-protocol)

---

## About Us

The **OCDO Data Science Team** is dedicated to accelerating Health Canada's data-enabled digital transformation. We serve as an **Enabler, Facilitator, and Champion** for data projects across the department, providing expertise in data science, analytics, and data-enabled transformation projects.

## Our Projects and Repositories

Our team engages in a variety of projects to support data science initiatives within Health Canada. Below are some of our key repositories:

### Key Projects

#### File-Processing Suite of Python Libraries

The **file-processing suite** is a collection of Python libraries designed to generalize and streamline the processing of diverse file types.

##### 1. [file-processing](https://github.com/hc-sc-ocdo-bdpd/file-processing)

The core library that provides a generalized `File` class using a strategy pattern to select appropriate processors based on file extensions. It supports over 20 unique file processors and extracts metadata and text from files.

##### 2. [file-processing-ocr](https://github.com/hc-sc-ocdo-bdpd/file-processing-ocr)

Extends `file-processing` by enabling Optical Character Recognition (OCR) capabilities. It wraps around relevant file types to extract text from images and scanned documents. Currently utilizes Tesseract OCR.

##### 3. [file-processing-transcription](https://github.com/hc-sc-ocdo-bdpd/file-processing-transcription)

Adds transcription capabilities to `file-processing` by processing audio and video files. Uses OpenAI Whisper for transcribing speech to text.

##### 4. [file-processing-analytics](https://github.com/hc-sc-ocdo-bdpd/file-processing-analytics)

Designed for analyzing collections of files. It iterates through directories, creating `File` objects, collecting metadata, and outputting results to a CSV file.

##### 5. [file-processing-models](https://github.com/hc-sc-ocdo-bdpd/file-processing-models)

Integrates machine learning models into the file-processing suite. Extends file processors to include functionalities like loading models, performing inferences, and creating embeddings.

##### 6. [file-processing-indices](https://github.com/hc-sc-ocdo-bdpd/file-processing-indices)

Facilitates the creation and management of indices (e.g., FAISS) for efficient data retrieval in RAG LLMs. Includes functionality for loading and searching indices.

##### 7. [file-processing-test-data](https://github.com/hc-sc-ocdo-bdpd/file-processing-test-data)

A collection of over 100 sample files used for testing across the file-processing suite, ensuring robustness and reliability. The sample files are generic and publicly available, containing no sensitive or proprietary information, and their content is unrelated to our organization's operations.

##### Diagram of the File-Processing Suite

![File-Processing Suite Diagram](https://github.com/hc-sc-ocdo-bdpd/.github/blob/main/src/Concept_IDP_Suite_Diagram.jpg)

*Conceptual diagram illustrating the relationships between the libraries in the file-processing suite.*

---

#### Use Case Example: Retrieval-Augmented Generation (RAG) LLM

An example workflow using our file-processing suite:

1. **Data Extraction**: Use `file-processing-analytics` to collect file paths and extract text from a company's directory.
2. **Embedding Creation**: Employ `file-processing-models` to create embeddings of the extracted text.
3. **Indexing**: Utilize `file-processing-indices` to build a FAISS index from the embeddings.
4. **Query Handling**: When a user submits a query, search the FAISS index using `file-processing-indices` to retrieve relevant context.
5. **Response Generation**: Feed the user's prompt and retrieved context into the model using `file-processing-models` to generate an answer.

---

### Other Repositories

#### [Python_Container_Demo](https://github.com/hc-sc-ocdo-bdpd/Python_Container_Demo)

Docker templates for data science applications, including:

- A web application
- Jupyter Notebook examples
- A security-focused "isolated" container
- A GPU-enabled notebook example

#### [Python_demo](https://github.com/hc-sc-ocdo-bdpd/Python_demo)

A simple template demonstrating essential components of a Python library, such as project structure and test cases.

#### [uml_generation](https://github.com/hc-sc-ocdo-bdpd/uml_generation)

Code to automatically generate UML diagrams from a codebase. Aims to provide UML diagrams for all our repositories to enhance understanding and documentation.

---

## Repository Versioning Protocol

Our versioning protocol ensures consistency and traceability across all repositories:

- **Major Releases**: Indicate feature additions (e.g., `1.0`, `2.0`). Labeled using Git tags.
- **Minor Releases**: Include bug fixes and minor improvements (e.g., `1.1`, `1.2`).
- **Branching Strategy**:
  - Releases live only in the `main` branch.
  - Development occurs in `dev` or feature branches before merging into `main`.
- **Changelog**: All updates are summarized in a `CHANGELOG.md` file within each repository.

---

*We are committed to fostering collaboration and innovation within Health Canada and beyond. Explore our repositories, contribute, or get in touch to learn more about our work.*