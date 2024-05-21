## Structured template for the literature review. To host on GitHub Pages and enabled to be filled out in the browser, downloaded, or shared through email.

### *Template for Literature Review Notes*
---

1. __Citation__
    - Author(s):
    - Title:
    - Journal/Source:
    - Year:
    - DOI/URL:
2. __Summary__
    - Terminology:
    - Key Points:
    - Research Questions:
    - Methodology:
3. __Findings__
    - Main Findings:
    - Data and Evidence:
4. __Relevance__
    - Relevance to Your Research:
    - Gaps Identified:
    - Future Research Directions:

---

__Hosting on GitHub Pages:__
To create a webpage where you can fill out this template and download it, a combination of HTML, CSS, and JavaScript is used:
- *example:*

__HTML__ (index.html):
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Literature Review Template</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>Literature Review Notes</h1>
    <form id="literature-review-form">
        <section>
            <h2>Citation</h2>
            <label>Author(s): <input type="text" id="authors"></label><br>
            <label>Title: <input type="text" id="title"></label><br>
            <label>Journal/Source: <input type="text" id="journal"></label><br>
            <label>Year: <input type="text" id="year"></label><br>
            <label>DOI/URL: <input type="text" id="doi"></label><br>
        </section>
        <section>
            <h2>Summary</h2>
            <label>Key Points: <textarea id="key-points"></textarea></label><br>
            <label>Research Questions: <textarea id="research-questions"></textarea></label><br>
            <label>Methodology: <textarea id="methodology"></textarea></label><br>
        </section>
        <section>
            <h2>Findings</h2>
            <label>Main Findings: <textarea id="findings"></textarea></label><br>
            <label>Data and Evidence: <textarea id="data"></textarea></label><br>
        </section>
        <section>
            <h2>Relevance</h2>
            <label>Relevance to Your Research: <textarea id="relevance"></textarea></label><br>
            <label>Gaps Identified: <textarea id="gaps"></textarea></label><br>
            <label>Future Research Directions: <textarea id="future-research"></textarea></label><br>
        </section>
        <section>
            <h2>Personal Notes</h2>
            <textarea id="personal-notes"></textarea><br>
        </section>
        <button type="button" onclick="generateFile()">Download Notes</button>
    </form>
    <script src="scripts.js"></script>
</body>
</html>
```

__CSS__ (styles.css):
```css
body {
    font-family: Arial, sans-serif;
    margin: 20px;
}

h1, h2 {
    color: #333;
}

label {
    display: block;
    margin: 10px 0;
}

textarea, input[type="text"] {
    width: 100%;
    padding: 10px;
    margin-top: 5px;
    border: 1px solid #ccc;
    border-radius: 5px;
}

button {
    display: inline-block;
    margin-top: 20px;
    padding: 10px 20px;
    background-color: #5cb85c;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #4cae4c;
}
```

__JavaScript__ (scripts.js):
```javascript
function generateFile() {
    const authors = document.getElementById("authors").value;
    const title = document.getElementById("title").value;
    const journal = document.getElementById("journal").value;
    const year = document.getElementById("year").value;
    const doi = document.getElementById("doi").value;
    const keyPoints = document.getElementById("key-points").value;
    const researchQuestions = document.getElementById("research-questions").value;
    const methodology = document.getElementById("methodology").value;
    const findings = document.getElementById("findings").value;
    const data = document.getElementById("data").value;
    const relevance = document.getElementById("relevance").value;
    const gaps = document.getElementById("gaps").value;
    const futureResearch = document.getElementById("future-research").value;
    const personalNotes = document.getElementById("personal-notes").value;

    const content = `
# Citation
- **Author(s):** ${authors}
- **Title:** ${title}
- **Journal/Source:** ${journal}
- **Year:** ${year}
- **DOI/URL:** ${doi}

# Summary
- **Key Points:**
${keyPoints.split('\n').map(point => '  - ' + point).join('\n')}
- **Research Questions:**
${researchQuestions.split('\n').map(question => '  - ' + question).join('\n')}
- **Methodology:**
${methodology.split('\n').map(method => '  - ' + method).join('\n')}

# Findings
- **Main Findings:**
${findings.split('\n').map(finding => '  - ' + finding).join('\n')}
- **Data and Evidence:**
${data.split('\n').map(evidence => '  - ' + evidence).join('\n')}

# Relevance
- **Relevance to Your Research:**
${relevance.split('\n').map(rel => '  - ' + rel).join('\n')}
- **Gaps Identified:**
${gaps.split('\n').map(gap => '  - ' + gap).join('\n')}
- **Future Research Directions:**
${futureResearch.split('\n').map(direction => '  - ' + direction).join('\n')}

# Personal Notes
${personalNotes}
`;

    const blob = new Blob([content], { type: "text/plain" });
    const url = URL.createObjectURL(blob);
    const a = document.createElement("a");
    a.href = url;
    a.download = "literature_review_notes.txt";
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
}
```

__To Host on GitHub Pages:__
- Create repository on GitHub.
- Add the HTML, CSS, and JavaScript files to the repository.
- Go to the repository settings, scroll down to the "GitHub Pages" section, and set the source to the main branch (or the branch where your files are located).
Thiswebpage can be filled out with the literature review template and have the literature review downloaded as a text file. To add functionality for exporting as PDF or DOCX, will need to integrate libraries like `jsPDF` or `docx.js`. Additionally, to share directly to __Google Drive__, need to use the __Google Drive API__.

---

To create a network that connects information, questions, and sources, I will use a combination of front-end and back-end technologies. A step-by-step approach is outlined here:

1. Choose a Visualization Library
D3.js: A powerful JavaScript library for creating dynamic, interactive data visualizations in the web browser.
Cytoscape.js: A graph theory library for visualization and analysis.
2. Set Up Your Project
Frontend: Use HTML, CSS, and JavaScript.
Backend: Use a server-side technology like Node.js to manage data and connections.
3. Design the Network Structure
Nodes: Represent papers, questions, and sources.
Edges: Represent the relationships between these nodes.
4. Create a Basic HTML Structure

__HTML__ (index.html):
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Literature Review Network</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>Literature Review Network</h1>
    <div id="network"></div>
    <form id="add-node-form">
        <h2>Add a Node</h2>
        <label>Type: 
            <select id="node-type">
                <option value="paper">Paper</option>
                <option value="question">Question</option>
                <option value="source">Source</option>
            </select>
        </label><br>
        <label>Label: <input type="text" id="node-label"></label><br>
        <button type="button" onclick="addNode()">Add Node</button>
    </form>
    <form id="add-edge-form">
        <h2>Add an Edge</h2>
        <label>Source Node ID: <input type="text" id="source-id"></label><br>
        <label>Target Node ID: <input type="text" id="target-id"></label><br>
        <button type="button" onclick="addEdge()">Add Edge</button>
    </form>
    <script src="https://unpkg.com/cytoscape/dist/cytoscape.min.js"></script>
    <script src="scripts.js"></script>
</body>
</html>
```

5. Add Styles
__CSS__ (styles.css):
```css
body {
    font-family: Arial, sans-serif;
    margin: 20px;
}

h1, h2 {
    color: #333;
}

#network {
    width: 100%;
    height: 500px;
    border: 1px solid #ccc;
    margin-bottom: 20px;
}

form {
    margin-bottom: 20px;
}

label {
    display: block;
    margin: 10px 0;
}

input[type="text"], select {
    width: 100%;
    padding: 10px;
    margin-top: 5px;
    border: 1px solid #ccc;
    border-radius: 5px;
}

button {
    display: inline-block;
    margin-top: 20px;
    padding: 10px 20px;
    background-color: #5cb85c;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #4cae4c;
}
```

6. Implement JavaScript for Network Visualization
__JavaScript__ (scripts.js):
```javascript
document.addEventListener('DOMContentLoaded', function () {
    const cy = cytoscape({
        container: document.getElementById('network'),
        style: [
            {
                selector: 'node',
                style: {
                    'background-color': '#666',
                    'label': 'data(label)'
                }
            },
            {
                selector: 'edge',
                style: {
                    'width': 3,
                    'line-color': '#ccc',
                    'target-arrow-color': '#ccc',
                    'target-arrow-shape': 'triangle'
                }
            }
        ],
        elements: [],
        layout: {
            name: 'grid',
            rows: 1
        }
    });

    window.addNode = function () {
        const type = document.getElementById('node-type').value;
        const label = document.getElementById('node-label').value;
        cy.add({
            group: 'nodes',
            data: { id: label, label: `${type}: ${label}` }
        });
        cy.layout({ name: 'grid', rows: 1 }).run();
    };

    window.addEdge = function () {
        const source = document.getElementById('source-id').value;
        const target = document.getElementById('target-id').value;
        cy.add({
            group: 'edges',
            data: { id: `${source}-${target}`, source: source, target: target }
        });
        cy.layout({ name: 'grid', rows: 1 }).run();
    };
});
```

7. Hosting on GitHub Pages
Push your project files to a GitHub repository.
Go to the repository settings, scroll down to the "GitHub Pages" section, and set the source to the main branch (or the branch where your files are located).
8. Additional Features
Data Persistence: Use a database like Firebase or MongoDB to store nodes and edges, so they persist across sessions.
Export/Import: Add functionality to export the network to a JSON file and import it back, allowing for easier sharing and continuation of work.
Advanced Visualization: Enhance the network visualization with more sophisticated layouts, clustering, and styling using Cytoscape.js or D3.js.
By following these steps, you can create a comprehensive tool for managing and visualizing connections between literature review notes, questions, and sources, hosted on GitHub Pages.

To accommodate literature reviews that span multiple pages and provide the option to append different reviews into one extended PDF document, you'll need to enhance the initial setup with additional features. This includes handling multi-page inputs and using a library to create and manage PDFs. Here's how you can approach this:

1. Frontend Enhancements
Enhance the HTML form to allow multiple pages for each literature review.

HTML (index.html)
html
Copy code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Literature Review Network</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>Literature Review Network</h1>
    <div id="network"></div>
    
    <form id="add-node-form">
        <h2>Add a Node</h2>
        <label>Type: 
            <select id="node-type">
                <option value="paper">Paper</option>
                <option value="question">Question</option>
                <option value="source">Source</option>
            </select>
        </label><br>
        <label>Label: <input type="text" id="node-label"></label><br>
        <button type="button" onclick="addNode()">Add Node</button>
    </form>
    
    <form id="add-edge-form">
        <h2>Add an Edge</h2>
        <label>Source Node ID: <input type="text" id="source-id"></label><br>
        <label>Target Node ID: <input type="text" id="target-id"></label><br>
        <button type="button" onclick="addEdge()">Add Edge</button>
    </form>
    
    <form id="lit-review-form">
        <h2>Literature Review</h2>
        <div id="pages">
            <div class="page" id="page-1">
                <h3>Page 1</h3>
                <label>Author(s): <input type="text" class="authors"></label><br>
                <label>Title: <input type="text" class="title"></label><br>
                <label>Journal/Source: <input type="text" class="journal"></label><br>
                <label>Year: <input type="text" class="year"></label><br>
                <label>DOI/URL: <input type="text" class="doi"></label><br>
                <label>Summary: <textarea class="summary"></textarea></label><br>
                <label>Findings: <textarea class="findings"></textarea></label><br>
                <label>Relevance: <textarea class="relevance"></textarea></label><br>
                <label>Personal Notes: <textarea class="notes"></textarea></label><br>
            </div>
        </div>
        <button type="button" onclick="addPage()">Add Page</button>
        <button type="button" onclick="generatePDF()">Download as PDF</button>
    </form>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.4.0/jspdf.umd.min.js"></script>
    <script src="https://unpkg.com/cytoscape/dist/cytoscape.min.js"></script>
    <script src="scripts.js"></script>
</body>
</html>
2. JavaScript for Adding Pages and Generating PDFs
JavaScript (scripts.js)
javascript
Copy code
document.addEventListener('DOMContentLoaded', function () {
    const cy = cytoscape({
        container: document.getElementById('network'),
        style: [
            {
                selector: 'node',
                style: {
                    'background-color': '#666',
                    'label': 'data(label)'
                }
            },
            {
                selector: 'edge',
                style: {
                    'width': 3,
                    'line-color': '#ccc',
                    'target-arrow-color': '#ccc',
                    'target-arrow-shape': 'triangle'
                }
            }
        ],
        elements: [],
        layout: {
            name: 'grid',
            rows: 1
        }
    });

    window.addNode = function () {
        const type = document.getElementById('node-type').value;
        const label = document.getElementById('node-label').value;
        cy.add({
            group: 'nodes',
            data: { id: label, label: `${type}: ${label}` }
        });
        cy.layout({ name: 'grid', rows: 1 }).run();
    };

    window.addEdge = function () {
        const source = document.getElementById('source-id').value;
        const target = document.getElementById('target-id').value;
        cy.add({
            group: 'edges',
            data: { id: `${source}-${target}`, source: source, target: target }
        });
        cy.layout({ name: 'grid', rows: 1 }).run();
    };

    let pageCount = 1;

    window.addPage = function () {
        pageCount++;
        const pagesDiv = document.getElementById('pages');
        const newPage = document.createElement('div');
        newPage.className = 'page';
        newPage.id = `page-${pageCount}`;
        newPage.innerHTML = `
            <h3>Page ${pageCount}</h3>
            <label>Author(s): <input type="text" class="authors"></label><br>
            <label>Title: <input type="text" class="title"></label><br>
            <label>Journal/Source: <input type="text" class="journal"></label><br>
            <label>Year: <input type="text" class="year"></label><br>
            <label>DOI/URL: <input type="text" class="doi"></label><br>
            <label>Summary: <textarea class="summary"></textarea></label><br>
            <label>Findings: <textarea class="findings"></textarea></label><br>
            <label>Relevance: <textarea class="relevance"></textarea></label><br>
            <label>Personal Notes: <textarea class="notes"></textarea></label><br>
        `;
        pagesDiv.appendChild(newPage);
    };

    window.generatePDF = function () {
        const { jsPDF } = window.jspdf;
        const doc = new jsPDF();

        for (let i = 1; i <= pageCount; i++) {
            if (i > 1) doc.addPage();
            const page = document.getElementById(`page-${i}`);
            const authors = page.querySelector('.authors').value;
            const title = page.querySelector('.title').value;
            const journal = page.querySelector('.journal').value;
            const year = page.querySelector('.year').value;
            const doi = page.querySelector('.doi').value;
            const summary = page.querySelector('.summary').value;
            const findings = page.querySelector('.findings').value;
            const relevance = page.querySelector('.relevance').value;
            const notes = page.querySelector('.notes').value;

            doc.setFontSize(12);
            doc.text(`Page ${i}`, 10, 10);
            doc.text(`Authors: ${authors}`, 10, 20);
            doc.text(`Title: ${title}`, 10, 30);
            doc.text(`Journal/Source: ${journal}`, 10, 40);
            doc.text(`Year: ${year}`, 10, 50);
            doc.text(`DOI/URL: ${doi}`, 10, 60);
            doc.text(`Summary: ${summary}`, 10, 70);
            doc.text(`Findings: ${findings}`, 10, 100);
            doc.text(`Relevance: ${relevance}`, 10, 130);
            doc.text(`Personal Notes: ${notes}`, 10, 160);
        }

        doc.save('literature_review.pdf');
    };
});
3. Combining Multiple Literature Reviews
To combine multiple reviews into one extended PDF, you can extend the generatePDF function to accept multiple sets of reviews and append them sequentially.

JavaScript (scripts.js)
javascript
Copy code
document.addEventListener('DOMContentLoaded', function () {
    const cy = cytoscape({
        container: document.getElementById('network'),
        style: [
            {
                selector: 'node',
                style: {
                    'background-color': '#666',
                    'label': 'data(label)'
                }
            },
            {
                selector: 'edge',
                style: {
                    'width': 3,
                    'line-color': '#ccc',
                    'target-arrow-color': '#ccc',
                    'target-arrow-shape': 'triangle'
                }
            }
        ],
        elements: [],
        layout: {
            name: 'grid',
            rows: 1
        }
    });

    window.addNode = function () {
        const type = document.getElementById('node-type').value;
        const label = document.getElementById('node-label').value;
        cy.add({
            group: 'nodes',
            data: { id: label, label: `${type}: ${label}` }
        });
        cy.layout({ name: 'grid', rows: 1 }).run();
    };

    window.addEdge = function () {
        const source = document.getElementById('source-id').value;
        const target = document.getElementById('target-id').value;
        cy.add({
            group: 'edges',
            data: { id: `${source}-${target}`, source: source, target: target }
        });
        cy.layout({ name: 'grid', rows: 1 }).run();
    };

    let pageCount = 1;

    window.addPage = function () {
        pageCount++;
        const pagesDiv = document.getElementById('pages');
        const newPage = document.createElement('div');
        newPage.className = 'page';
        newPage.id = `page-${pageCount}`;
        newPage.innerHTML = `
            <h3>Page ${pageCount}</h3>
            <label>Author(s): <input type="text" class="authors"></label><br>
            <label>Title: <input type="text" class="title"></label><br>
            <label>Journal/Source: <input type="text" class="journal"></label><br>
            <label>Year: <input type="text" class="year"></label><br>
            <label>DOI/URL: <input type="text" class="doi"></label><br>
            <label>Summary: <textarea class="summary"></textarea></label><br>
            <label>Findings: <textarea class="findings"></textarea></label><br>
            <label>Relevance: <textarea class="relevance"></textarea></label><br>
            <label>Personal Notes: <textarea class="notes"></textarea></label><br>
        `;
        pagesDiv.appendChild(newPage);
    };

    window.generatePDF = function () {
        const { jsPDF } = window.jspdf;
        const doc = new jsPDF();

        for (let i = 1; i <= pageCount; i++) {
            if (i > 1) doc.addPage();
            const page = document.getElementById(`page-${i}`);
            const authors = page.querySelector('.authors').value;
            const title = page.querySelector('.title').value;
            const journal = page.querySelector('.journal').value;
            const year = page.querySelector('.year').value;
            const doi = page.querySelector('.doi').value;
            const summary = page.querySelector('.summary').value;
            const findings = page.querySelector('.findings').value;
            const relevance = page.querySelector('.relevance').value;
            const notes = page.querySelector('.notes').value;

            doc.setFontSize(12);
            doc.text(`Page ${i}`, 10, 10);
            doc.text(`Authors: ${authors}`, 10, 20);
            doc.text(`Title: ${title}`, 10, 30);
            doc.text(`Journal/Source: ${journal}`, 10, 40);
            doc.text(`Year: ${year}`, 10, 50);
            doc.text(`DOI/URL: ${doi}`, 10, 60);
            doc.text(`Summary: ${summary}`, 10, 70);
            doc.text(`Findings: ${findings}`, 10, 100);
            doc.text(`Relevance: ${relevance}`, 10, 130);
            doc.text(`Personal Notes: ${notes}`, 10, 160);
        }

        doc.save('literature_review.pdf');
    };

    window.combinePDFs = function (pdfFiles) {
        const { jsPDF } = window.jspdf;
        const mergedDoc = new jsPDF();

        pdfFiles.forEach((file, index) => {
            const reader = new FileReader();
            reader.onload = function (event) {
                const existingPdfBytes = event.target.result;
                const pdf = new jsPDF();
                pdf.load(existingPdfBytes);
                const numPages = pdf.getNumberOfPages();

                for (let i = 1; i <= numPages; i++) {
                    if (index > 0 || i > 1) mergedDoc.addPage();
                    const pageContent = pdf.getPageContent(i);
                    mergedDoc.addPageContent(pageContent);
                }

                if (index === pdfFiles.length - 1) {
                    mergedDoc.save('combined_literature_review.pdf');
                }
            };
            reader.readAsArrayBuffer(file);
        });
    };
});
4. Additional HTML for Combining PDFs
Add an input for selecting multiple PDF files to combine.

HTML (index.html)
html
Copy code
<form id="combine-pdf-form">
    <h2>Combine Literature Reviews</h2>
    <label>Select PDF files: <input type="file" id="pdf-files" multiple></label><br>
    <button type="button" onclick="combinePDFs(document.getElementById('pdf-files').files)">Combine PDFs</button>
</form>
With these enhancements, you can create a comprehensive tool for literature reviews that supports multi-page reviews and the ability to combine multiple reviews into one extended PDF document, hosted on GitHub Pages.







