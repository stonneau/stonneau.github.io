---
layout: page
permalink: /publications/
title: publications
description: Publications in reverse chronological order. A selection of PDFs is hosted here; the rest link to HAL, arXiv or the publisher.
nav: true
nav_order: 3
---

<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="pub-type-filter" role="group" aria-label="Filter publications by type">
  <label><input type="checkbox" data-pub-type="conference" checked> conferences</label>
  <label><input type="checkbox" data-pub-type="journal" checked> journal</label>
  <label><input type="checkbox" data-pub-type="other" checked> other</label>
</div>

<script>
  // The three tick boxes work together with the text filter above (bibsearch.js): an entry is shown
  // only if its type is ticked AND it matches the text. The type comes from the hidden BibTeX block
  // of each entry (@article = journal, @inproceedings/@incollection = conference, anything else,
  // plus arXiv preprints and editorials = other).
  (function () {
    function pubType(li) {
      var block = li.querySelector(".bibtex.hidden");
      var t = block ? block.textContent.replace(/\s+/g, " ") : "";
      var m = t.match(/@(\w+)\s*\{/);
      var kind = m ? m[1].toLowerCase() : "";
      if (/journal\s*=\s*\{arXiv/i.test(t) || /title\s*=\s*\{Editorial/i.test(t)) return "other";
      if (kind === "article") return "journal";
      if (["inproceedings", "incollection", "inbook", "conference", "proceedings"].indexOf(kind) !== -1) return "conference";
      return "other";
    }

    function apply() {
      var shown = {};
      document.querySelectorAll("input[data-pub-type]").forEach(function (box) {
        shown[box.getAttribute("data-pub-type")] = box.checked;
      });
      document.querySelectorAll("ol.bibliography > li").forEach(function (li) {
        li.classList.toggle("pub-type-hidden", !shown[li.dataset.pubType]);
      });
      // hide a year heading (and its list) when nothing is left under it, whichever filter hid the entries
      document.querySelectorAll("h2.bibliography").forEach(function (h2) {
        var ol = h2.nextElementSibling;
        while (ol && ol.tagName !== "OL" && ol.tagName !== "H2") ol = ol.nextElementSibling;
        if (!ol || ol.tagName !== "OL") return;
        var visible = ol.querySelectorAll(":scope > li:not(.pub-type-hidden):not(.unloaded)").length;
        h2.classList.toggle("pub-type-hidden", visible === 0);
        ol.classList.toggle("pub-type-hidden", visible === 0);
      });
    }

    document.addEventListener("DOMContentLoaded", function () {
      document.querySelectorAll("ol.bibliography > li").forEach(function (li) {
        li.dataset.pubType = pubType(li);
      });
      document.querySelectorAll("input[data-pub-type]").forEach(function (box) {
        box.addEventListener("change", apply);
      });
      // bibsearch.js recomputes its own hiding on every keystroke and on hash changes; run after it
      var search = document.getElementById("bibsearch");
      if (search) search.addEventListener("input", function () { setTimeout(apply, 0); });
      window.addEventListener("hashchange", function () { setTimeout(apply, 0); });
      setTimeout(apply, 0);
    });
  })();
</script>

<div class="publications">

{% bibliography %}

</div>
