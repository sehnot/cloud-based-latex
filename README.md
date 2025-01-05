# Cloud-Based LaTeX

A simple and automated workflow for compiling LaTeX documents and generating PDFs in a cloud-based environment using GitHub Actions.

## Features

- **Automated PDF Compilation**: Automatically compiles the `main.tex` file into a PDF every time changes are pushed to the `main` branch.
- **GitHub Actions Integration**: Leverages GitHub Actions to automate the LaTeX build process.
- **Version Control**: Keeps track of changes to both the LaTeX source file and the generated PDF.

## Requirements

- A GitHub repository containing:
  - A `main.tex` file with your LaTeX source code.
  - The provided `update.yml` GitHub Actions workflow file in `.github/workflows/`.
- Basic understanding of LaTeX and GitHub.

## Usage

1. **Clone the Repository**
   ```bash
   git clone https://github.com/sehnot/cloud-based-latex.git
   cd cloud-based-latex
   ```

2. **Set Repository Secrets**
   - Go to the settings of your repository
   - Go to 'Actions secrets and variables'
   - Create two repository secrets
     - `USER` and set the value to your user name
     - `EMAIL` and set the value to your email address; you can find it at: [github.com/settings/emails](https://github.com/settings/emails) 

3. **Edit the LaTeX Source**

   Modify `main.tex` to include your content. You can manage additional .tex files and assets in subfolders if you want to

4. **Push Changes**
   ```bash
   git add main.tex
   git commit -m "Updated LaTeX source"
   git push origin main
   ```

5. **Automatic PDF Generation**

   The GitHub Actions workflow (`update.yml`) compiles the LaTeX source and updates the `main.pdf` file in the repository.

## Workflow Details

The GitHub Actions workflow is defined in `update.yml` and includes the following steps:

1. **Set Up Repository**: Checks out the repository code.
2. **Compile LaTeX Document**: Uses the `xu-cheng/latex-action` action to compile `main.tex`.
3. **Validate PDF**: Ensures that the generated file is a valid PDF.
4. **Commit and Push PDF**: Updates the `main.pdf` file in the repository with the latest version.

A workflow run takes about 90 seconds for starting Ubuntu and installing LaTeX. Add some time depending on your LaTeX files.

## Example

The repository includes a sample LaTeX document (`main.tex`) that generates a simple PDF with an abstract, introduction, and sections. You can replace this with your own content.

## Contributions

Feel free to contribute to this repository by:
- Submitting issues for bugs or enhancements.
- Creating pull requests with new features or fixes.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Author

Created by [Stephan Otto](https://github.com/sehnot).

