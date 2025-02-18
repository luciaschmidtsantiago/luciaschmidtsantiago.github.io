---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}


I'm Caterina Fuster-Barceló, currently in the post-doc world with my focus on AI4Life project, Bioimage Model Zoo, the BioImage.IO Chatbot, and deepImageJ. My Ph.D. in Computer Science and Technology kickstarted this journey, leading me into the fascinating realm of bioimage analysis. Through projects like deepImageJ and the Bioimage Model Zoo, I'm on the front lines of integrating artificial intelligence into biomedical imaging, making strides in how we analyze and interpret biological images. Whether it's developing a chatbot to streamline bioimage analysis or pushing the boundaries with AI4Life, my work is all about leveraging technology to unveil the microscopic mysteries of biology. It's not just about the tech; it's about opening new doors in healthcare and research, one pixel at a time.

Academic Background
======
* Ph.D. in Computer Science and Technology, [Universidad Carlos III de Madrid](https://www.uc3m.es/phdprogram/computer-science-technology), _13 Dec. 2022_
* M.Sc. in Cibersecurity, [Universidad Carlos III de Madrid](https://www.uc3m.es/master/cybersecurity), 2020
* B.Sc. in Telematics Engineering, [Universitat de les Illes Balears](https://www.uib.eu/Learn/estudis-de-grau/grau/telematica/GTTT-P/), 2019

Professional History
======
* __Post-doctoral Researcher__: _Jan 2023 - present_
  * __Where__: [UC3M](https://www.uc3m.es/about-uc3m/bioengineering-aerospace-engineering-department),  Bioengineering Department
  * __Field__: Bioimage analysis
  * __PI__: [Dra. Arrate Muñoz Barrutia](https://image.hggm.es/es/arrate-munoz) 
  * __Projects__: [AI4Life](https://ai4life.eurobioimaging.eu), [Bioimage Model Zoo](https://bioimage.io/#/), [deepImageJ](https://deepimagej.github.io)

* __Post-doctoral Researcher__: _Jan 2024 - present_
  * __Where__: [IISGM](https://www.iisgm.com/investigacion/areas-de-investigacion/area-1-ingenieria-biomedica/29769-2/),  Biomedical Applications for Engineering
  * __Field__: Artificial Intelligence in biomedical imaging
  * __PI__: [Dra. Arrate Muñoz Barrutia](https://image.hggm.es/es/arrate-munoz) and [Dr. Javier Pascau González](https://igt.uc3m.es/jpascau/)

* __Visiting Researcher__: _Sept 2023 - Oct 2023_
  * __Where__: [KTH](https://www.kth.se/en),  [SciLifeLab](https://www.scilifelab.se), [AICell Lab](https://aicell.io), Stockholm, Sweden.
  * __Field__: Bioimage analysis
  * __PI__: [Dr. Wei Ouyang](https://oeway.github.io)  
  * __Projects__: [AI4Life](https://ai4life.eurobioimaging.eu), [Bioimage Model Zoo](https://bioimage.io/#/)

* __PhD Candidate__: _Sept 2020 - Dec 2022_
  * __Where__: [UC3M](https://www.uc3m.es/phdprogram/computer-science-technology), Computer Science and Technology
  * __Field__: Deep Learning applied to Biometrics
  * __Supervisors__:  [Dr. Pedro Peris-López](https://lightweightcryptography.com) and [Dra. Carmen Cámara](https://researchportal.uc3m.es/display/inv43106) 
  * __Project__: [CYNAMON-CM](https://www.tic.itefi.csic.es/CYNAMON/)

* __Research Assistant__: _October 2019 - Dec 2022_
  * __Where__: [UC3M](https://www.uc3m.es/home), [COSEC Laboratory](https://cosec.inf.uc3m.es)
  * __Field__: Cibersecurity  
  * __Supervisors__: [Dr. Pedro Peris-López](https://lightweightcryptography.com) and [Dra. Carmen Cámara](https://researchportal.uc3m.es/display/inv43106)

* __Security and DevOps Systems Technician__: _June 2019 - September 2019_
  * __Where__: [Air Europa, S.L.](https://www.aireuropa.com)
  * __Field__: Server and infraestructure mantainance and cibersecurity management
  * __Supervisor__: [Bernat Mut González](https://es.linkedin.com/in/bernatmut)

Publications
======
{% assign categories_order = "Peer-review Journals,Preprints,Conference Proceedings,Conference Abstracts,Datasets,Misc" | split: "," %}

{% for category in categories_order %}
  {% assign publications_in_category = site.publications | where: "category", category %}

  {% if publications_in_category.size > 0 %}
<h2 class="category-toggle">{{ category | capitalize }} <span class="toggle-icon">+</span></h2>
<div id="publications-{{ category | slugify }}" class="publications-section">
      {% for post in publications_in_category %}
        {% include archive-single.html %}
      {% endfor %}
</div>
  {% endif %}
{% endfor %}
  
Talks
======
{% assign sorted_talks = site.talks | sort: 'date' | reverse %}
{% assign last_year = "" %}

<div class="cv-container">
  {% for post in sorted_talks %}
    {% capture current_year %}{{ post.date | date: "%Y" }}{% endcapture %}

    {% unless last_year == current_year %}
      {% assign last_year = current_year %}
      <h3 class="year-toggle">{{ last_year }} <span class="toggle-icon">+</span></h3>
      <div class="year-content">
    {% endunless %}

    {% include archive-single-talk-cv.html %}

    {% if forloop.last %}
      </div>
    {% else %}
      {% capture next_talk_year %}{{ sorted_talks[forloop.index].date | date: "%Y" }}{% endcapture %}
      {% if next_talk_year != last_year %}
        </div>
      {% endif %}
    {% endif %}
  {% endfor %}
</div>

Teaching
======
<!-- Bachelor Thesis -->
<h3 class="section-toggle" onclick="toggleSection('bt-section')">Bachelor Theses <span id="toggle-icon-corporate-section" class="toggle-icon">+</span></h3>
<div id="bt-section" class="section-content">
  {% for post in site.teaching %}
    {% if post.type == "Bachelor Thesis" %}
      {% include archive-single-cv.html %}
    {% endif %}
  {% endfor %}
</div>

<!-- Master Programs -->
<h3 class="section-toggle" onclick="toggleSection('master-section')">Master Programs <span id="toggle-icon-master-section" class="toggle-icon">+</span></h3>
<div id="master-section" class="section-content">
  {% for post in site.teaching %}
    {% if post.type == "Master course" %}
      {% include archive-single-cv.html %}
    {% endif %}
  {% endfor %}
</div>

Hackathons
======
* __ImgLib2 and BigDataViewer Hackathon Prague__:
  * __What:__ Working on [SAMJ](https://github.com/segment-anything-models-java/SAMJ-IJ) and some exciting new projects related to ImagLib2. Visit the even webpage [here](https://www.ceitec.eu/imglib2-and-bigdataviewer-hackathon-prague/a4679).
  * __When:__ 15/04/2024-23/04/2024
  * __Where:__ Prague, Czech Republic
  * __Supported by:__ [CEITEC](https://www.ceitec.eu) and [CZI](https://chanzuckerberg.com)

* __BioImage Model Zoo Enhancements Hackathon__:
  * __What:__ Working on the rework of the Bioimage.io documentation and other enhancements of the BioImage Model Zoo ([see here](https://ai4life.eurobioimaging.eu/hackathon-summary-bioimage-model-zoo-enhancements/))
  * __When:__ 11/03/2024-15/03/2024
  * __Where:__ [EMBL Heidelberg](https://www.embl.org/sites/heidelberg/), Germany
  * __Supported by:__ [AI4Life](https://ai4life.eurobioimaging.eu)

* __deepImageJ and friends Hackathon__:
  * __What:__ Hackathon on deepImageJ and Fiji plugins
  * __When:__ 15/01/2024-19/01/2024
  * __Where:__ Universidad Carlos III de Madrid, Spain
  * __Supported by:__ [AI4Life](https://ai4life.eurobioimaging.eu)

* __AI4Life Hackathon and Solvathon__:
  * __What:__ [Hackathon and Solvathon of AI4Life](https://ai4life.eurobioimaging.eu/event/ai4life-hackathon-solvathon/)
  * __When:__ 09/10/2023-13/10/2023
  * __Where:__ [EMBL Heidelberg](https://www.embl.org/sites/heidelberg/), Germany
  * __Supported by:__ [AI4Life](https://ai4life.eurobioimaging.eu)

* __Cloud Based and AI Hackathon__:
  * __What:__ [Hackathon on Web and Cloud Infrastructure for AI-Powered BioImage Analysis](https://www.scilifelab.se/event/hackathon-on-cloud-based-and-ai-powered-bioimage-analysis/)
  * __When:__ 05/06/2023-09/06/2023
  * __Where:__ [SciLifeLab](https://www.scilifelab.se), Stockholm, Sweden
  * __Supported by:__ [AI4Life](https://ai4life.eurobioimaging.eu)

* __Accessibility of DL models from Java Hackathon__:
  * __Summary:__ [Deep Learning in Java - AI4Life](https://ai4life.eurobioimaging.eu/hackathon-deep-learning-in-java/)
  * __When:__ 05/02/2023-10/02/2023
  * __Where:__ [Human Technopole](https://humantechnopole.it/en/), Milan, Italy
  * __Supported by:__ [AI4Life](https://ai4life.eurobioimaging.eu)


Conferences and Workshops
====== 
* [Effectively Communicating Bioimage Analysis Workshop](https://www.biologists.com/workshops/february-2024/), East Sussex, UK, _Feb 2024_
* [CASEIB 2023](https://caseib.es/2023/), Cartagena, _Nov 2023_
* [PyConES 2022](https://2022.es.pycon.org), Granada, _Sept-Oct 2022_ 
* [VII Jornadas Nacionales de Investigación en Ciberseguridad](https://2022.jnic.es), Bilbao, _June 2022_
* [Women Techmakers](http://wtmgdgmadrid.github.io/#program), Madrid, _April 2022_
* [VIII Jornades TIC Salut i Social, Tecnologia i humanisme: Teràpies digitals](https://ticsalutsocial.cat/event/8es-jornades-rdi-tic-salut-social/), Vic, _Sept 2018_

Dissertations
======
* __Biopotential Signals and their Applicability to Cybersecurity__, _cum laude_
  * Ph.D. Thesis Dissertation, [Universidad Carlos III de Madrid](https://www.uc3m.es/phdprogram/computer-science-technology), Dec. 2022
  * Under the supervision of [Dr. Pedro Peris-López](https://lightweightcryptography.com) and [Dra. Carmen Cámara](https://researchportal.uc3m.es/display/inv43106)
* __A Novel Biometrics Technique based on Electrocardiomatrix__
  * M.Sc. Thesis Dissertation, [Universidad Carlos III de Madrid](https://www.uc3m.es/master/cybersecurity), 2020, July. 2020
  * Under the supervision of [Dr. Pedro Peris-López](https://lightweightcryptography.com) and [Dra. Carmen Cámara](https://researchportal.uc3m.es/display/inv43106)
* __Event Management and Safety Information__
  * B.Sc. Thesis Dissertation, [Universitat de les Illes Balears](https://www.uib.eu/Learn/estudis-de-grau/grau/telematica/GTTT-P/), July 2019
  * Under the supervision of [Dra. María Francisca Hinarejos Campos](https://www.uib.es/es/personal/ABjExMDM1Nw/)

Certifications
======
* [Academic Teaching Excellence](https://www.uc3m.es/pdi/PDI-Training/Courses/Academic-teaching-excellence#contenido) - British Council
* [Microscopy data analysis: machine learning and the BioImage Archive](https://www.ebi.ac.uk/training/events/microscopy-data-analysis-0/) - EMBL
* [Microscopy and Application Course](https://www.csic.es/es/formacion-y-empleo/cursos-de-alta-especializacion-del-csic/vi-curso-microscopia-y-aplicaciones) - CSIC
* Autopsy Software for Forensic Analysis
* Ethical Hacking
* English Level C1 (MECR)
* French Level A2
* Machine Learning with Python (edX)
* Deep Learning ([UC3M](https://aplicaciones.uc3m.es/cpa/generaFicha?est=359&asig=18056&idioma=2))


Others
======
* Finalist for the [Thesis Talks 2021](https://www.uc3m.es/doctorado/thesis-talk-2021), video available [here](https://media.uc3m.es/video/60d2df8c8f4208a50b8b456d?track_id=60d2e01c8f4208f50b8b4567), _2021_
* Collaborator student maintaining a the University webpage for online courses, _2018_
* Trainee at [Fundació Bit](https://www.fundaciobit.org/es/inicio/), Parc Bit, _May to September 2018_
* Waitress at Restaurant Es Port, Portocolom, _2017_
* Volunteer instructor at the Science Fair at the [UIB](https://seras.uib.cat/ciencia/2016/) , _2016 and 2017_
* Linear Algebra and Discrete Mathematics with honours in the B.Sc. in Telemmatics Engineering, _2016_
* Award-winning for the short-story contest in Setmanari Felanitx, _2016_
* Waitress at [Sa Cova Dets Ases](https://goo.gl/maps/RrAiCwAej4EKAkbh8), Portocolom, _2015 and 2016_

<style>
.section-toggle {
  cursor: pointer;
  margin-bottom: 5px;
}

.section-content {
  display: none;
  margin-bottom: 20px;
}

.toggle-icon {
  margin-left: 5px;
}

.publications-section {
  display: none;
  margin-bottom: 20px;
}

.year-content {
    display: none; /* Hide the content by default */
  }

.category-toggle {
  cursor: pointer;
}
</style>



<script>
document.querySelectorAll('.year-toggle').forEach(function (toggle) {
    toggle.addEventListener('click', function () {
      var content = this.nextElementSibling;
      content.style.display = content.style.display === 'none' ? 'block' : 'none';
      this.querySelector('.toggle-icon').textContent = content.style.display === 'none' ? '+' : '-';
    });
  });

var yearToggles = document.querySelectorAll('.year-toggle');
yearToggles.forEach(function(toggle) {
  toggle.addEventListener('click', function() {
    var publicationsSection = this.nextElementSibling;
    var toggleIcon = this.querySelector('.toggle-icon');
    
    if (publicationsSection.style.display === 'none') {
      publicationsSection.style.display = 'block';
      toggleIcon.innerHTML = '-';
    } else {
      publicationsSection.style.display = 'none';
      toggleIcon.innerHTML = '+';
    }
  });
});
function toggleSection(sectionId) {
  var sectionContent = document.getElementById(sectionId);
  var toggleIcon = document.getElementById("toggle-icon-" + sectionId);
  
  if (sectionContent.style.display === "none") {
    sectionContent.style.display = "block";
    toggleIcon.innerHTML = "-";
  } else {
    sectionContent.style.display = "none";
    toggleIcon.innerHTML = "+";
  }
}
var categoryToggles = document.querySelectorAll('.category-toggle');
categoryToggles.forEach(function(toggle) {
  toggle.addEventListener('click', function() {
    var publicationsSection = this.nextElementSibling;
    var toggleIcon = this.querySelector('.toggle-icon');
    
    if (publicationsSection.style.display === 'none') {
      publicationsSection.style.display = 'block';
      toggleIcon.innerHTML = '-';
    } else {
      publicationsSection.style.display = 'none';
      toggleIcon.innerHTML = '+';
    }
  });
});
</script>

