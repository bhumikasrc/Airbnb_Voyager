<script src="https://mozilla.github.io/pdf.js/build/pdf.js"></script>

<div>
    <canvas id="pdfViewer" style="border:1px solid black;"></canvas>
</div>
<script>
    // Specify the path to your PDF file
    var pdfPath = 'EDA_Final_Presentation.pdf';
    var canvas = document.getElementById('pdfViewer');
    pdfjsLib.getDocument(pdfPath).then(function (pdf) {
        // Fetch the first page
        pdf.getPage(1).then(function (page) {
            // Set the canvas dimensions
            var viewport = page.getViewport({ scale: 1.5 });
            canvas.width = viewport.width;
            canvas.height = viewport.height;
            var context = canvas.getContext('2d');
            page.render({ canvasContext: context, viewport: viewport });
        });
    });
</script>
