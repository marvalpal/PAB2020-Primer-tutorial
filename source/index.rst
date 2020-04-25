<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
  "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">


<html xmlns="http://www.w3.org/1999/xhtml">
  <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
    
    <title>1. Restructured Text (reST) and Sphinx CheatSheet &mdash; Sphinx and RST syntax guide (0.9.3)</title>
    
    <link rel="stylesheet" href="_static/software.css" type="text/css" />
    <link rel="stylesheet" href="_static/pygments.css" type="text/css" />
    
    <script type="text/javascript">
      var DOCUMENTATION_OPTIONS = {
        URL_ROOT:    './',
        VERSION:     '0.9',
        COLLAPSE_INDEX: false,
        FILE_SUFFIX: '.html',
        HAS_SOURCE:  true
      };
    </script>
    <script type="text/javascript" src="_static/jquery.js"></script>
    <script type="text/javascript" src="_static/underscore.js"></script>
    <script type="text/javascript" src="_static/doctools.js"></script>
    <script type="text/javascript" src="_static/copybutton.js"></script>
    <link rel="top" title="Sphinx and RST syntax guide (0.9.3)" href="index.html" />
    <link rel="next" title="2. Example on how to document your Python docstrings" href="docstring_python.html" />
    <link rel="prev" title="2. QuickStart" href="quickstart.html" />


<script type="text/javascript" src="https://apis.google.com/js/plusone.js"></script>

    <script type="text/javascript">
      var _gaq = _gaq || [];
      _gaq.push(['_setAccount', 'UA-4372857-1)']);
      _gaq.push(['_trackPageview']);
    </script>



  </head>
  <body>
    <div class="header-wrapper">
        <div class="header">
            <h1><a href="index.html">Sphinx and RST syntax guide (0.9.3)</a>
            </h1>
            <div class="rel">
                  <a href="quickstart.html" 
                    title="2. QuickStart"
                 accesskey="P">previous</a> |
                  <a href="docstring_python.html" 
                    title="2. Example on how to document your Python docstrings"
                 accesskey="N">next</a> |
                  <a href="py-modindex.html" 
                    title="Python Module Index"
                 >modules</a> |
                  <a href="genindex.html" 
                    title="General Index"
                 accesskey="I">index</a>
            </div>
       </div>
    </div>

    <div class="content-wrapper">
      <div class="content">
        <div class="document">
            
            
      <div class="documentwrapper">
        <div class="bodywrapper">
          <div class="body">
            
  <div class="section" id="restructured-text-rest-and-sphinx-cheatsheet">
<span id="rst-tutorial"></span><h1><a class="toc-backref" href="#id4">1. Restructured Text (reST) and Sphinx CheatSheet</a><a class="headerlink" href="#restructured-text-rest-and-sphinx-cheatsheet" title="Permalink to this headline">¶</a></h1>
<div class="topic">
<p class="topic-title first">Overview</p>
<p>This page describes some of the RST and Sphinx syntax. It is based on resource found at <a class="reference external" href="http://sphinx.pocoo.org/rest.html">Sphinx</a> , <a class="reference external" href="http://docutils.sourceforge.net/rst.html">Docutils</a> and more generally software documentation written with Sphinx.</p>
<p>This is not an exhaustive description but it should allow you to start and create already nice documentation.</p>
<table class="docutils field-list" frame="void" rules="none">
<col class="field-name" />
<col class="field-body" />
<tbody valign="top">
<tr class="field-odd field"><th class="field-name">Date:</th><td class="field-body">August 14, 2014</td>
</tr>
<tr class="field-even field"><th class="field-name">Author:</th><td class="field-body"><strong>Thomas Cokelaer</strong></td>
</tr>
</tbody>
</table>
</div>
<div class="contents topic" id="contents">
<p class="topic-title first">Contents</p>
<ul class="simple">
<li><a class="reference internal" href="#restructured-text-rest-and-sphinx-cheatsheet" id="id4">Restructured Text (reST) and Sphinx CheatSheet</a><ul>
<li><a class="reference internal" href="#introduction" id="id5">Introduction</a></li>
<li><a class="reference internal" href="#text-formatting" id="id6">Text Formatting</a><ul>
<li><a class="reference internal" href="#inline-markup-and-special-characters-e-g-bold-italic-verbatim" id="id7">Inline markup and special characters (e.g., bold, italic, verbatim)</a></li>
<li><a class="reference internal" href="#headings" id="id8">Headings</a></li>
<li><a class="reference internal" href="#internal-and-external-links" id="id9">Internal and External Links</a></li>
<li><a class="reference internal" href="#list-and-bullets" id="id10">List and bullets</a></li>
</ul>
</li>
<li><a class="reference internal" href="#what-are-directives" id="id11">What are directives</a></li>
<li><a class="reference internal" href="#inserting-code-and-literal-blocks" id="id12">Inserting code and Literal blocks</a><ul>
<li><a class="reference internal" href="#how-to-include-simple-code" id="id13">How to include simple code</a></li>
<li><a class="reference internal" href="#code-block-directive" id="id14">code-block directive</a></li>
<li><a class="reference internal" href="#include-code-with-the-literalinclude-directive" id="id15">Include code with the literalinclude directive</a></li>
</ul>
</li>
<li><a class="reference internal" href="#tables" id="id16">Tables</a><ul>
<li><a class="reference internal" href="#simple-tables" id="id17">Simple tables</a></li>
<li><a class="reference internal" href="#multicells-tables-first-method" id="id18">Multicells tables, first method</a></li>
<li><a class="reference internal" href="#multicells-table-second-method" id="id19">Multicells table, second method</a></li>
<li><a class="reference internal" href="#the-tabularcolumns-directive" id="id20">The tabularcolumns directive</a></li>
<li><a class="reference internal" href="#the-csv-table-directive" id="id21">The csv-table directive</a></li>
</ul>
</li>
<li><a class="reference internal" href="#include-other-rst-files-with-the-toctree-directive" id="id22">Include other RST files with the toctree directive</a></li>
<li><a class="reference internal" href="#python-software" id="id23">Python software</a><ul>
<li><a class="reference internal" href="#auto-document-your-python-code" id="id24">Auto-document your python code</a></li>
<li><a class="reference internal" href="#python-docstrings" id="id25">python docstrings</a></li>
</ul>
</li>
<li><a class="reference internal" href="#images-and-figures" id="id26">Images and figures</a><ul>
<li><a class="reference internal" href="#include-images" id="id27">Include Images</a></li>
<li><a class="reference internal" href="#include-a-figure" id="id28">Include a Figure</a></li>
</ul>
</li>
<li><a class="reference internal" href="#boxes" id="id29">Boxes</a><ul>
<li><a class="reference internal" href="#colored-boxes-note-seealso-todo-and-warnings" id="id30">Colored boxes: note, seealso, todo and warnings</a></li>
<li><a class="reference internal" href="#topic-directive" id="id31">Topic directive</a></li>
<li><a class="reference internal" href="#sidebar-directive" id="id32">Sidebar directive</a></li>
</ul>
</li>
<li><a class="reference internal" href="#others" id="id33">Others</a><ul>
<li><a class="reference internal" href="#comments" id="id34">Comments</a></li>
<li><a class="reference internal" href="#substitutions" id="id35">Substitutions</a></li>
<li><a class="reference internal" href="#glossary-centered-index-download-and-field-list" id="id36">glossary, centered, index, download and field list</a></li>
<li><a class="reference internal" href="#footnote" id="id37">Footnote</a></li>
<li><a class="reference internal" href="#citations" id="id38">Citations</a></li>
<li><a class="reference internal" href="#more-about-aliases" id="id39">More about aliases</a></li>
<li><a class="reference internal" href="#intersphinx" id="id40">Intersphinx</a></li>
<li><a class="reference internal" href="#file-wide-metadata" id="id41">file-wide metadata</a></li>
<li><a class="reference internal" href="#metainformation" id="id42">metainformation</a></li>
<li><a class="reference internal" href="#contents-directives" id="id43">contents directives</a></li>
</ul>
</li>
<li><a class="reference internal" href="#useful-extensions" id="id44">Useful extensions</a><ul>
<li><a class="reference internal" href="#pngmath-maths-and-equations-with-latex" id="id45">pngmath: Maths and Equations with LaTeX</a></li>
<li><a class="reference internal" href="#todo-extension" id="id46">TODO extension</a></li>
<li><a class="reference internal" href="#copybutton" id="id47">copybutton</a></li>
</ul>
</li>
</ul>
</li>
</ul>
</div>
<div class="section" id="introduction">
<h2><a class="toc-backref" href="#id5">1.1. Introduction</a><a class="headerlink" href="#introduction" title="Permalink to this headline">¶</a></h2>
<p>The reStructuredText (RST) syntax provides an easy-to-read, what-you-see-is-what-you-get plaintext markup syntax and parser system. However, you need to be very precise and stick to some strict rules:</p>
<blockquote>
<div><ul class="simple">
<li>like Python, RST syntax is sensitive to indentation !</li>
<li>RST requires blank lines between paragraphs</li>
</ul>
</div></blockquote>
<p>This entire document is written with the RST syntax. In the right sidebar, you should find a link <strong>show source</strong>, which shows the RST source code.</p>
</div>
<div class="section" id="text-formatting">
<h2><a class="toc-backref" href="#id6">1.2. Text Formatting</a><a class="headerlink" href="#text-formatting" title="Permalink to this headline">¶</a></h2>
<div class="section" id="inline-markup-and-special-characters-e-g-bold-italic-verbatim">
<h3><a class="toc-backref" href="#id7">1.2.1. Inline markup and special characters (e.g., bold, italic, verbatim)</a><a class="headerlink" href="#inline-markup-and-special-characters-e-g-bold-italic-verbatim" title="Permalink to this headline">¶</a></h3>
<p>There are a few special characters used to format text. The special character <tt class="docutils literal"><span class="pre">*</span></tt> is used to defined bold and italic text as shown in the table below. The backquote character <tt class="docutils literal"><span class="pre">`</span></tt> is another special character used to create links to internal or external web pages as you will see in section <a class="reference internal" href="#internal-and-external-links">Internal and External Links</a>.</p>
<table border="1" class="docutils">
<colgroup>
<col width="15%" />
<col width="45%" />
<col width="40%" />
</colgroup>
<thead valign="bottom">
<tr class="row-odd"><th class="head">usage</th>
<th class="head">syntax</th>
<th class="head">HTML rendering</th>
</tr>
</thead>
<tbody valign="top">
<tr class="row-even"><td>italic</td>
<td><cite>*italic*</cite></td>
<td><em>italic</em></td>
</tr>
<tr class="row-odd"><td>bold</td>
<td><cite>**bold**</cite></td>
<td><strong>bold</strong></td>
</tr>
<tr class="row-even"><td>link</td>
<td><tt class="docutils literal"><span class="pre">`python</span> <span class="pre">&lt;www.python.org&gt;`_</span></tt></td>
<td><a class="reference external" href="www.python.org">python</a></td>
</tr>
<tr class="row-odd"><td>verbatim</td>
<td><tt class="docutils literal"><span class="pre">``*``</span></tt></td>
<td><tt class="docutils literal"><span class="pre">*</span></tt></td>
</tr>
</tbody>
</table>
<p>The double backquote is used to enter in verbatim mode, which can be used as the escaping character.
There are some restrictions about the <tt class="docutils literal"><span class="pre">*</span></tt> and <tt class="docutils literal"><span class="pre">``</span></tt> syntax. They</p>
<blockquote>
<div><ul class="simple">
<li>cannot not be nested,</li>
<li>content may not start or end with whitespace: <tt class="docutils literal"><span class="pre">*</span> <span class="pre">text*</span></tt> is wrong,</li>
<li>it must be separated from surrounding text by non-word characters like a space.</li>
</ul>
</div></blockquote>
<p>The use of backslash is a work around to second previous restrictions about whitespaces in the following case:</p>
<blockquote>
<div><ul class="simple">
<li><tt class="docutils literal"><span class="pre">this</span> <span class="pre">is</span> <span class="pre">a</span> <span class="pre">*longish*</span> <span class="pre">paragraph</span></tt> is correct and gives <em>longish</em>.</li>
<li><tt class="docutils literal"><span class="pre">this</span> <span class="pre">is</span> <span class="pre">a</span> <span class="pre">long*ish*</span> <span class="pre">paragraph</span></tt> is not interpreted as expected. You
should use <tt class="docutils literal"><span class="pre">this</span> <span class="pre">is</span> <span class="pre">a</span> <span class="pre">long\</span> <span class="pre">*ish*</span> <span class="pre">paragraph</span></tt> to obtain long<em>ish</em> paragraph</li>
</ul>
</div></blockquote>
<p>In Python docstrings it will be necessary to escape any backslash characters so that they actually reach reStructuredText. The simplest way to do this is to use raw strings by adding the letter <tt class="docutils literal"><span class="pre">r</span></tt> in front of the docstring.</p>
<table border="1" class="docutils">
<colgroup>
<col width="54%" />
<col width="46%" />
</colgroup>
<thead valign="bottom">
<tr class="row-odd"><th class="head">Python string</th>
<th class="head">Typical result</th>
</tr>
</thead>
<tbody valign="top">
<tr class="row-even"><td><tt class="docutils literal"><span class="pre">r&quot;&quot;&quot;\*escape*</span> <span class="pre">\`with`</span> <span class="pre">&quot;\\&quot;&quot;&quot;&quot;</span></tt></td>
<td><tt class="docutils literal"><span class="pre">*escape*</span> <span class="pre">`with`</span> <span class="pre">&quot;\&quot;</span></tt></td>
</tr>
<tr class="row-odd"><td><tt class="docutils literal"><span class="pre">&quot;&quot;&quot;\\*escape*</span> <span class="pre">\\`with`</span> <span class="pre">&quot;\\\\&quot;&quot;&quot;&quot;</span></tt></td>
<td><tt class="docutils literal"><span class="pre">*escape*</span> <span class="pre">`with`</span> <span class="pre">&quot;\&quot;</span></tt></td>
</tr>
<tr class="row-even"><td><tt class="docutils literal"><span class="pre">&quot;&quot;&quot;\*escape*</span> <span class="pre">\`with`</span> <span class="pre">&quot;\\&quot;&quot;&quot;&quot;</span></tt></td>
<td><tt class="docutils literal"><span class="pre">escape</span> <span class="pre">with</span> <span class="pre">&quot;&quot;</span></tt></td>
</tr>
</tbody>
</table>
</div>
<div class="section" id="headings">
<h3><a class="toc-backref" href="#id8">1.2.2. Headings</a><a class="headerlink" href="#headings" title="Permalink to this headline">¶</a></h3>
<p>In order to write a title, you can either underline it or under and overline it. The following examples are correct titles.</p>
<div class="highlight-rest"><div class="highlight"><pre><span class="gh">*****</span>
<span class="gh">Title</span>
<span class="gh">*****</span>

<span class="gh">subtitle</span>
<span class="gh">########</span>

<span class="gh">subsubtitle</span>
<span class="gh">**********************</span>
and so on
</pre></div>
</div>
<p>Two rules:</p>
<blockquote>
<div><ul class="simple">
<li>If under and overline are used, their length must be identical</li>
<li>The length of the underline must be at least as long as the title itself</li>
</ul>
</div></blockquote>
<p>Normally, there are no heading levels assigned to certain characters as the
structure is determined from the succession of headings. However, it is better to stick to the same convention throughout a project. For instance:</p>
<ul class="simple">
<li><cite>#</cite> with overline, for parts</li>
<li><cite>*</cite> with overline, for chapters</li>
<li><cite>=</cite>, for sections</li>
<li><cite>-</cite>, for subsections</li>
<li><cite>^</cite>, for subsubsections</li>
<li><cite>&#8220;</cite>, for paragraphs</li>
</ul>
</div>
<div class="section" id="internal-and-external-links">
<h3><a class="toc-backref" href="#id9">1.2.3. Internal and External Links</a><a class="headerlink" href="#internal-and-external-links" title="Permalink to this headline">¶</a></h3>
<dl class="docutils">
<dt>In Sphinx, you have 3 type of links:</dt>
<dd><ol class="first last arabic simple">
<li>External links (http-like)</li>
<li>Implicit links to title</li>
<li>Explicit links to user-defined label (e.g., to refer to external titles).</li>
</ol>
</dd>
</dl>
<div class="section" id="external-links">
<h4>1.2.3.1. External links<a class="headerlink" href="#external-links" title="Permalink to this headline">¶</a></h4>
<p>If you want to create a link to a website, the syntax is</p>
<div class="highlight-python"><div class="highlight"><pre>`&lt;http://www.python.org/&gt;`_
</pre></div>
</div>
<p>which appear as <a class="reference external" href="http://www.python.org/">http://www.python.org/</a> . Note the underscore after the final single quote. Since the full name of the link is not always simple or meaningful, you can specify a label (note the space between the label and link name):</p>
<div class="highlight-python"><div class="highlight"><pre>`Python &lt;http://www.python.org/&gt;`_
</pre></div>
</div>
<p>The rendering is now: <a class="reference external" href="http://www.python.org/">Python</a>.</p>
<div class="admonition note">
<p class="first admonition-title">Note</p>
<p class="last">If you have an underscore within the label/name, you got to escape it with a &#8216;\&#8217; character.</p>
</div>
</div>
<div class="section" id="implicit-links-to-titles">
<span id="implicit"></span><h4>1.2.3.2. Implicit Links to Titles<a class="headerlink" href="#implicit-links-to-titles" title="Permalink to this headline">¶</a></h4>
<p>All titles are considered as hyperlinks. A link to a title is just its name within quotes and a final underscore:</p>
<div class="highlight-python"><div class="highlight"><pre>`Internal and External links`_
</pre></div>
</div>
<p>This syntax works only if the title and link are within the same RST file.
If this is not the case, then you need to create a label before the title and refer to this new link explicitly, as explained in <a class="reference internal" href="#explicit-links">Explicit Links</a> section.</p>
</div>
<div class="section" id="explicit-links">
<h4>1.2.3.3. Explicit Links<a class="headerlink" href="#explicit-links" title="Permalink to this headline">¶</a></h4>
<p>You can create explicit links within your RST files. For instance, this document has a label at the top called <tt class="docutils literal"><span class="pre">rst_tutorial</span></tt>, which is specified by typing:</p>
<div class="highlight-python"><div class="highlight"><pre>.. _rst_tutorial:
</pre></div>
</div>
<p>You can refer to this label using two different methods. The first one is:</p>
<div class="highlight-python"><div class="highlight"><pre><span class="n">rst_tutorial_</span>
</pre></div>
</div>
<p>The second method use the <tt class="docutils literal"><span class="pre">ref</span></tt> role as follows:</p>
<div class="highlight-python"><div class="highlight"><pre>:ref:`rst_tutorial`
</pre></div>
</div>
<p>With the first method, the link appears as <a class="reference internal" href="#rst-tutorial">rst_tutorial</a>, whereas the second method use the first title&#8217;s name found after the link. Here, the second method would appear as <a class="reference internal" href="#rst-tutorial"><em>Restructured Text (reST) and Sphinx CheatSheet</em></a>.</p>
<p>Note that the second method is compulsary if the link is to be found in an external RST file. For instance, the introduction page is an external page with a link called <tt class="docutils literal"><span class="pre">introduction</span></tt> at the top of the page. You can jump there by writting <tt class="docutils literal"><span class="pre">:ref:`introduction`</span></tt>, which appears as: <a class="reference internal" href="introduction.html#introduction"><em>Why Sphinx and for which users ?</em></a>.</p>
<div class="admonition note">
<p class="first admonition-title">Note</p>
<p class="last">Note that if you use the <tt class="docutils literal"><span class="pre">ref</span></tt> role, the final underscore is not required anymore.</p>
</div>
</div>
</div>
<div class="section" id="list-and-bullets">
<h3><a class="toc-backref" href="#id10">1.2.4. List and bullets</a><a class="headerlink" href="#list-and-bullets" title="Permalink to this headline">¶</a></h3>
<p>The following code:</p>
<div class="highlight-python"><div class="highlight"><pre>* This is a bulleted list.
* It has two items, the second
  item uses two lines. (note the indentation)

1. This is a numbered list.
2. It has two items too.

#. This is a numbered list.
#. It has two items too.
</pre></div>
</div>
<p>gives:</p>
<ul class="simple">
<li>This is a bulleted list.</li>
<li>It has two items, the second
item uses two lines. (note the indentation)</li>
</ul>
<ol class="arabic simple">
<li>This is a numbered list.</li>
<li>It has two items too.</li>
<li>This is a numbered list.</li>
<li>It has two items too.</li>
</ol>
<div class="admonition note">
<p class="first admonition-title">Note</p>
<p class="last">if two lists are separated by a blanck line only, then the two lists are not differentiated as you can see above.</p>
</div>
</div>
</div>
<div class="section" id="what-are-directives">
<h2><a class="toc-backref" href="#id11">1.3. What are directives</a><a class="headerlink" href="#what-are-directives" title="Permalink to this headline">¶</a></h2>
<p>Sphinx and the RST syntax provides directives to include formatted text. As an example, let us consider the <strong>code-block</strong> syntax. It allows to insert code (here HTML) within your document:</p>
<div class="highlight-python"><div class="highlight"><pre>.. code-block:: html
    :linenos:

    &lt;h1&gt;code block example&lt;/h1&gt;
</pre></div>
</div>
<p>Its rendering is:</p>
<div class="highlight-html"><table class="highlighttable"><tr><td class="linenos"><div class="linenodiv"><pre>1</pre></div></td><td class="code"><div class="highlight"><pre> <span class="nt">&lt;h1&gt;</span>code block example<span class="nt">&lt;/h1&gt;</span>
</pre></div>
</td></tr></table></div>
<p>Here, <strong>code-block</strong> is the name of the directive. <strong>html</strong> is an argument telling that the code is in HTML format, <strong>lineos</strong> is an option telling to insert line number and finally after a blank line is the text to include.</p>
<p>Note that options are tabulated.</p>
</div>
<div class="section" id="inserting-code-and-literal-blocks">
<h2><a class="toc-backref" href="#id12">1.4. Inserting code and Literal blocks</a><a class="headerlink" href="#inserting-code-and-literal-blocks" title="Permalink to this headline">¶</a></h2>
<div class="section" id="how-to-include-simple-code">
<h3><a class="toc-backref" href="#id13">1.4.1. How to include simple code</a><a class="headerlink" href="#how-to-include-simple-code" title="Permalink to this headline">¶</a></h3>
<p>This easiest way to insert literal code blocks is to end a paragraph with the special marker made of a double coulumn <cite>::</cite>. Then, the literal block must be indented:</p>
<div class="highlight-python"><div class="highlight"><pre>This is a simple example::

    import math
    print &#39;import done&#39;
</pre></div>
</div>
<p>or:</p>
<div class="highlight-python"><div class="highlight"><pre>This is a simple example:
::

    import math
    print &#39;import done&#39;
</pre></div>
</div>
<p>gives:</p>
<p>This is a simple example:</p>
<div class="highlight-python"><div class="highlight"><pre><span class="kn">import</span> <span class="nn">math</span>
<span class="k">print</span> <span class="s">&#39;import done&#39;</span>
</pre></div>
</div>
</div>
<div class="section" id="code-block-directive">
<h3><a class="toc-backref" href="#id14">1.4.2. code-block directive</a><a class="headerlink" href="#code-block-directive" title="Permalink to this headline">¶</a></h3>
<p>By default the syntax of the language is Python, but you can specify the language using the <strong>code-block</strong> directive as follows:</p>
<div class="highlight-python"><div class="highlight"><pre>.. code-block:: html
   :linenos:

   &lt;h1&gt;code block example&lt;/h1&gt;
</pre></div>
</div>
<p>produces</p>
<div class="highlight-html"><table class="highlighttable"><tr><td class="linenos"><div class="linenodiv"><pre>1</pre></div></td><td class="code"><div class="highlight"><pre><span class="nt">&lt;h1&gt;</span>code block example<span class="nt">&lt;/h1&gt;</span>
</pre></div>
</td></tr></table></div>
</div>
<div class="section" id="include-code-with-the-literalinclude-directive">
<h3><a class="toc-backref" href="#id15">1.4.3. Include code with the literalinclude directive</a><a class="headerlink" href="#include-code-with-the-literalinclude-directive" title="Permalink to this headline">¶</a></h3>
<p>Then, it is also possible to include the contents of a file as follows:</p>
<div class="highlight-rest"><div class="highlight"><pre><span class="p">..</span> <span class="ow">literalinclude</span><span class="p">::</span> filename
    <span class="nc">:linenos:</span>
    <span class="nc">:language:</span> <span class="nf">python</span>
    <span class="nc">:lines:</span> <span class="nf">1, 3-5</span>
    <span class="nc">:start-after:</span> <span class="nf">3</span>
    <span class="nc">:end-before:</span> <span class="nf">5</span>
</pre></div>
</div>
<p>For instance, the <tt class="docutils literal"><span class="pre">sample.py</span></tt> file contents can be printed:</p>
<div class="highlight-python"><table class="highlighttable"><tr><td class="linenos"><div class="linenodiv"><pre> 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16</pre></div></td><td class="code"><div class="highlight"><pre><span class="sd">&quot;&quot;&quot; here is a dummy documentation&quot;&quot;&quot;</span>
<span class="kn">import</span> <span class="nn">os</span>


<span class="k">def</span> <span class="nf">square</span><span class="p">(</span><span class="n">a</span><span class="p">):</span>
    <span class="sd">&quot;&quot;&quot;short description of the function square</span>

<span class="sd">    longish explanation: returns the square of a: :math:`a^2`</span>

<span class="sd">    :param a: an input argument</span>

<span class="sd">    :returns: a*a</span>
<span class="sd">    &quot;&quot;&quot;</span>
    <span class="k">return</span> <span class="n">a</span><span class="o">*</span><span class="n">a</span>

<span class="k">assert</span> <span class="mi">4</span> <span class="o">==</span> <span class="n">square</span><span class="p">(</span><span class="mi">2</span><span class="p">)</span>
</pre></div>
</td></tr></table></div>
</div>
</div>
<div class="section" id="tables">
<h2><a class="toc-backref" href="#id16">1.5. Tables</a><a class="headerlink" href="#tables" title="Permalink to this headline">¶</a></h2>
<p>There are several ways to write tables. Use standard reStructuredText tables as explained here. They work fine in HTML output, however, there are some gotchas when using tables for LaTeX output.</p>
<p>The rendering of the table depends on the CSS/HTML style, not on sphinx itself.</p>
<div class="section" id="simple-tables">
<h3><a class="toc-backref" href="#id17">1.5.1. Simple tables</a><a class="headerlink" href="#simple-tables" title="Permalink to this headline">¶</a></h3>
<p>Simple tables can be written as follows:</p>
<div class="highlight-python"><div class="highlight"><pre>+---------+---------+-----------+
| 1       |  2      |  3        |
+---------+---------+-----------+
</pre></div>
</div>
<p>which gives:</p>
<table border="1" class="docutils">
<colgroup>
<col width="31%" />
<col width="31%" />
<col width="38%" />
</colgroup>
<tbody valign="top">
<tr class="row-odd"><td>1</td>
<td>2</td>
<td>3</td>
</tr>
</tbody>
</table>
<p>Size of the cells can be adjusted as follows:</p>
<div class="highlight-python"><div class="highlight"><pre>+---------------------+---------+---+
|1                    |        2| 3 |
+---------------------+---------+---+
</pre></div>
</div>
<p>renders as follows:</p>
<table border="1" class="docutils">
<colgroup>
<col width="64%" />
<col width="27%" />
<col width="9%" />
</colgroup>
<tbody valign="top">
<tr class="row-odd"><td>1</td>
<td>2</td>
<td>3</td>
</tr>
</tbody>
</table>
<p>This syntax is quite limited, especially for multi cells/columns.</p>
</div>
<div class="section" id="multicells-tables-first-method">
<h3><a class="toc-backref" href="#id18">1.5.2. Multicells tables, first method</a><a class="headerlink" href="#multicells-tables-first-method" title="Permalink to this headline">¶</a></h3>
<p>A first method is the following syntax:</p>
<div class="highlight-python"><div class="highlight"><pre>+------------+------------+-----------+
| Header 1   | Header 2   | Header 3  |
+============+============+===========+
| body row 1 | column 2   | column 3  |
+------------+------------+-----------+
| body row 2 | Cells may span columns.|
+------------+------------+-----------+
| body row 3 | Cells may  | - Cells   |
+------------+ span rows. | - contain |
| body row 4 |            | - blocks. |
+------------+------------+-----------+
</pre></div>
</div>
<p>gives:</p>
<table border="1" class="docutils">
<colgroup>
<col width="34%" />
<col width="34%" />
<col width="31%" />
</colgroup>
<thead valign="bottom">
<tr class="row-odd"><th class="head">Header 1</th>
<th class="head">Header 2</th>
<th class="head">Header 3</th>
</tr>
</thead>
<tbody valign="top">
<tr class="row-even"><td>body row 1</td>
<td>column 2</td>
<td>column 3</td>
</tr>
<tr class="row-odd"><td>body row 2</td>
<td colspan="2">Cells may span columns.</td>
</tr>
<tr class="row-even"><td>body row 3</td>
<td rowspan="2">Cells may
span rows.</td>
<td rowspan="2"><ul class="first last simple">
<li>Cells</li>
<li>contain</li>
<li>blocks.</li>
</ul>
</td>
</tr>
<tr class="row-odd"><td>body row 4</td>
</tr>
</tbody>
</table>
</div>
<div class="section" id="multicells-table-second-method">
<h3><a class="toc-backref" href="#id19">1.5.3. Multicells table, second method</a><a class="headerlink" href="#multicells-table-second-method" title="Permalink to this headline">¶</a></h3>
<p>The previous syntax can be simplified:</p>
<div class="highlight-python"><div class="highlight"><pre>=====  =====  ======
   Inputs     Output
------------  ------
  A      B    A or B
=====  =====  ======
False  False  False
True   False  True
=====  =====  ======
</pre></div>
</div>
<p>gives:</p>
<table border="1" class="docutils">
<colgroup>
<col width="31%" />
<col width="31%" />
<col width="38%" />
</colgroup>
<thead valign="bottom">
<tr class="row-odd"><th class="head" colspan="2">Inputs</th>
<th class="head">Output</th>
</tr>
<tr class="row-even"><th class="head">A</th>
<th class="head">B</th>
<th class="head">A or B</th>
</tr>
</thead>
<tbody valign="top">
<tr class="row-odd"><td>False</td>
<td>False</td>
<td>False</td>
</tr>
<tr class="row-even"><td>True</td>
<td>False</td>
<td>True</td>
</tr>
</tbody>
</table>
<div class="admonition note">
<p class="first admonition-title">Note</p>
<p class="last">table and latex documents are not yet compatible in sphinx, and you should therefore precede them with the a special directive (.. htmlonly::)</p>
</div>
</div>
<div class="section" id="the-tabularcolumns-directive">
<h3><a class="toc-backref" href="#id20">1.5.4. The tabularcolumns directive</a><a class="headerlink" href="#the-tabularcolumns-directive" title="Permalink to this headline">¶</a></h3>
<p>The previous examples work fine in HTML output, however there are some gotchas when using tables in LaTeX: the column width is hard to determine correctly automatically. For this reason, the following directive exists:</p>
<div class="highlight-python"><div class="highlight"><pre>.. tabularcolumns:: column spec
</pre></div>
</div>
<p>This directive gives a “column spec” for the next table occurring in the source file. It can have values like:</p>
<div class="highlight-python"><div class="highlight"><pre>|l|l|l|
</pre></div>
</div>
<p>which means three left-adjusted (LaTeX syntax). By default, Sphinx uses a table layout with L for every column. This code:</p>
<div class="highlight-python"><div class="highlight"><pre>.. tabularcolumns:: |l|c|p{5cm}|

+--------------+---+-----------+
|  simple text | 2 | 3         |
+--------------+---+-----------+
</pre></div>
</div>
<p>gives</p>
<table border="1" class="docutils">
<colgroup>
<col width="38%" />
<col width="32%" />
<col width="30%" />
</colgroup>
<thead valign="bottom">
<tr class="row-odd"><th class="head">title</th>
<th class="head">&nbsp;</th>
<th class="head">&nbsp;</th>
</tr>
</thead>
<tbody valign="top">
<tr class="row-even"><td>simple text</td>
<td>2</td>
<td>3</td>
</tr>
</tbody>
</table>
</div>
<div class="section" id="the-csv-table-directive">
<h3><a class="toc-backref" href="#id21">1.5.5. The csv-table directive</a><a class="headerlink" href="#the-csv-table-directive" title="Permalink to this headline">¶</a></h3>
<p>Finally, a convenient way to create table is the usage of CSV-like syntax:</p>
<div class="highlight-python"><div class="highlight"><pre>.. csv-table:: a title
   :header: &quot;name&quot;, &quot;firstname&quot;, &quot;age&quot;
   :widths: 20, 20, 10

   &quot;Smith&quot;, &quot;John&quot;, 40
   &quot;Smith&quot;, &quot;John, Junior&quot;, 20
</pre></div>
</div>
<p>that is rendered as follows:</p>
<table border="1" class="docutils">
<caption>a title</caption>
<colgroup>
<col width="40%" />
<col width="40%" />
<col width="20%" />
</colgroup>
<thead valign="bottom">
<tr class="row-odd"><th class="head">name</th>
<th class="head">firstname</th>
<th class="head">age</th>
</tr>
</thead>
<tbody valign="top">
<tr class="row-even"><td>Smith</td>
<td>John</td>
<td>40</td>
</tr>
<tr class="row-odd"><td>Smith</td>
<td>John, Junior</td>
<td>20</td>
</tr>
</tbody>
</table>
</div>
</div>
<div class="section" id="include-other-rst-files-with-the-toctree-directive">
<h2><a class="toc-backref" href="#id22">1.6. Include other RST files with the toctree directive</a><a class="headerlink" href="#include-other-rst-files-with-the-toctree-directive" title="Permalink to this headline">¶</a></h2>
<p>Sooner or later you will want to structure your project documentation by having several RST files. The <strong>toctree</strong> directive allows you to insert other files within a RST file. The reason to use this directive is that RST does not have facilities to interconnect several documents, or split documents into multiple output files. The <strong>toctree</strong> directive looks like</p>
<div class="highlight-rest"><div class="highlight"><pre><span class="p">..</span> <span class="ow">toctree</span><span class="p">::</span>
    <span class="nc">:maxdepth:</span> <span class="nf">2</span>
    <span class="nc">:numbered:</span>
    <span class="nc">:titlesonly:</span>
    <span class="nc">:glob:</span>
    <span class="nc">:hidden:</span>

    intro.rst
    chapter1.rst
    chapter2.rst
</pre></div>
</div>
<p>It includes 3 RST files and shows a TOC that includes the title found in the RST documents.</p>
<p>Here are a few notes about the different options</p>
<ul class="simple">
<li><strong>maxdepth</strong> is used to indicates the depth of the tree.</li>
<li><strong>numbered</strong> adds relevant section numbers.</li>
<li><strong>titlesonly</strong> adds only the main title of each document</li>
<li><strong>glob</strong> can be used to indicate that * and ? characters are used to indicate patterns.</li>
<li><strong>hidden</strong> hides the toctree. It can be used to include files that do not need to be shown (e.g. a bibliography).</li>
</ul>
<p>The glob option works as follows:</p>
<div class="highlight-rest"><div class="highlight"><pre><span class="p">..</span> <span class="ow">toctree</span><span class="p">::</span>
    <span class="nc">:glob:</span>

    intro*
    recipe/*
    *
</pre></div>
</div>
<p>Note also that the title that appear in the toctree are the file&#8217;s title. You may want to change this behaviour by changing the toctree as follows:</p>
<div class="highlight-rest"><div class="highlight"><pre><span class="p">..</span> <span class="ow">toctree</span><span class="p">::</span>
    <span class="nc">:glob:</span>

    Chapter1 description &lt;chapter1&gt;
</pre></div>
</div>
<p>So that the title of this section is more meaningful.</p>
</div>
<div class="section" id="python-software">
<h2><a class="toc-backref" href="#id23">1.7. Python software</a><a class="headerlink" href="#python-software" title="Permalink to this headline">¶</a></h2>
<p>Sphinx can be used to create generic documentation, or software documentation dedicated to Python, but not only (can C, C++, ...). Here, we&#8217;ll focus on Python itself.</p>
<div class="section" id="auto-document-your-python-code">
<h3><a class="toc-backref" href="#id24">1.7.1. Auto-document your python code</a><a class="headerlink" href="#auto-document-your-python-code" title="Permalink to this headline">¶</a></h3>
<p>Let us suppose you have a python file called <em>sample.py</em> with a function called <em>square</em>. The function&#8217;s code is :</p>
<div class="highlight-python"><table class="highlighttable"><tr><td class="linenos"><div class="linenodiv"><pre> 1
 2
 3
 4
 5
 6
 7
 8
 9
10</pre></div></td><td class="code"><div class="highlight"><pre><span class="k">def</span> <span class="nf">square</span><span class="p">(</span><span class="n">a</span><span class="p">):</span>
    <span class="sd">&quot;&quot;&quot;short description of the function square</span>

<span class="sd">    longish explanation: returns the square of a: :math:`a^2`</span>

<span class="sd">    :param a: an input argument</span>

<span class="sd">    :returns: a*a</span>
<span class="sd">    &quot;&quot;&quot;</span>
    <span class="k">return</span> <span class="n">a</span><span class="o">*</span><span class="n">a</span>
</pre></div>
</td></tr></table></div>
<p>Using the <strong>autofunction</strong> :</p>
<div class="highlight-rest"><div class="highlight"><pre><span class="p">..</span> <span class="ow">currentmodule</span><span class="p">::</span> sample
<span class="p">..</span> <span class="ow">autofunction</span><span class="p">::</span> square
</pre></div>
</div>
<p>Gives</p>
<dl class="function">
<dt id="sample.square">
<tt class="descname">square</tt><big>(</big><em>a</em><big>)</big><a class="reference internal" href="_modules/sample.html#square"><span class="viewcode-link">[source]</span></a><a class="headerlink" href="#sample.square" title="Permalink to this definition">¶</a></dt>
<dd><p>short description of the function square</p>
<p>longish explanation: returns the square of a: <img class="math" src="_images/math/4c77d9b404c32574fb927ad22d79d05b4970f279.png" alt="a^2"/></p>
<table class="docutils field-list" frame="void" rules="none">
<col class="field-name" />
<col class="field-body" />
<tbody valign="top">
<tr class="field-odd field"><th class="field-name">Parameters:</th><td class="field-body"><strong>a</strong> &#8211; an input argument</td>
</tr>
<tr class="field-even field"><th class="field-name">Returns:</th><td class="field-body">a*a</td>
</tr>
</tbody>
</table>
</dd></dl>

<p>Here, we need to specify in which module should be found the function <strong>square</strong>, hence the <tt class="docutils literal"><span class="pre">..</span> <span class="pre">module::sample</span></tt> directive. You can use <strong>autoclass</strong> and <strong>automodule</strong> in the same way.</p>
<p>Using the <strong>module</strong> directive also creates an index (see top right of this page) so it is worth specifying more information using platform and synopsis options for example:</p>
<div class="highlight-rest"><div class="highlight"><pre><span class="p">..</span> <span class="ow">module</span><span class="p">::</span> sample
    <span class="nc">:platform:</span> <span class="nf">Unix, Windows</span>
    <span class="nc">:synopsis:</span> <span class="nf">sample of documented python code</span>
</pre></div>
</div>
<p>The results will be shown in a module section (link in top right panel).</p>
<span class="target" id="module-sample"></span><div class="admonition note">
<p class="first admonition-title">Note</p>
<p class="last">the directive module should be use only once for a given module.</p>
</div>
<div class="admonition warning">
<p class="first admonition-title">Warning</p>
<p class="last">the python code must be in the PYTHONPATH.</p>
</div>
<div class="admonition seealso">
<p class="first admonition-title">See also</p>
<p class="last"><a class="reference external" href="http://sphinx.pocoo.org/markup/desc.html">http://sphinx.pocoo.org/markup/desc.html</a></p>
</div>
</div>
<div class="section" id="python-docstrings">
<h3><a class="toc-backref" href="#id25">1.7.2. python docstrings</a><a class="headerlink" href="#python-docstrings" title="Permalink to this headline">¶</a></h3>
<p>In a python shell, when you type a statement, it is preceeded by the &gt;&gt;&gt; sign.
The results are printed without it. For instance:</p>
<div class="highlight-python"><div class="highlight"><pre><span class="gp">&gt;&gt;&gt; </span><span class="n">a</span> <span class="o">=</span> <span class="mi">1</span>
<span class="go">1</span>
</pre></div>
</div>
<p>If you want to copy and paste this code, you will get errors since the &gt;&gt;&gt; sign is not part of the syntax. There is a javascript solution to hide it in the <a class="reference internal" href="#useful-extensions">Useful extensions</a> section.</p>
</div>
</div>
<div class="section" id="images-and-figures">
<h2><a class="toc-backref" href="#id26">1.8. Images and figures</a><a class="headerlink" href="#images-and-figures" title="Permalink to this headline">¶</a></h2>
<div class="section" id="include-images">
<h3><a class="toc-backref" href="#id27">1.8.1. Include Images</a><a class="headerlink" href="#include-images" title="Permalink to this headline">¶</a></h3>
<p>Use:</p>
<div class="highlight-python"><div class="highlight"><pre>.. image:: stars.jpg
    :width: 200px
    :align: center
    :height: 100px
    :alt: alternate text
</pre></div>
</div>
<p>to put an image</p>
<a class="reference internal image-reference" href="_images/stars.jpg"><img alt="alternate text" class="align-center" src="_images/stars.jpg" style="width: 200px; height: 100px;" /></a>
</div>
<div class="section" id="include-a-figure">
<h3><a class="toc-backref" href="#id28">1.8.2. Include a Figure</a><a class="headerlink" href="#include-a-figure" title="Permalink to this headline">¶</a></h3>
<div class="highlight-python"><div class="highlight"><pre>.. figure:: stars.jpg
    :width: 200px
    :align: center
    :height: 100px
    :alt: alternate text
    :figclass: align-center

    figure are like images but with a caption

    and whatever else youwish to add

    .. code-block:: python

        import image
</pre></div>
</div>
<p>gives</p>
<div class="align-center figure">
<a class="reference internal image-reference" href="_images/stars.jpg"><img alt="alternate text" src="_images/stars.jpg" style="width: 200px; height: 100px;" /></a>
<p class="caption">figure are like images but with a caption</p>
<div class="legend">
<p>and whatever else youwish to add</p>
<div class="highlight-python"><div class="highlight"><pre><span class="kn">import</span> <span class="nn">image</span>
</pre></div>
</div>
</div>
</div>
<p>The option <strong>figclass</strong> is a CSS class that can be tuned for the final HTML rendering.</p>
</div>
</div>
<div class="section" id="boxes">
<h2><a class="toc-backref" href="#id29">1.9. Boxes</a><a class="headerlink" href="#boxes" title="Permalink to this headline">¶</a></h2>
<div class="section" id="colored-boxes-note-seealso-todo-and-warnings">
<h3><a class="toc-backref" href="#id30">1.9.1. Colored boxes: note, seealso, todo and warnings</a><a class="headerlink" href="#colored-boxes-note-seealso-todo-and-warnings" title="Permalink to this headline">¶</a></h3>
<p>There are simple directives like <strong>seealso</strong> that creates nice colored boxes:</p>
<div class="admonition seealso">
<p class="first admonition-title">See also</p>
<p class="last">This is a simple <strong>seealso</strong> note.</p>
</div>
<p>created using:</p>
<div class="highlight-python"><div class="highlight"><pre>.. seealso:: This is a simple **seealso** note.
</pre></div>
</div>
<p>You have also the <strong>note</strong> directive:</p>
<div class="admonition note">
<p class="first admonition-title">Note</p>
<p class="last">This is a <strong>note</strong> box.</p>
</div>
<p>with</p>
<div class="highlight-python"><div class="highlight"><pre>.. note::  This is a **note** box.
</pre></div>
</div>
<p>and the warning directive:</p>
<div class="admonition warning">
<p class="first admonition-title">Warning</p>
<p class="last">note the space between the directive and the text</p>
</div>
<p>generated with:</p>
<div class="highlight-python"><div class="highlight"><pre>.. warning:: note the space between the directive and the text
</pre></div>
</div>
<p>There is another  <strong>todo</strong> directive but requires an extension. See
<a class="reference internal" href="#useful-extensions">Useful extensions</a></p>
</div>
<div class="section" id="topic-directive">
<h3><a class="toc-backref" href="#id31">1.9.2. Topic directive</a><a class="headerlink" href="#topic-directive" title="Permalink to this headline">¶</a></h3>
<p>A <strong>Topic</strong> directive  allows to write a title and a text together within a box similarly to the <strong>note</strong> directive.</p>
<p>This code:</p>
<div class="highlight-python"><div class="highlight"><pre>.. topic:: Your Topic Title

    Subsequent indented lines comprise
    the body of the topic, and are
    interpreted as body elements.
</pre></div>
</div>
<p>gives</p>
<div class="topic">
<p class="topic-title first">Your Topic Title</p>
<p>Subsequent indented lines comprise
the body of the topic, and are
interpreted as body elements.</p>
</div>
</div>
<div class="section" id="sidebar-directive">
<h3><a class="toc-backref" href="#id32">1.9.3. Sidebar directive</a><a class="headerlink" href="#sidebar-directive" title="Permalink to this headline">¶</a></h3>
<p>It is possible to create sidebar using the following code:</p>
<div class="highlight-python"><div class="highlight"><pre>.. sidebar:: Sidebar Title
    :subtitle: Optional Sidebar Subtitle

    Subsequent indented lines comprise
    the body of the sidebar, and are
    interpreted as body elements.
</pre></div>
</div>
<div class="sidebar">
<p class="first sidebar-title">Sidebar Title</p>
<p class="sidebar-subtitle">Optional Sidebar Subtitle</p>
<p class="last">Subsequent indented lines comprise
the body of the sidebar, and are
interpreted as body elements.</p>
</div>
</div>
</div>
<div class="section" id="others">
<h2><a class="toc-backref" href="#id33">1.10. Others</a><a class="headerlink" href="#others" title="Permalink to this headline">¶</a></h2>
<div class="section" id="comments">
<h3><a class="toc-backref" href="#id34">1.10.1. Comments</a><a class="headerlink" href="#comments" title="Permalink to this headline">¶</a></h3>
<p>Comments can be made by adding two dots at the beginning of a line as follows:</p>
<div class="highlight-python"><div class="highlight"><pre>.. comments
</pre></div>
</div>
</div>
<div class="section" id="substitutions">
<h3><a class="toc-backref" href="#id35">1.10.2. Substitutions</a><a class="headerlink" href="#substitutions" title="Permalink to this headline">¶</a></h3>
<p>Substitutions  are defined as follows:</p>
<div class="highlight-python"><div class="highlight"><pre>.. _Python: http://www.python.org/
</pre></div>
</div>
<p>and to refer to it, use the same syntax as for the internal links: just insert the alias in the text (e.g., <tt class="docutils literal"><span class="pre">Python_</span></tt>,  which appears as <a href="#id48"><span class="problematic" id="id49">Python_</span></a> ).</p>
<p>A second method is as follows:</p>
<div class="highlight-python"><div class="highlight"><pre>.. |longtext| replace:: this is a very very long text to include
</pre></div>
</div>
<p>and then insert  <tt class="docutils literal"><span class="pre">|longtext|</span></tt> wherever required.</p>
</div>
<div class="section" id="glossary-centered-index-download-and-field-list">
<h3><a class="toc-backref" href="#id36">1.10.3. glossary, centered, index, download and field list</a><a class="headerlink" href="#glossary-centered-index-download-and-field-list" title="Permalink to this headline">¶</a></h3>
<div class="section" id="field-list">
<h4>1.10.3.1. Field list<a class="headerlink" href="#field-list" title="Permalink to this headline">¶</a></h4>
<table class="docutils field-list" frame="void" rules="none">
<col class="field-name" />
<col class="field-body" />
<tbody valign="top">
<tr class="field-odd field"><th class="field-name">Whatever:</th><td class="field-body">this is handy to create new field and the following text is indented</td>
</tr>
</tbody>
</table>
<div class="highlight-python"><div class="highlight"><pre>:Whatever: this is handy to create new field
</pre></div>
</div>
</div>
<div class="section" id="glossary">
<h4>1.10.3.2. glossary<a class="headerlink" href="#glossary" title="Permalink to this headline">¶</a></h4>
<div class="highlight-python"><div class="highlight"><pre>.. glossary::
     apical
        at the top of the plant.
</pre></div>
</div>
<p>gives</p>
<dl class="glossary docutils">
<dt id="term-apical">apical</dt>
<dd>at the top of the plant.</dd>
</dl>
</div>
<div class="section" id="index">
<h4>1.10.3.3. index<a class="headerlink" href="#index" title="Permalink to this headline">¶</a></h4>
<div class="highlight-python"><div class="highlight"><pre>.. index::
</pre></div>
</div>
</div>
<div class="section" id="download">
<h4>1.10.3.4. download<a class="headerlink" href="#download" title="Permalink to this headline">¶</a></h4>
<div class="highlight-python"><div class="highlight"><pre>:download:`download samplet.py &lt;sample.py&gt;`
</pre></div>
</div>
<p>gives <a class="reference download internal" href="_downloads/sample.py"><tt class="xref download docutils literal"><span class="pre">download</span> <span class="pre">sample.py</span></tt></a></p>
</div>
<div class="section" id="hlist-directive">
<h4>1.10.3.5. hlist directive<a class="headerlink" href="#hlist-directive" title="Permalink to this headline">¶</a></h4>
<p>hlist can be use to set a list on several columns.</p>
<dl class="directive">
<dt id="directive-hlist">
<tt class="descname">.. hlist::</tt><tt class="descclassname"> </tt><a class="headerlink" href="#directive-hlist" title="Permalink to this definition">¶</a></dt>
<dd><div class="highlight-python"><div class="highlight"><pre>.. hlist::
    :columns: 3

    * first item
    * second item
    * 3d item
    * 4th item
    * 5th item
</pre></div>
</div>
<table class="hlist"><tr><td><ul class="simple">
<li>first item</li>
<li>second item</li>
</ul>
</td><td><ul class="simple">
<li>3d item</li>
<li>4th item</li>
</ul>
</td><td><ul class="simple">
<li>5th item</li>
</ul>
</td></tr></table>
</dd></dl>

</div>
</div>
<div class="section" id="footnote">
<h3><a class="toc-backref" href="#id37">1.10.4. Footnote</a><a class="headerlink" href="#footnote" title="Permalink to this headline">¶</a></h3>
<p>For footnotes, use <tt class="docutils literal"><span class="pre">[#name]_</span></tt> to mark the footnote location, and add the
footnote body at the bottom of the document after a “Footnotes” rubric
heading, like so:</p>
<div class="highlight-python"><div class="highlight"><pre>Some text that requires a footnote [#f1]_ .

.. rubric:: Footnotes

.. [#f1] Text of the first footnote.
</pre></div>
</div>
<p>You can also explicitly number the footnotes (<tt class="docutils literal"><span class="pre">[1]_</span></tt>) or use auto-numbered
footnotes without names (<tt class="docutils literal"><span class="pre">[#]_</span></tt>). Here is an example <a class="footnote-reference" href="#footnote1" id="id2">[1]</a>.</p>
</div>
<div class="section" id="citations">
<h3><a class="toc-backref" href="#id38">1.10.5. Citations</a><a class="headerlink" href="#citations" title="Permalink to this headline">¶</a></h3>
<p>Citation references, like <a class="reference internal" href="#cit2002" id="id3">[CIT2002]</a> may be defined at the bottom of the page:</p>
<div class="highlight-python"><div class="highlight"><pre>.. [CIT2002] A citation
          (as often used in journals).
</pre></div>
</div>
<p>and called as follows:</p>
<div class="highlight-python"><div class="highlight"><pre>[CIT2002]_
</pre></div>
</div>
</div>
<div class="section" id="more-about-aliases">
<h3><a class="toc-backref" href="#id39">1.10.6. More about aliases</a><a class="headerlink" href="#more-about-aliases" title="Permalink to this headline">¶</a></h3>
<p>Directives can be used within aliases:</p>
<div class="highlight-python"><div class="highlight"><pre>.. |logo| image:: stars.jpg
    :width: 20pt
    :height: 20pt
</pre></div>
</div>
<p>Using this image alias, you can insert it easily in the text <cite>|logo|</cite>, like this <a class="reference internal" href="_images/stars.jpg"><img alt="logo" class="align-middle" src="_images/stars.jpg" style="width: 20pt; height: 20pt;" /></a>. This is especially useful when dealing with complicated code. For instance, in order to include 2 images within a table do as follows:</p>
<div class="highlight-python"><div class="highlight"><pre>+---------+---------+-----------+
| |logo|  | |logo|  | |longtext||
+---------+---------+-----------+
</pre></div>
</div>
<table border="1" class="docutils">
<colgroup>
<col width="31%" />
<col width="31%" />
<col width="38%" />
</colgroup>
<tbody valign="top">
<tr class="row-odd"><td><a class="reference internal" href="_images/stars.jpg"><img alt="logo" class="align-middle" src="_images/stars.jpg" style="width: 20pt; height: 20pt;" /></a></td>
<td><a class="reference internal" href="_images/stars.jpg"><img alt="logo" class="align-middle" src="_images/stars.jpg" style="width: 20pt; height: 20pt;" /></a></td>
<td>this is a longish text to include within a table and which is longer than the width of the column.</td>
</tr>
</tbody>
</table>
<div class="admonition note">
<p class="first admonition-title">Note</p>
<p class="last">Not easy to get exactly what you want though.</p>
</div>
</div>
<div class="section" id="intersphinx">
<h3><a class="toc-backref" href="#id40">1.10.7. Intersphinx</a><a class="headerlink" href="#intersphinx" title="Permalink to this headline">¶</a></h3>
<p>When you create a project, Sphinx generates a file containing an index to  all the possible links (title, classes, functions, ...).</p>
<p>You can refer to those index only if Sphinx knowns where to find this index. THis is possible thanks to the <strong>intersphinx</strong> option in your configuration file.</p>
<p>For instance, Python provides such a file, by default Sphinx knows about it. The following code can be found at the end of a typical Sphinx configuration file. Complete it to your needds:</p>
<div class="highlight-python"><div class="highlight"><pre><span class="c"># Example configuration for intersphinx: refer to the Python standard library.</span>
<span class="n">intersphinx_mapping</span> <span class="o">=</span> <span class="p">{</span><span class="s">&#39;http://docs.python.org/&#39;</span><span class="p">:</span> <span class="bp">None</span><span class="p">,</span> <span class="p">}</span>
</pre></div>
</div>
</div>
<div class="section" id="file-wide-metadata">
<h3><a class="toc-backref" href="#id41">1.10.8. file-wide metadata</a><a class="headerlink" href="#file-wide-metadata" title="Permalink to this headline">¶</a></h3>
<p>when using the following syntax:</p>
<div class="highlight-python"><div class="highlight"><pre>:fieldname: some contents
</pre></div>
</div>
<p>some special keywords are recognised. For instance, <em>orphan</em>, <em>nocomments</em>, <em>tocdepth</em>.</p>
<p>An example of rendering is the toctree of top of this page.</p>
<div class="section" id="orphan">
<h4>1.10.8.1. orphan<a class="headerlink" href="#orphan" title="Permalink to this headline">¶</a></h4>
<p>Sometimes, you have an rst file, that is not included in any rst files (when using include for instance). Yet, there are warnings. If you want to supprresse the warnings, include this code in the file:</p>
<div class="highlight-python"><div class="highlight"><pre>:orphan:
</pre></div>
</div>
<p>There is also tocdepth and nocomments metadata. See Sphinx homepage.</p>
</div>
</div>
<div class="section" id="metainformation">
<h3><a class="toc-backref" href="#id42">1.10.9. metainformation</a><a class="headerlink" href="#metainformation" title="Permalink to this headline">¶</a></h3>
<dl class="directive">
<dt id="directive-sectionauthor">
<tt class="descname">.. sectionauthor::</tt><tt class="descclassname"> name &lt;email&gt;</tt><a class="headerlink" href="#directive-sectionauthor" title="Permalink to this definition">¶</a></dt>
<dd><p>Specifies the author of the current section.:</p>
<div class="highlight-python"><div class="highlight"><pre>.. sectionauthor:: John Smith &lt;js@python.org&gt;
</pre></div>
</div>
<p>By default, this markup isn’t reflected in the output in any way,  but you can set the configuration value <strong>show_authors</strong> to True to make them produce a paragraph in the output.</p>
</dd></dl>

</div>
<div class="section" id="contents-directives">
<h3><a class="toc-backref" href="#id43">1.10.10. contents directives</a><a class="headerlink" href="#contents-directives" title="Permalink to this headline">¶</a></h3>
<dl class="directive">
<dt id="directive-contents">
<tt class="descname">.. contents::</tt><tt class="descclassname"> </tt><a class="headerlink" href="#directive-contents" title="Permalink to this definition">¶</a></dt>
<dd><div class="highlight-python"><div class="highlight"><pre>.. contents:: a title for the contents
    :depth: 2
</pre></div>
</div>
<ul class="simple">
<li><strong>depth</strong> indicates the max section depth to be shown in the contents</li>
</ul>
</dd></dl>

</div>
</div>
<div class="section" id="useful-extensions">
<h2><a class="toc-backref" href="#id44">1.11. Useful extensions</a><a class="headerlink" href="#useful-extensions" title="Permalink to this headline">¶</a></h2>
<p>In the special file called <strong>conf.py</strong>, there is a variable called <strong>extensions</strong>. You can add extension in this variable. For instance:</p>
<div class="highlight-python"><div class="highlight"><pre><span class="n">extensions</span> <span class="o">=</span> <span class="p">[</span><span class="o">-</span>
    <span class="s">&#39;easydev.copybutton&#39;</span><span class="p">,</span>
    <span class="s">&#39;sphinx.ext.autodoc&#39;</span><span class="p">,</span>
    <span class="s">&#39;sphinx.ext.autosummary&#39;</span><span class="p">,</span>
    <span class="s">&#39;sphinx.ext.coverage&#39;</span><span class="p">,</span>
    <span class="s">&#39;sphinx.ext.graphviz&#39;</span><span class="p">,</span>
    <span class="s">&#39;sphinx.ext.doctest&#39;</span><span class="p">,</span>
    <span class="s">&#39;sphinx.ext.intersphinx&#39;</span><span class="p">,</span>
    <span class="s">&#39;sphinx.ext.todo&#39;</span><span class="p">,</span>
    <span class="s">&#39;sphinx.ext.coverage&#39;</span><span class="p">,</span>
    <span class="s">&#39;sphinx.ext.pngmath&#39;</span><span class="p">,</span>
    <span class="s">&#39;sphinx.ext.ifconfig&#39;</span><span class="p">,</span>
    <span class="s">&#39;matplotlib.sphinxext.only_directives&#39;</span><span class="p">,</span>
    <span class="s">&#39;matplotlib.sphinxext.plot_directive&#39;</span><span class="p">,</span>
 <span class="p">]</span>
</pre></div>
</div>
<div class="section" id="pngmath-maths-and-equations-with-latex">
<h3><a class="toc-backref" href="#id45">1.11.1. pngmath: Maths and Equations with LaTeX</a><a class="headerlink" href="#pngmath-maths-and-equations-with-latex" title="Permalink to this headline">¶</a></h3>
<p>The extension to be added is the pngmath from sphinx:</p>
<div class="highlight-python"><div class="highlight"><pre><span class="n">extensions</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="s">&#39;sphinx.ext.pngmath&#39;</span><span class="p">)</span>
</pre></div>
</div>
<p>In order to include equations or simple Latex code in the text (e.g., <img class="math" src="_images/math/69aee8294efcf74a12c547e2eecbeea462981e9b.png" alt="\alpha \leq \beta"/> ) use the following code:</p>
<div class="highlight-python"><div class="highlight"><pre>:math:`\alpha &gt; \beta`
</pre></div>
</div>
<div class="admonition warning">
<p class="first admonition-title">Warning</p>
<p class="last">The <em>math</em> markup can be used within RST files (to be parsed by Sphinx) but within your python&#8217;s docstring, the slashes need to be escaped ! <tt class="docutils literal"><span class="pre">:math:`\alpha`</span></tt> should therefore be written <tt class="docutils literal"><span class="pre">:math:`\\alpha`</span></tt> or put an &#8220;r&#8221; before the docstring</p>
</div>
<p>Note also, that you can easily include more complex mathematical expressions using the math directive:</p>
<div class="highlight-python"><div class="highlight"><pre>.. math::

    n_{\mathrm{offset}} = \sum_{k=0}^{N-1} s_k n_k
</pre></div>
</div>
<p>Here is another:</p>
<div class="math">
<p><img src="_images/math/77e80baab0b9dafa039808919b9e20235ef4d1ab.png" alt="n_{\mathrm{offset}} = \sum_{k=0}^{N-1} s_k n_k"/></p>
</div><p>It seems that there is no limitations to LaTeX usage:</p>
<div class="math">
<p><img src="_images/math/58485172602dee9ec77913d26d7439c3bb65478d.png" alt="s_k^{\mathrm{column}} = \prod_{j=0}^{k-1} d_j , \quad  s_k^{\mathrm{row}} = \prod_{j=k+1}^{N-1} d_j ."/></p>
</div></div>
<div class="section" id="todo-extension">
<h3><a class="toc-backref" href="#id46">1.11.2. TODO extension</a><a class="headerlink" href="#todo-extension" title="Permalink to this headline">¶</a></h3>
<p>Similarly to the note directive, one can include todo boxes bu it requires the <cite>sphinx.ext.todo</cite> extension to be added in the <strong>conf.py</strong> file by adding two lines of code:</p>
<div class="highlight-python"><div class="highlight"><pre><span class="n">extensions</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="s">&#39;sphinx.ext.todo&#39;</span><span class="p">)</span>
<span class="n">todo_include_todos</span><span class="o">=</span><span class="bp">True</span>
</pre></div>
</div>
<div class="admonition-todo admonition" id="index-0">
<p class="first admonition-title">Todo</p>
<p class="last">a todo box</p>
</div>
</div>
<div class="section" id="copybutton">
<h3><a class="toc-backref" href="#id47">1.11.3. copybutton</a><a class="headerlink" href="#copybutton" title="Permalink to this headline">¶</a></h3>
<p>When including Python code with the &gt;&gt;&gt; signs, there is a nice extension called copybutton that allows to hide the signs hence make a copy/paste possible. I put this extension into the package <strong>easydev</strong>, available on Pypi website. I do not know the origin of this code so sorry if it&#8217;s yours. If so, let me know so that I can add the author!copyright.</p>
<p>So, if you add the easydev.extension into the configuration file</p>
<div class="highlight-python"><div class="highlight"><pre><span class="n">extensions</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="s">&#39;easydev.copybutton&#39;</span><span class="p">)</span>
<span class="n">jscopybutton_path</span> <span class="o">=</span> <span class="n">easydev</span><span class="o">.</span><span class="n">copybutton</span><span class="o">.</span><span class="n">get_copybutton_path</span><span class="p">()</span>

<span class="k">if</span> <span class="n">os</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">isdir</span><span class="p">(</span><span class="s">&#39;_static&#39;</span><span class="p">)</span><span class="o">==</span><span class="bp">False</span><span class="p">:</span>
    <span class="n">os</span><span class="o">.</span><span class="n">mkdir</span><span class="p">(</span><span class="s">&#39;_static&#39;</span><span class="p">)</span>

<span class="kn">import</span> <span class="nn">shutil</span>
<span class="n">shutil</span><span class="o">.</span><span class="n">copy</span><span class="p">(</span><span class="n">jscopybutton_path</span><span class="p">,</span> <span class="s">&#39;_static&#39;</span><span class="p">)</span>

<span class="n">html_static_path</span> <span class="o">=</span> <span class="p">[</span><span class="s">&#39;_static&#39;</span><span class="p">]</span>
</pre></div>
</div>
<p>Then, you can add a block code (using the &gt;&gt;&gt; signs) and you should see a clickable set of characters (&gt;&gt;&gt;) in the top right corner to swith on/off the &gt;&gt;&gt; signs:</p>
<div class="highlight-python"><div class="highlight"><pre><span class="gp">&gt;&gt;&gt; </span><span class="n">a</span><span class="o">=</span><span class="mi">1</span>
</pre></div>
</div>
<p class="rubric">Footnotes</p>
<table class="docutils footnote" frame="void" id="footnote1" rules="none">
<colgroup><col class="label" /><col /></colgroup>
<tbody valign="top">
<tr><td class="label"><a class="fn-backref" href="#id2">[1]</a></td><td>this is a footnote aimed at illustrating the footnote capability.</td></tr>
</tbody>
</table>
<p class="rubric">Bibliography</p>
<table class="docutils citation" frame="void" id="cit2002" rules="none">
<colgroup><col class="label" /><col /></colgroup>
<tbody valign="top">
<tr><td class="label"><a class="fn-backref" href="#id3">[CIT2002]</a></td><td>A citation
(as often used in journals).</td></tr>
</tbody>
</table>
</div>
</div>
</div>


          </div>
        </div>
      </div>
        </div>
        <div class="sidebar">

            <!-- <g:plusone size="tall"></g:plusone> -->
            <g:plusone size="standard" count='true'></g:plusone>
          		
          <h3 style="margin-top: 1.5em;">Search</h3>
          <form class="search" action="search.html" method="get">
            <input type="text" name="q" />
            <input type="submit" value="Go" />
            <input type="hidden" name="check_keywords" value="yes" />
            <input type="hidden" name="area" value="default" />
          </form>
          <p class="searchtip" style="font-size: 90%">
            Enter search terms or a module, class or function name.
          </p>
   	       	<hr />
   	       	<!-- Authors: <a></a> -->
	          <hr />
            This page: <a href="_sources/rest_syntax.txt">Show source.</a>
            <hr />
           		<h3><a href="index.html">Table Of Contents</a></h3>
          		<ul>
<li class="toctree-l1"><a class="reference internal" href="introduction.html">1. Why Sphinx and for which users ?</a></li>
<li class="toctree-l1"><a class="reference internal" href="quickstart.html">2. QuickStart</a></li>
</ul>
<ul class="current">
<li class="toctree-l1 current"><a class="current reference internal" href="">1. Restructured Text (reST) and Sphinx CheatSheet</a></li>
<li class="toctree-l1"><a class="reference internal" href="docstring_python.html">2. Example on how to document your Python docstrings</a></li>
<li class="toctree-l1"><a class="reference internal" href="doctest.html">3. How to include test in your Python docstrings using doctest</a></li>
</ul>
<ul>
<li class="toctree-l1"><a class="reference internal" href="faqs.html">FAQS</a></li>
<li class="toctree-l1"><a class="reference internal" href="changelog.html">Changelog</a></li>
</ul>

          	<hr />
        </div>
        <div class="clearer"></div>
      </div>
    </div>

    <div class="footer-wrapper">
      <div class="footer">
      		<div class="left">
      &copy;
       <a href="copyright.html">Copyright</a> Thomas Cokelaer.
      
     <br/>
       	Last updated on Aug 14, 2014.
       	
       <br/>
       Created using <a href="http://sphinx.pocoo.org/">Sphinx</a> 1.2.2.
       <br/> 
   		</div>

       <div class="right">
          <a href="quickstart.html" title="2. QuickStart"
             >previous</a> |
          <a href="docstring_python.html" title="2. Example on how to document your Python docstrings"
             >next</a> |
          <a href="py-modindex.html" title="Python Module Index"
             >modules</a> |
          <a href="genindex.html" title="General Index"
             >index</a>
          <br/>
        </div>

        <div class="clearer"></div>
      </div>
    </div>

  </body>
</html>