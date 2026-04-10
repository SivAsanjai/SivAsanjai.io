---
layout: page
title: My Thesis
permalink: /thesis/
---

# On Random Walks and Exploration on Unknown Networks

<div class="thesis-header" style="margin: 2rem 0 1rem 0;">
  <a href="{{ '/assets/pdfs/thesis.pdf' | relative_url }}" download class="btn-download" style="display: inline-block; padding: 0.75rem 1.5rem; background-color: #0066cc; color: white; text-decoration: none; border-radius: 5px; font-weight: 500; margin-right: 1rem;">
    📥 Download PDF
  </a>
  <a href="{{ '/assets/pdfs/thesis.pdf' | relative_url }}" target="_blank" class="btn-view" style="display: inline-block; padding: 0.75rem 1.5rem; background-color: #6c757d; color: white; text-decoration: none; border-radius: 5px; font-weight: 500;">
    🔗 Open in New Tab
  </a>
</div>

<!-- Embedded PDF Viewer -->
<div class="pdf-viewer-container" style="margin: 2rem 0; border: 1px solid #dee2e6; border-radius: 8px; overflow: hidden; box-shadow: 0 2px 4px rgba(0,0,0,0.1);">
  <object 
  data="{{ '/assets/pdfs/thesis.pdf' | relative_url }}" 
  type="application/pdf"
  style="width:100%; height:800px;">
  
  <!-- Fallback for browsers that don't support object tag -->
  <iframe 
    src="{{ '/assets/pdfs/thesis.pdf' | relative_url }}"
    style="width:100%; height:800px; border:none;">
  </iframe>
  
  <!-- Final fallback -->
  <div style="padding: 2rem; text-align: center; background-color: #f8f9fa;">
    <p style="margin-bottom: 1rem;">Unable to display PDF in browser.</p>
    <a href="{{ '/assets/pdfs/thesis.pdf' | relative_url }}" download style="color: #0066cc; font-weight: 500;">
      Click here to download the thesis
    </a>
  </div>
</object>
</div>

## Abstract

Explored how probabilistic processes, particularly random walks, behave on regular graphs, and how these insights inform the analysis of randomized algorithms like randomized depth-first search (rDFS).

Focusing on toroidal grid graphs, examined the cost of exploration through an electrical network lens, leveraging resistance-based formulations and exploiting the block-circulant structure of the graph Laplacian.

Enabled efficient computation via the 2D Discrete Fourier Transform and revealed connections to lattice Green's functions, with asymptotic behavior of the form $\frac{1}{2\pi} \ln n + c + O(1)$.

## Citation

```bibtex
@thesis{sanjai2025randomwalks,
  author = {Siva Sanjai G A},
  title = {On Random Walks and Exploration on Unknown Networks},
  year = {2025},
  school = {Ashoka University},
  type = {Undergraduate Thesis}
}
```

---

*For questions or comments about this work, please contact me at sivasanjaiga@gmail.com*