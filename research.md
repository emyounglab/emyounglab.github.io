---
layout: page
title: Research
permalink: /research/
description: "The Young Lab makes new organisms engineerable — bacteria, yeasts, and plant cell cultures — and uses them to build biosensors, produce molecules, and verify genetic engineering."
---

<div class="rmap" id="rmap">
<p class="rmap-cap">Our core capability is host onboarding: bringing an organism into the biofoundry pipeline by merging bioinformatics with modular genetic parts libraries, to enable high-throughput combinatorial pathway engineering (building and testing many designs at once).</p>
<svg class="rmap-arcs" aria-hidden="true"></svg>

<div class="rmap-band">
<span class="rmap-axis">Research Areas</span>
<div class="rmap-row">
<a class="rmap-chip" data-node="r1" href="#onboarding">Organism Onboarding</a>
<a class="rmap-chip" data-node="r2" href="#metabolic-engineering">Metabolic Engineering</a>
<a class="rmap-chip" data-node="r3" href="#circuits">Genetic Circuits</a>
<a class="rmap-chip" data-node="r4" href="#biofoundries">Biofoundries</a>
</div>
</div>

<div class="rmap-band rmap-band-apps">
<div class="rmap-row">
<a class="rmap-chip rmap-chip-app" data-node="a1" href="#app-soil-sensing">Soil Sensing</a>
<a class="rmap-chip rmap-chip-app" data-node="a2" href="#app-biomanufacturing">Biomanufacturing</a>
<a class="rmap-chip rmap-chip-app" data-node="a3" href="#app-medicines">Medicines and Nutrition</a>
<a class="rmap-chip rmap-chip-app" data-node="a4" href="#app-biomaterials">Biomaterials</a>
<a class="rmap-chip rmap-chip-app" data-node="a5" href="#app-biosecurity">Biosecurity</a>
</div>
<span class="rmap-axis">Applications</span>
</div>

<div class="rmap-resources">
<span class="rmap-axis">Get Our Parts and Tools</span>
<div class="rmap-row">
<a class="rmap-link" href="https://www.addgene.org/kits/young-opencidar/">OpenCidar kit</a>
<a class="rmap-link" href="https://www.addgene.org/browse/article/28252864/">Xd MoClo kit</a>
<span class="rmap-link is-soon">Dh MoClo <span class="soon-tag">soon</span></span>
<a class="rmap-link" href="https://github.com/emyounglab/prymetime">PRYMETIME</a>
<a class="rmap-link" href="#part-kits">All resources</a>
</div>
</div>

<div class="rmap-resources">
<span class="rmap-axis">Current Funding</span>
<p class="rmap-funding">NSF CREATE Biofoundry &middot; WPI BioHub &middot; DEVCOM &middot; Evonik &middot; Takeda &middot; <a href="#funding">funding and experience</a></p>
</div>

<p class="rmap-note">Hover or focus any item to see what connects to it. Select one to open its section.</p>
</div>

<h2 class="research-group-label">Research Areas</h2>

<details class="research-section" id="onboarding">
<summary><h2>Organism Onboarding</h2></summary>
<p>We build the genomic foundation and modular parts that make a new host engineerable &mdash; nonconventional yeasts, diverse bacteria, and plant cell cultures. Our key strategy is merging bioinformatics and development of modular genetic parts libraries to facilitate high-throughput combinatorial pathway engineering in these organisms.</p>
<p>In yeasts we have developed two hosts, <a href="https://doi.org/10.1101/2025.10.23.684212"><i>Debaryomyces hansenii</i></a> and <a href="https://doi.org/10.1007/s00253-024-13379-w"><i>Xanthophyllomyces dendrorhous</i></a>, that can grow on inexpensive sugars, and we use <a href="https://doi.org/10.1002/bit.28891">comparative transcriptomics</a> to characterize a new yeast before we engineer it. The same foundation has produced reference genomes and phenotype maps for other nonconventional yeasts &mdash; <a href="https://doi.org/10.1128/MRA.00397-23"><i>Kregervanrija delftensis</i></a>, <a href="https://doi.org/10.1128/MRA.00611-22"><i>Ogataea polymorpha</i></a>, and <a href="https://doi.org/10.1093/g3journal/jkad093">probiotic strains characterised by nanopore sequencing</a>.</p>
<p>In bacteria we have developed <a href="https://doi.org/10.1021/acssynbio.3c00104">a genetic part library</a> that is generalizable to a large set of gram negative soil bacteria and biomaterial producing bacteria, using a broad host range plasmid to test already designed DNA parts in various organisms. We have tested this in <i>Pseudomonas putida</i>, a soil bacterium with unusual metabolic versatility and tolerance of chemical stress, which makes it a durable host, or chassis, for sensing in the field; in <i>Cupriavidus necator</i>, a potential platform host for biomaterial production from CO<sub>2</sub>; and in <a href="https://doi.org/10.1101/2023.08.21.554206">bacterial nanocellulose producing bacteria</a>.</p>
</details>

<details class="research-section" id="metabolic-engineering">
<summary><h2>Metabolic Engineering</h2></summary>
<p>We engineer these hosts, using modular parts libraries and combinatorial pathway engineering, to overproduce a target molecule.</p>
<p><b><i>Debaryomyces hansenii</i>.</b> Grows in extremely salty water on lignocellulosic biomass and overproduces fatty acids, which can support on-demand manufacture of oleochemicals like omega-3 fatty acids, <a href="https://doi.org/10.1101/2025.10.23.684212">alkanes</a>, or lubricants.</p>
<p><b><i>Xanthophyllomyces dendrorhous</i>.</b> Grows on lignocellulosic biomass and overproduces <a href="https://doi.org/10.1007/s00253-024-13379-w">terpenes</a>, a diverse class of molecules that has long held promise for making medicines, fuels, and chemicals.</p>
<p><b><i>Taxus chinensis</i>.</b> In collaboration with Prof. Susan Roberts we extend this to <a href="https://doi.org/10.1007/978-3-030-58271-5_1">plant cell culture</a>, engineering <a href="https://doi.org/10.1016/j.ymben.2026.102524">suspension cell lines to overproduce paclitaxel</a>, including <a href="https://doi.org/10.3389/fbioe.2023.1272811">CRISPR-guided control of supporting pathways</a>.</p>
<p class="rs-collab">Co-advised PhD work with the Roberts lab at WPI.</p>
</details>

<details class="research-section" id="circuits">
<summary><h2>Genetic Circuits</h2></summary>
<p>We have developed a unique fungal-bacterial system that can send signals centimeters underground. The system uses bacteria with a biosensor to detect a chemical, and then fungal mycelia to send the detection signal to the surface. This required a great deal of genetic circuit optimization to make the system work in actual dry soil. We have developed a method of sequential screening to filter out candidate genetic circuits and plan to use this to develop diverse biosensors that work in actual soil.</p>
<p>This work was funded by DARPA through the BioReporters and Ceres programs. <a href="https://patentsgazette.uspto.gov/week10/OG/html/1544-2/US12571789-20260310.html">US Patent 12,571,789 B1</a> has been awarded.</p>
<p class="rs-collab">With RTX BBN Technologies.</p>
</details>

<details class="research-section" id="biofoundries">
<summary><h2>Biofoundries</h2></summary>
<p><b>Software and bioinformatics.</b> We have developed processes to <a href="https://doi.org/10.1038/s41467-021-21656-9">integrate genome sequencing into strain development workflows</a> to verify accuracy of genetic engineering. This same approach can be used to <a href="https://doi.org/10.1021/acssynbio.3c00398">identify genetic engineering from complex environmental samples</a> in biosecurity contexts. The same assembly work reads yeasts that were never engineered at all: with Reeta Rao we resolved the <a href="https://doi.org/10.1093/g3journal/jkad093">genetic basis of probiotic yeast phenotypes</a> and the <a href="https://doi.org/10.1128/iai.00103-24">virulence and drug tolerance of <i>Candida auris</i></a>. With Claudia Vickers we applied PRYMETIME to engineered yeast, showing that <a href="https://doi.org/10.1021/acssynbio.3c00363">plasmid integration diversifies a strain</a>. We also <a href="https://doi.org/10.1021/acssynbio.1c00188">curated synthetic biology knowledge</a> from the literature into a searchable system, combining <a href="https://doi.org/10.1021/acssynbio.1c00611">text mining</a> with <a href="https://doi.org/10.1021/acssynbio.1c00225">curation principles drawn from the SBOL iGEM data set</a>, so that published designs and data could be found and reused.</p>
<p><b>Automation.</b> We work on <a href="https://doi.org/10.1007/978-1-0716-5320-3_19">laboratory automation</a> for genetic engineering, and build it as shared infrastructure through the <a href="https://createbiofoundries.org">CREATE Biofoundry</a> &mdash; the NSF Center for Robust, Equitable and Accessible Technology for Next-Generation BioFoundries, with Mark Blenner at the University of Delaware and Howard Salis at Penn State. CREATE builds distributed automation and design capability for proteins, biosensors, and bacteriophage products, and puts those tools within reach of institutions that could not run a foundry of their own &mdash; primarily undergraduate institutions, HBCUs, minority-serving institutions, and women's colleges across the Northeast and Mid-Atlantic.</p>
<p><b>Scale.</b> Automation is necessary for combinatorial engineering, and fermentation capacity is necessary to turn a strain into a process. The <a href="https://massbiohub.org">WPI BioHub</a>, one of five NSF biofoundries nationally, provides fermentation from 1&nbsp;L to 100&nbsp;L, process development, and trained personnel, so that a product developed at the bench can be scaled in Central Massachusetts. It was launched with $5.2M from the Massachusetts Technology Collaborative and built on the WPI Cell Engineering Research Equipment Suite (CERES) and Bioprocess Center.</p>
<p class="rs-collab">Knowledge curation with Chris Myers and a multi-institution team.</p>
</details>

<h2 class="research-group-label">Applications</h2>

<details class="research-section" id="app-soil-sensing">
<summary><h2>Soil Sensing and Environmental Monitoring</h2></summary>
<p>We build bacterial biosensors that detect a chemical underground and use fungal mycelia to carry the signal to the surface, over centimeters of soil.</p>
<p>Making this work in actual dry soil took a great deal of genetic circuit optimization. Comparing circuit output across labs and instruments requires <a href="https://doi.org/10.1093/synbio/ysac010">calibrated fluorescence measurement</a>. We use <i>Pseudomonas putida</i> for the sensing function because it tolerates the chemical stress of a field environment. This work was funded by DARPA through the BioReporters and Ceres programs, and <a href="https://patentsgazette.uspto.gov/week10/OG/html/1544-2/US12571789-20260310.html">US Patent 12,571,789 B1</a> has been awarded.</p>
<ul class="project-links">
<li><a href="#circuits">Genetic Circuits</a></li>
<li><a href="#onboarding">Organism Onboarding</a></li>
</ul>
</details>

<details class="research-section" id="app-biomanufacturing">
<summary><h2>Biomanufacturing from Inexpensive Biomass</h2></summary>
<p>Feedstock cost determines whether a bio-based product is viable. We work with hosts that grow on inexpensive inputs: lignocellulosic biomass, water too salty for most organisms, and CO<sub>2</sub>.</p>
<p><i>Debaryomyces hansenii</i> overproduces fatty acids while growing in extremely salty water, a route to <a href="https://doi.org/10.1101/2025.10.23.684212">alkanes</a> and lubricants. <a href="https://doi.org/10.1007/s00253-024-13379-w"><i>Xanthophyllomyces dendrorhous</i></a> makes terpenes from lignocellulose. <i>Cupriavidus necator</i> fixes CO<sub>2</sub> directly. Scaling any of these from a strain to a process requires fermentation capacity, which the <a href="https://massbiohub.org">BioHub</a> provides.</p>
<ul class="project-links">
<li><a href="#onboarding">Organism Onboarding</a></li>
<li><a href="#metabolic-engineering">Metabolic Engineering</a></li>
<li><a href="#biofoundries">Biofoundries</a></li>
</ul>
</details>

<details class="research-section" id="app-medicines">
<summary><h2>Medicines and Nutrition</h2></summary>
<p>Paclitaxel is still sourced from yew trees or made semi-synthetically. With the Roberts lab we engineer <a href="https://doi.org/10.1016/j.ymben.2026.102524"><i>Taxus chinensis</i> suspension cell lines to overproduce it</a>, including <a href="https://doi.org/10.3389/fbioe.2023.1272811">CRISPR-guided control of the supporting pathways</a> that compete for the same precursors.</p>
<p><i>D. hansenii</i> produces fatty acids, a route to omega-3 fatty acids, and the <a href="https://doi.org/10.1007/s00253-024-13379-w">terpenes</a> from <i>X. dendrorhous</i> are precursors to a large class of drugs.</p>
<p class="rs-review">We surveyed the field in <a href="https://doi.org/10.1016/j.copbio.2018.02.001">Genetic engineering of host organisms for pharmaceutical synthesis</a>.</p>
<ul class="project-links">
<li><a href="#onboarding">Organism Onboarding</a></li>
<li><a href="#metabolic-engineering">Metabolic Engineering</a></li>
</ul>
</details>

<details class="research-section" id="app-biomaterials">
<summary><h2>Biomaterials</h2></summary>
<p>Bacterial nanocellulose is pure and strong, and bacteria grow it directly. We have characterized <a href="https://doi.org/10.1101/2023.08.21.554206">cellulose-producing <i>Acetobacteraceae</i></a> and shown that the carbon source changes the material: <a href="https://doi.org/10.1016/j.bioadv.2023.213345"><i>Komagataeibacter hansenii</i> grown on arabitol yields optically clear cellulose</a>.</p>
<p>Onboarding these organisms enables genetic tuning of the material. <i>Cupriavidus necator</i> extends this to materials built from CO<sub>2</sub>.</p>
<p class="rs-review">We surveyed the field in <a href="https://doi.org/10.1016/j.coche.2019.03.002">Synthetic biology for bio-derived structural materials</a>.</p>
<ul class="project-links">
<li><a href="#onboarding">Organism Onboarding</a></li>
<li><a href="#metabolic-engineering">Metabolic Engineering</a></li>
</ul>
</details>

<details class="research-section" id="app-biosecurity">
<summary><h2>Biosecurity</h2></summary>
<p>The same genome reading that verifies a strain we built can also determine whether an unknown sample was engineered.</p>
<p>We built <a href="https://doi.org/10.1038/s41467-021-21656-9">assembly methods that recover engineered constructs intact</a> from mixed samples, and contributed to <a href="https://doi.org/10.1021/acssynbio.3c00398">ensemble detection</a> that flags engineering signatures across many target organisms without requiring an expert to review each case.</p>
<p>Reading a genome requires collecting a sample first. The biosensors and circuits we build for soil report from the field without a sample.</p>
<ul class="project-links">
<li><a href="#biofoundries">Biofoundries</a></li>
<li><a href="#circuits">Genetic Circuits</a></li>
</ul>
</details>

<h2 class="research-group-label">Funding and Experience</h2>

<details class="research-section" id="funding">
<summary><h2>Funding and Experience</h2></summary>
<h3>Current</h3>
<ul class="fund-now">
<li><a href="https://createbiofoundries.org">NSF CREATE Biofoundry</a></li>
<li><a href="https://massbiohub.org">WPI BioHub</a></li>
<li>DEVCOM</li>
<li>Evonik</li>
<li>Takeda</li>
</ul>
<h3>Past</h3>
<ul class="fund-past">
<li><b>IARPA FELIX</b> &mdash; detecting engineered organisms</li>
<li><b>NSF CAREER</b> &mdash; onboarding and engineering <i>Xanthophyllomyces dendrorhous</i> and <i>Debaryomyces hansenii</i></li>
<li><b>DARPA BioReporters</b> &mdash; soil sensing</li>
<li><b>DARPA Ceres</b> &mdash; soil sensing</li>
<li><b>NSF Harnessing the Data Revolution</b> &mdash; synthetic biology knowledge curation</li>
<li><b>Massachusetts Life Sciences Center Building Breakthroughs</b> &mdash; the WPI Cell Engineering Research Equipment Suite (CERES) and <i>Debaryomyces hansenii</i></li>
<li><b>BioMADE</b></li>
</ul>
<h3>Fellowships in the group</h3>
<p class="fund-note">Awarded to trainees, not to the lab.</p>
<ul class="fund-past">
<li><b>NSF CEDAR NRT</b> &mdash; traineeship</li>
<li><b>NSF Graduate Research Fellowship</b> &mdash; traineeship</li>
</ul>
</details>

<h2 class="research-group-label">Resources</h2>

<details class="research-section" id="part-kits">
<summary><h2>Part Kits</h2></summary>
<p>We distribute standardized genetic part kits that enable reproducible synthetic biology across labs and organisms. The MoClo kits follow modular cloning, a standard that enables parts from different labs to assemble in a single reaction. We distribute through Addgene.</p>
<ul class="project-links">
  <li><a href="https://www.addgene.org/kits/young-opencidar/">OpenCidar</a></li>
  <li><a href="https://www.addgene.org/browse/article/28252864/">Xd MoClo</a></li>
  <li>Dh MoClo <span class="pending">deposit in progress</span></li>
</ul>
{% include addgene-widget.html %}
</details>

<details class="research-section" id="software-projects">
<summary><h2>Software Projects</h2></summary>
<p>We have developed open-source tools for synthetic biology design, data analysis, and genetic engineering workflows.</p>

<h3><a href="https://github.com/emyounglab/prymetime">PRYMETIME</a></h3>
<p>Pipeline for Recombinant Yeast genoMEs That Identifies Markers of Engineering. It assembles yeast genomes from long and short reads and finds the engineering in them. <a href="https://doi.org/10.1038/s41467-021-21656-9">Introduced in 2021</a>, it has since carried four lines of work:</p>
<ul class="tool-uses">
  <li><b>Onboarding our own yeasts.</b> Reference genomes for <a href="https://doi.org/10.1128/MRA.00397-23"><i>Kregervanrija delftensis</i></a> and <a href="https://doi.org/10.1128/MRA.00611-22"><i>Ogataea polymorpha</i></a>.</li>
  <li><b>Detecting engineering in unknown samples.</b> <a href="https://doi.org/10.1021/acssynbio.3c00398">Ensemble detection of DNA engineering signatures</a> across many target organisms, for IARPA FELIX.</li>
  <li><b>Sequencing yeasts we did not engineer.</b> With Reeta Rao, the <a href="https://doi.org/10.1093/g3journal/jkad093">genetic basis of probiotic yeast phenotypes</a> and the <a href="https://doi.org/10.1128/iai.00103-24">virulence and drug tolerance of <i>Candida auris</i></a>.</li>
  <li><b>Verifying engineered strains.</b> With Claudia Vickers, how <a href="https://doi.org/10.1021/acssynbio.3c00363">plasmid integration diversifies an engineered strain</a>.</li>
</ul>
</details>

<details class="research-section" id="reviews">
<summary><h2>Reviews and Perspectives</h2></summary>
<p>These reviews and chapters are a starting point for readers new to the field.</p>
<ul class="reading-list">
  <li><a href="https://doi.org/10.1016/B978-0-443-24738-5.00099-9">Synthetic Biology: An Overview</a> <span class="rl-meta">2026</span><br>An introduction to the field.</li>
  <li><a href="https://doi.org/10.1007/978-1-0716-5320-3_19">Automated Genetic Engineering in the Laboratory</a> <span class="rl-meta">2026</span><br>How automation is used for genetic engineering in the lab.</li>
  <li><a href="https://doi.org/10.1016/j.copbio.2018.02.001">Genetic engineering of host organisms for pharmaceutical synthesis</a> <span class="rl-meta">2018</span><br>How the choice of host affects what a drug pathway can produce.</li>
  <li><a href="https://doi.org/10.1016/j.coche.2019.03.002">Synthetic biology for bio-derived structural materials</a> <span class="rl-meta">2019</span><br>Using synthetic biology to make structural materials.</li>
  <li><a href="https://doi.org/10.1007/978-3-030-58271-5_1">Secondary metabolite production in plant cell culture</a> <span class="rl-meta">2021</span><br>With the Roberts lab, on epigenetic control of plant natural products.</li>
  <li><a href="https://doi.org/10.1021/acssynbio.4c00276">Ten years of the Synthetic Biology Summer Course at Cold Spring Harbor Laboratory</a> <span class="rl-meta">2024</span><br>A decade of the CSHL synthetic biology course, written with the instructors.</li>
</ul>
</details>

<details class="research-section" id="organizations">
<summary><h2>Organizations</h2></summary>
<p>We build and share automation capacity through two biofoundries, described under <a href="#biofoundries">Biofoundries</a>.</p>
<ul class="project-links">
  <li><a href="https://createbiofoundries.org">CREATE Biofoundry</a></li>
  <li><a href="https://massbiohub.org">BioHub</a></li>
</ul>
</details>

<p class="research-join">We take PhD students, undergraduates, and postdocs. See <a href="{{ '/join/' | relative_url }}">Join the lab</a>.</p>

<script>
(function(){
  var map=document.getElementById('rmap'); if(!map) return;
  var svg=map.querySelector('.rmap-arcs');
  var EDGES=[['r1','a1'],['r3','a1'],
             ['r1','a2'],['r2','a2'],
             ['r2','a3'],['r1','a3'],
             ['r1','a4'],['r2','a4'],
             ['r4','a5'],['r3','a5'],['r4','a2']];
  var chips={}, paths=[];
  map.querySelectorAll('.rmap-chip').forEach(function(c){ chips[c.dataset.node]=c; });

  // a wrapped chip row makes the arc geometry meaningless, so bail instead
  function wrapped(){
    return Array.prototype.some.call(map.querySelectorAll('.rmap-row'),function(row){
      var cs=row.querySelectorAll('.rmap-chip'); if(cs.length<2) return false;
      var t=cs[0].getBoundingClientRect().top;
      return Array.prototype.some.call(cs,function(c){
        return Math.abs(c.getBoundingClientRect().top-t)>2;
      });
    });
  }
  function draw(){
    svg.innerHTML=''; paths=[];
    var box=map.getBoundingClientRect();
    // matches the 900px breakpoint that hides .rmap-arcs in the stylesheet
    if(window.innerWidth<=900) return;
    if(wrapped()) return;
    EDGES.forEach(function(e){
      var a=chips[e[0]], b=chips[e[1]]; if(!a||!b) return;
      var ra=a.getBoundingClientRect(), rb=b.getBoundingClientRect();
      var x1=ra.left-box.left+ra.width/2, y1=ra.bottom-box.top;
      var x2=rb.left-box.left+rb.width/2, y2=rb.top-box.top;
      var dy=(y2-y1)*0.55;
      var p=document.createElementNS('http://www.w3.org/2000/svg','path');
      p.setAttribute('d','M'+x1+' '+y1+' C'+x1+' '+(y1+dy)+', '+x2+' '+(y2-dy)+', '+x2+' '+y2);
      p.setAttribute('class','rmap-edge');
      p.dataset.a=e[0]; p.dataset.b=e[1];
      svg.appendChild(p); paths.push(p);
    });
  }
  function activate(node){
    map.classList.add('is-active');
    var keep={}; keep[node]=1;
    paths.forEach(function(p){
      var hit=(p.dataset.a===node||p.dataset.b===node);
      p.classList.toggle('is-on',hit);
      if(hit){ keep[p.dataset.a]=1; keep[p.dataset.b]=1; }
    });
    Object.keys(chips).forEach(function(k){ chips[k].classList.toggle('is-on',!!keep[k]); });
  }
  function clear(){
    map.classList.remove('is-active');
    paths.forEach(function(p){ p.classList.remove('is-on'); });
    Object.keys(chips).forEach(function(k){ chips[k].classList.remove('is-on'); });
  }
  Object.keys(chips).forEach(function(k){
    var c=chips[k];
    c.addEventListener('mouseenter',function(){ activate(k); });
    c.addEventListener('focus',function(){ activate(k); });
    c.addEventListener('mouseleave',clear);
    c.addEventListener('blur',clear);
  });

  // any in-page link opens the section it points at, not just map chips
  function openTarget(hash){
    if(!hash||hash.length<2) return;
    var el; try{ el=document.querySelector(hash); }catch(e){ return; }
    if(el&&el.tagName==='DETAILS') el.open=true;
  }
  document.querySelectorAll('a[href^="#"]').forEach(function(a){
    a.addEventListener('click',function(){ openTarget(this.getAttribute('href')); });
  });
  window.addEventListener('hashchange',function(){ openTarget(location.hash); });
  openTarget(location.hash);
  map.addEventListener('mouseleave',clear);
  draw();
  var pending=0;
  function redraw(){ if(pending) return; pending=requestAnimationFrame(function(){ pending=0; draw(); }); }
  if(window.ResizeObserver) new ResizeObserver(redraw).observe(map);
  else window.addEventListener('resize',redraw);
  if(document.fonts&&document.fonts.ready) document.fonts.ready.then(draw);
})();
</script>
