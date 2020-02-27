---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Radio Frequency Machine Learning (RFML)"
summary: "Extracting circuit-level fingerprints to distinguish between wireless devices sending exactly same message"
authors: []
tags: []
categories: []
date: 2020-02-25T14:49:34-08:00

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Communication system"
  focal_point: "bottom"
  preview_only: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_code: ""
url_pdf: ""
url_slides: "https://wcsl.ece.ucsb.edu/sites/default/files/publications/ita2020_madhow.pdf"
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

<ul>
	<li>Our goal is to learn&nbsp;<strong><em>RF signatures</em></strong>&nbsp;that can distinguish between devices sending&nbsp;<em>exactly</em>&nbsp;the same message. This is possible due to subtle hardware imperfections (labeled&nbsp;"nonlinearities" in the figure below) unique to each device.</li>
</ul>

<ul>
	<li>Since the information in RF data resides in complex baseband, we employ CNNs with complex-valued weights to learn these signatures. This technique&nbsp;does&nbsp;not use&nbsp;signal domain knowledge and can be used for any wireless protocol. We demonstrate its effectiveness for two protocols -&nbsp;WiFi and ADS-B.</li>
</ul>

<img src="architect.png" alt="Simply Easy Learning" width="600"
         height="240">

<ul>
	<li>We show that this&nbsp;approach is vulnerable to spoofing&nbsp;when using&nbsp;the entire packet:&nbsp;the CNN focuses on&nbsp;fields containing ID info (eg. MAC ID in WiFi) which can be easily spoofed. When using the preamble alone, reasonably high accuracies are obtained, and performance is significantly enhanced by noise augmentation.</li>
</ul>

<ul>
	<li>We also study robustness to confounding factors&nbsp;in data collected over multiple days and locations, such as the carrier frequency offset (CFO), which drifts over time, and the wireless channel, which depends on the propagation environment. We show that carefully designed data augmentation is critical for learning robust wireless signatures.</li>
</ul>

<p><small>&nbsp;</small></p>

<div class="field__item odd"><div class="entity entity-paragraphs-item paragraphs-item-related-publications-topic-group">
  <div class="content">
    <div class="field field--name-field-sub-topic-title field--type-text field--label-hidden"><div class="field__items"><div class="field__item even"><h3 class="">Yayınlar</h3></div></div></div>


<div class="field field--name-field-related-publications field--type-entityreference field--label-hidden"><div class="field__items"><div class="field__item even">	<div role="article" class="node node--simple-publication node--promoted contextual-links-region node--citation node--simple-publication--citation">
	  <div class="node__content">
	    <div class="field citation"> <b>Metehan Cekic*</b>,&nbsp;Soorya Gopalakrishnan*,&nbsp;Upamanyu Madhow, "<a href="https://arxiv.org/pdf/2002.10791.pdf" target="_self">Robust Wireless Fingerprinting: Generalizing Across Space and Time</a>", arXiv:2002.10791.


<br/>
<br/>

</div></div></div>  </div>
</div>
</div>


<div class="field field--name-field-related-publications field--type-entityreference field--label-hidden"><div class="field__items"><div class="field__item even">	<div role="article" class="node node--simple-publication node--promoted contextual-links-region node--citation node--simple-publication--citation">
	  <div class="node__content">
	    <div class="field citation">Soorya Gopalakrishnan*, <b> Metehan Cekic* </b>,&nbsp;Upamanyu Madhow, "<a href="https://www.ece.ucsb.edu/~metehancekic/publication/fingerprinting-2019-globecom/" target="_self">Robust Wireless Fingerprinting via Complex-Valued Neural Networks</a>", <i>IEEE Global Communications Conference (Globecom)</i>,&nbsp;Waikoloa, Hawaii, Dec. 2019. 
          
</div></div></div>  </div>
</div>
</div>