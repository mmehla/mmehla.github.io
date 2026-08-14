---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Professional Experience
======
* **Assistant Research Scientist**, Texas A&M AgriLife Research, Temple, TX *(Jul 2026 – Present)*
* **Postdoctoral Research Associate**, Texas A&M AgriLife Research, Temple, TX *(Feb 2025 – Jun 2026)*
* **Postdoctoral Research Associate**, Texas Tech University, Lubbock, TX *(Jul 2023 – Jan 2025)*
* **Senior Research Fellow**, ICAR-Central Soil Salinity Research Institute, Karnal, IN *(Jan 2023 – Jun 2023)*
* **Senior Research Fellow**, Maharana Pratap University of Agriculture and Technology, Udaipur, IN *(Aug 2019 – Dec 2022)*

Education
======
* **Ph.D. in Soil and Water Conservation Engineering**, Maharana Pratap University of Agriculture and Technology, Udaipur, IN *(Aug 2019 – Jun 2023)*
  * **Dissertation:** [*Assessment of Water Footprint Sustainability for Major Crops in Banas River Basin*](https://krishikosh.egranth.ac.in/handle/1/5810211653)
* **M.Tech. in Soil and Water Engineering**, Chaudhary Charan Singh Haryana Agricultural University, Hisar, IN *(Aug 2017 – Jul 2019)*
  * **Thesis:** [*Effect of Drip Irrigation Frequency on Onion Yield and Water Productivity*](http://krishikosh.egranth.ac.in/handle/1/5810142413)
* **B.Tech. in Agricultural Engineering**, Chaudhary Charan Singh Haryana Agricultural University, Hisar, IN *(Aug 2013 – Jun 2017)*

Technical Skills
======
* **GIS & Geospatial Software:** ArcMap, ArcGIS Pro, QGIS, Surfer
* **Hydrological & Crop Modeling:** SWAT, SWAT+, AquaCrop, CropWAT
* **Programming & Analytics:** Python, R, MATLAB, SPSS
* **Computer-Aided Design (CAD):** AutoCAD, SolidWorks, SketchUp

Licenses & Certifications
======
* **Remote Pilot Certificate (Part 107)**, Federal Aviation Administration (FAA), USA *(2023)*

Academic Service & Editorial Roles
======
* **Associate Editor**, *Agrosystems, Geosciences & Environment* (AGE) Journal *(Aug 2024 – Dec 2026)*

Professional Memberships
======
* Member, American Geophysical Union (AGU)
* Member, Sigma Xi The Scientific Research Honor Society
* Member, Crop Science Society of America (CSSA)
* Member, Association of Agricultural Scientists of Indian Origin (AASIO)
* Life Member, Indian Society of Agricultural Engineers (ISAE) *(LM-12661)*
* Life Member, Society for Community Mobilization for Sustainable Development *(LM-1860)*

Publications
======
<div id="orcid-cv-publications">
  <p><i>Loading latest publications directly from ORCID...</i></p>
</div>

{% raw %}
<script>
  document.addEventListener("DOMContentLoaded", function() {
    const orcidId = "0000-0003-0948-4876";
    const container = document.getElementById("orcid-cv-publications");

    fetch("https://pub.orcid.org/v3.0/" + orcidId + "/works", {
      headers: { "Accept": "application/json" }
    })
    .then(function(response) {
      if (!response.ok) throw new Error("Network error");
      return response.json();
    })
    .then(function(data) {
      if (!data || !data.group || data.group.length === 0) {
        container.innerHTML = "<p>No publications found.</p>";
        return;
      }

      let html = "<ul style='list-style-type: none; padding-left: 0;'>";
      
      data.group.forEach(function(group) {
        if (!group["work-summary"] || group["work-summary"].length === 0) return;
        const summary = group["work-summary"][0];

        let title = (summary.title && summary.title.title && summary.title.title.value) ? summary.title.title.value : "Untitled";
        let year = (summary["publication-date"] && summary["publication-date"].year) ? summary["publication-date"].year.value : "";
        let journal = (summary["journal-title"] && summary["journal-title"].value) ? summary["journal-title"].value : "";

        let link = summary.url ? summary.url.value : "";
        if (!link && summary["external-ids"] && summary["external-ids"]["external-id"]) {
          const ids = summary["external-ids"]["external-id"];
          for (let i = 0; i < ids.length; i++) {
            if (ids[i]["external-id-type"] === "doi" && ids[i]["external-id-value"]) {
              link = "https://doi.org/" + ids[i]["external-id-value"];
              break;
            }
          }
        }

        html += "<li style='margin-bottom: 18px; padding: 14px 18px; border-left: 4px solid #0073e6; background-color: #f8f9fa;'>";
        html += "<strong style='font-size: 1.05em;'>" + title + "</strong>";
        if (year) html += " (" + year + ")";
        if (journal) html += "<br><span style='color: #555;'><em>" + journal + "</em></span>";
        if (link) html += "<br><a href='" + link + "' target='_blank' style='display: inline-block; margin-top: 6px; font-size: 0.9em; font-weight: bold;'>[View Paper / DOI]</a>";
        html += "</li>";
      });

      html += "</ul>";
      container.innerHTML = html;
    })
    .catch(function(error) {
      container.innerHTML = "<p>Unable to automatically fetch publications. View full publication record on <a href='https://orcid.org/0000-0003-0948-4876' target='_blank'>ORCID</a>.</p>";
    });
  });
</script>
{% endraw %}

Talks & Presentations
======
<ul style="list-style-type: none; padding-left: 0;">
{% for post in site.talks reversed %}
  <li style="margin-bottom: 18px; padding: 14px 18px; border-left: 4px solid #0073e6; background-color: #f8f9fa;">
    <strong style="font-size: 1.05em;">{{ post.title }}</strong>
    {% if post.date %}
      ({{ post.date | date: "%Y" }})
    {% endif %}
    {% if post.venue %}
      <br><span style="color: #555;"><em>{{ post.venue }}</em></span>
    {% endif %}
    {% if post.location %}
      <span> &bull; {{ post.location }}</span>
    {% endif %}
    {% if post.type %}
      <br><span style="display: inline-block; margin-top: 6px; font-size: 0.85em; font-weight: bold; color: #0073e6;">{{ post.type }}</span>
    {% endif %}
  </li>
{% endfor %}
</ul>
