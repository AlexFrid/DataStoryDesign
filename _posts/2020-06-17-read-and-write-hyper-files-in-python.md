---
keywords: fastai
description: A simple way to go between Tableau hyper files and Pandas DataFrames
title: Read and write hyper files in Python
toc: false
badges: false
comments: false
image: images/header_images/tableau-to-python.png
categories: [Python, Tableau]
nb_path: _notebooks/2020-06-17-read-and-write-hyper-files-in-python.ipynb
layout: notebook
---

<!--
#################################################
### THIS FILE WAS AUTOGENERATED! DO NOT EDIT! ###
#################################################
# file to edit: _notebooks/2020-06-17-read-and-write-hyper-files-in-python.ipynb
-->

<div class="container" id="notebook-container">
        
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Tableau-Hyper-IO">Tableau Hyper IO<a class="anchor-link" href="#Tableau-Hyper-IO"> </a></h1><p>A simple wrapper for the <a href="https://help.tableau.com/current/api/hyper_api/en-us/index.html">Tableau Hyper API</a></p>
<p><a href="https://github.com/AlexFrid/tableauhyperio">Click here to see the code on GitHub</a></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Why-was-this-made?">Why was this made?<a class="anchor-link" href="#Why-was-this-made?"> </a></h2><p>For a project I was working on I needed to read hyper files.
I searched if a package already existed and found only the <a href="https://pypi.org/project/pandleau/">pandleau</a> package,
which only writes to hyper files but does not read them and also uses the older extract 2.0 API.
Since I couldn't find any other package that met my needs I decided to make one myself, which has been a good learning experience.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Installation">Installation<a class="anchor-link" href="#Installation"> </a></h2><p>You can install tableauhyperio using pip:</p>
<div class="highlight"><pre><span></span>pip install tableauhyperio
</pre></div>
<p>This will also try downloading the Tableau hyper API, tqdm, pandas.</p>
<h2 id="Example-usage">Example usage<a class="anchor-link" href="#Example-usage"> </a></h2><div class="highlight"><pre><span></span><span class="kn">import</span> <span class="nn">tableauhyperio</span> <span class="k">as</span> <span class="nn">hio</span>

<span class="c1"># Reading a regular hyper file</span>
<span class="n">df</span> <span class="o">=</span> <span class="n">hio</span><span class="o">.</span><span class="n">read_hyper</span><span class="p">(</span><span class="s2">&quot;example.hyper&quot;</span><span class="p">)</span>

<span class="c1"># Reading a hyper file with a custom schema</span>
<span class="n">df</span> <span class="o">=</span> <span class="n">hio</span><span class="o">.</span><span class="n">read_hyper</span><span class="p">(</span><span class="s2">&quot;example.hyper&quot;</span><span class="p">,</span> <span class="s2">&quot;my_schema&quot;</span><span class="p">)</span>

<span class="c1"># Writing a regular hyper file</span>
<span class="n">hio</span><span class="o">.</span><span class="n">to_hyper</span><span class="p">(</span><span class="n">df</span><span class="p">,</span> <span class="s2">&quot;example_output.hyper&quot;</span><span class="p">)</span>

<span class="c1"># Writing a hyper file with a custom schema and custom table name</span>
<span class="n">hio</span><span class="o">.</span><span class="n">to_hyper</span><span class="p">(</span><span class="n">df</span><span class="p">,</span> <span class="s2">&quot;example_output.hyper&quot;</span><span class="p">,</span> <span class="s2">&quot;my_schema&quot;</span><span class="p">,</span> <span class="s2">&quot;my_table&quot;</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>
</div>
 
