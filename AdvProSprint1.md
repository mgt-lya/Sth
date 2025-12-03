---


---

<h2 id="if68">IF68</h2>
<p>The image filter project of group 68.</p>
<h2 id="description">Description</h2>
<p>A lightweight and customizable image filtering tool built with C++ and OpenCV. It applies various spatial domain filters to process images efficiently.</p>
<h2 id="feature">Feature</h2>
<p>Currently there are 4 filters which all operate in spatial domain as this <a href="https://dsp.stackexchange.com/questions/74358/spatial-domain-vs-frequency-domain-filtering-of-an-image-which-one-is-better">StackExchange thread</a> suggested:</p>
<p>-<a href="https://en.wikipedia.org/wiki/Gaussian_filter">Gaussian Blur</a>: Smoothing the image linearly by Gaussian kernal, effectively reduce the high frequency noise.</p>
<p>-<a href="https://en.wikipedia.org/wiki/Low-pass_filter">Low Pass</a>: Blurred the image by supressing high frequency components (rapid transition regions, e.g. edges) and preserved low-frequency components(smooth regions, e.g. shades).</p>
<p>-<a href="https://en.wikipedia.org/wiki/High-pass_filter">High Pass</a>: Opposite to Low pass, supressing low frequency components, and enhancing rapid transition regions.</p>
<p>-<a href="https://de.wikipedia.org/wiki/Laplace-Filter">Laplace Filter</a>: Highlight rapid transition regions by second order derivative operator.</p>
<h2 id="structure">Structure</h2>
<pre><code>
IF68/
├── README.md # Descriptive file
├── code.cpp # Main code
├── input.png # Input image
└── output.png # Output image

</code></pre>
<h2 id="prerequisite">Prerequisite</h2>
<p>C++ 11 or above.<br>
OpenCV installed.</p>
<h2 id="utilization">Utilization</h2>
<ol>
<li>Clone the repository</li>
</ol>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">git</span> clone https://gitlab.lrz.de/advprog2025/68
<span class="token function">cd</span> if68
</code></pre>
<ol start="2">
<li>Compile source code</li>
</ol>
<pre class=" language-bash"><code class="prism  language-bash">g++ -std<span class="token operator">=</span>c++11 -o filter code.cpp <span class="token variable"><span class="token variable">`</span>pkg-config --cflags --libs opencv4<span class="token variable">`</span></span>
</code></pre>
<ol start="3">
<li>Prepare image.</li>
</ol>
<p>Please Rename the input image as <code>input.png</code> and make sure <code>input.png</code> is at the same directory as <code>code.cpp</code></p>
<ol start="4">
<li>
<p>The code runs interactively with prompts:</p>
<p>Run the code:</p>
<pre class=" language-bash"><code class="prism  language-bash">./filter
</code></pre>
<p>Choose which filter to use:</p>
<pre class=" language-bash"><code class="prism  language-bash">Enter filter <span class="token punctuation">(</span>gaussian / lowpass / highpass / laplace<span class="token punctuation">)</span>:
</code></pre>
<p>Then specify the kernel size:</p>
<pre class=" language-bash"><code class="prism  language-bash">Enter kernel size <span class="token punctuation">(</span>odd number like 3, 5, 9, 15<span class="token punctuation">)</span>:
</code></pre>
</li>
</ol>
<p>Notes:</p>
<ol>
<li>Larger kernel size leads to smoother output image; and smaller kernel size will highlights more details.</li>
<li>Output image number will be “output.png” by default.</li>
</ol>
<h2 id="license">License</h2>
<p>MIT License</p>

