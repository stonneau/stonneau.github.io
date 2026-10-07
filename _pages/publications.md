---
layout: page
permalink: /publications/
title: Publications
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

<p class="pub-status" id="pub-status" aria-live="polite"></p>

<script>
  // Filter of the publications page. The theme's own text filter (bibsearch.js) only matches the exact
  // lowercase text, accents included, inside one text node. This script takes it over so that:
  //   - accents, case and hyphens do not matter ("corberes" finds "Corbères", "multi contact" finds "multi-contact");
  //   - several words can be typed, in any order ("thomas corbères");
  //   - the three tick boxes (conferences / journal / other) combine with the text;
  //   - the current state is always visible: "Showing 7 of 45 publications", with a reset link.
  // The type of an entry comes from its BibTeX entry type (@article = journal, @inproceedings and
  // @incollection = conference), arXiv preprints and editorials count as "other".
  (function () {
    var items = [];
    var input, boxes, status;

    function norm(s) {
      return s.normalize("NFD").replace(/[\u0300-\u036f]/g, "").toLowerCase()
        .replace(/ł/g, "l").replace(/ø/g, "o").replace(/ß/g, "ss")
        .replace(/[^a-z0-9]+/g, " ").trim();
    }

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

    function collect() {
      var year = "";
      document.querySelectorAll(".publications h2.bibliography, .publications ol.bibliography").forEach(function (node) {
        if (node.tagName === "H2") { year = node.textContent; return; }
        node.querySelectorAll(":scope > li").forEach(function (li) {
          var parts = [year];
          ["abbr", ".title", ".author", ".periodical"].forEach(function (sel) {
            li.querySelectorAll(sel).forEach(function (e) { parts.push(e.textContent); });
          });
          items.push({ li: li, text: norm(parts.join(" ")), type: pubType(li) });
        });
      });
    }

    function fromHash() {
      var h = "";
      try { h = decodeURIComponent(window.location.hash.substring(1)); } catch (e) { h = window.location.hash.substring(1); }
      input.value = h;
    }

    function refresh() {
      var tokens = norm(input.value).split(" ").filter(Boolean);
      var shown = {};
      boxes.forEach(function (b) { shown[b.getAttribute("data-pub-type")] = b.checked; });
      var count = 0;
      items.forEach(function (it) {
        var okText = tokens.every(function (t) { return it.text.indexOf(t) !== -1; });
        var okType = !!shown[it.type];
        it.li.classList.toggle("unloaded", !okText);
        it.li.classList.toggle("pub-type-hidden", !okType);
        if (okText && okType) count++;
      });
      // year headings and their lists: hidden when nothing is left under them
      document.querySelectorAll(".publications h2.bibliography, .publications ol.bibliography").forEach(function (e) { e.classList.remove("unloaded"); });
      document.querySelectorAll(".publications h2.bibliography").forEach(function (h2) {
        var ol = h2.nextElementSibling;
        while (ol && ol.tagName !== "OL" && ol.tagName !== "H2") ol = ol.nextElementSibling;
        if (!ol || ol.tagName !== "OL") return;
        var visible = ol.querySelectorAll(":scope > li:not(.unloaded):not(.pub-type-hidden)").length;
        h2.classList.toggle("pub-type-hidden", visible === 0);
        ol.classList.toggle("pub-type-hidden", visible === 0);
      });
      // the theme's highlight of the previous search term would stay on screen otherwise
      if (window.CSS && CSS.highlights) CSS.highlights.delete("search");
      var filtered = tokens.length > 0 || boxes.some(function (b) { return !b.checked; });
      status.textContent = "";
      if (filtered) {
        status.appendChild(document.createTextNode("Showing " + count + " of " + items.length + " publications. "));
        var reset = document.createElement("button");
        reset.type = "button";
        reset.textContent = "Reset filters";
        reset.addEventListener("click", function () {
          input.value = "";
          boxes.forEach(function (b) { b.checked = true; });
          if (window.location.hash) history.replaceState(null, "", window.location.pathname + window.location.search);
          refresh();
          input.focus();
        });
        status.appendChild(reset);
      } else {
        status.textContent = items.length + " publications";
      }
    }

    // registered while the page is parsed, so before the theme's own listeners: they are not run
    document.addEventListener("input", function (e) {
      if (e.target && e.target.id === "bibsearch") { e.stopImmediatePropagation(); refresh(); }
    }, true);
    window.addEventListener("hashchange", function (e) { e.stopImmediatePropagation(); fromHash(); refresh(); }, true);

    document.addEventListener("DOMContentLoaded", function () {
      input = document.getElementById("bibsearch");
      status = document.getElementById("pub-status");
      boxes = Array.prototype.slice.call(document.querySelectorAll("input[data-pub-type]"));
      if (!input) return;
      collect();
      boxes.forEach(function (b) { b.addEventListener("change", refresh); });
      // the theme applies its own filter once on load (from the #hash): run after it
      setTimeout(function () { fromHash(); refresh(); }, 0);
    });
  })();
</script>

<div class="publications">

{% bibliography %}

</div>
