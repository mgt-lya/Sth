---


---

<h2 id="if68">IF68</h2>
<p>The image filter project of group 68.</p>
<h2 id="description">Description</h2>
<p>A lightweight and customizable image filtering tool built with C++ and OpenCV. It applies various spatial domain filters to process images efficiently.</p>
<h2 id="main-features">Main Features</h2>
<h3 id="multiple-spatial-filters">Multiple spatial filters</h3>
<p>Currently there are 4 filters which all operate in spatial domain as this <a href="https://dsp.stackexchange.com/questions/74358/spatial-domain-vs-frequency-domain-filtering-of-an-image-which-one-is-better">StackExchange thread</a> suggested, which are:</p>
<ol>
<li><a href="https://en.wikipedia.org/wiki/Gaussian_filter">Gaussian Blur</a>: To smooth the image linearly by Gaussian kernal, effectively reduce the high frequency noise.</li>
<li><a href="https://en.wikipedia.org/wiki/Low-pass_filter">Low Pass</a>: To blur the image by supressing high frequency components (rapid transition regions, e.g. edges) and preserved low-frequency components(smooth regions, e.g. shades).</li>
<li><a href="https://en.wikipedia.org/wiki/High-pass_filter">High Pass</a>: Opposite to Low pass, to suppress low frequency components, and enhancing rapid transition regions.</li>
<li><a href="https://de.wikipedia.org/wiki/Laplace-Filter">Laplace Filter</a>: To highlight rapid transition regions by second order derivative operator.</li>
</ol>
<h3 id="customizable-input--output">Customizable input &amp; output</h3>
<ol>
<li>Various input image formats (e.g. PNG, JPG and similar formats) are accepted.</li>
<li>Input and output image paths can be specified anywhere on the system.</li>
<li>Output image name and format can be user-defined.</li>
</ol>
<h2 id="structure">Structure</h2>
<pre><code>IF68/
├── README.md # Descriptive file
└── sprint1.cpp # Main code
</code></pre>
<p>Input and output image path can be specified later in prompt window during the run time.</p>
<h2 id="prerequisite">Prerequisite</h2>
<p>C++ 11 or above.<br>
OpenCV installed.</p>
<ul>
<li>We use OpenCV 3.4.8, configured through system environment variables and Visual Studio.</li>
<li>For stability reasons, we recommend running the project with a lower OpenCV version.  See <a href="https://github.com/opencv/opencv%20/t%20_new">official sources</a></li>
</ul>
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
<pre class=" language-bash"><code class="prism  language-bash">g++ -std<span class="token operator">=</span>c++11 -o filter code.cpp <span class="token variable"><span class="token variable">`</span>pkg-config --cflags --libs opencv4<span class="token variable">`</span></span> -Wall -Wextra
</code></pre>
<ol start="3">
<li>
<p>The code runs interactively with prompts:</p>
<p>a. Run the code:</p>
<pre class=" language-bash"><code class="prism  language-bash">./filter
</code></pre>
<p>b. Choose an input image from any local path, and optionally specify an output path &amp; output file name</p>
<pre class=" language-bash"><code class="prism  language-bash">Enter input image path:<span class="token punctuation">(</span>e.g. E:/images/input.png<span class="token punctuation">)</span>
Enter output image name/path <span class="token punctuation">(</span>e.g.  simply save as result.png or E:/images/result.png<span class="token punctuation">)</span>: 
</code></pre>
<h4 id="note">Note:</h4>
<p>If no output location is given, the processed image will be written to the project directory by default.</p>
<p>c. Choose which filter to use:</p>
<pre class=" language-bash"><code class="prism  language-bash">Enter filter <span class="token punctuation">(</span>gaussian / lowpass / highpass / laplace<span class="token punctuation">)</span>:
</code></pre>
<p>d. Then specify the kernel size:</p>
<pre class=" language-bash"><code class="prism  language-bash">Enter kernel size <span class="token punctuation">(</span>odd number like 3, 5, 9, 15<span class="token punctuation">)</span>:
</code></pre>
<h4 id="note-1">Note:</h4>
<p>Larger kernel size leads to smoother output image; and smaller kernel size will highlights more details.</p>
</li>
</ol>
<h2 id="demo">Demo</h2>
<p>Basic Gaussian Blur with kernel size of 15:</p>
<pre class=" language-bash"><code class="prism  language-bash">$ ./filter
Enter input image path: ./photo.jpg
Enter output image name/path: ./blurred_photo.png
Enter filter <span class="token punctuation">(</span>gaussian / lowpass / highpass / laplace<span class="token punctuation">)</span>: gaussian
Enter kernel size <span class="token punctuation">(</span>odd number like 3, 5, 9, 15<span class="token punctuation">)</span>: 15
Saved filtered image to ./blurred_photo.png
</code></pre>
<h3 id="prompt-window-illustration">Prompt window illustration</h3>
<p><img src="https://github.com/mgt-lya/Sth/blob/master/5bb4ab14c9793defc12c3845d263c07a.png" alt="enter image description here"></p>
<h3 id="result-visualization">Result visualization</h3>
<p>Original image:<br>
<img src="https://github.com/mgt-lya/Sth/blob/master/1406e670f6bf842d4d603c3d60306a7f.png" alt="enter image description here"></p>
<p>Result image:<br>
<img src="https://github.com/mgt-lya/Sth/blob/master/d3936590481f3ea5357317e92ae70df3.png" alt="enter image description here"><br>
The result image is more smoother than the original image, as edges and reflections get blurred, which corresponds to the expected effect of Gaussian Blur filter.</p>
<h2 id="license">License</h2>
<p>MIT License</p>

