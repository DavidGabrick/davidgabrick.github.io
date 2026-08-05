# PDF portfolio build

`portfolio-print.html` is the print-only source for
`../David-Gabrick-Engineering-Portfolio.pdf`. It is not linked from the site.

Regenerate (requires WeasyPrint + pypdf):

    pip install weasyprint pypdf
    weasyprint -u "file://$(cd .. && pwd)/" --optimize-images -j 88 -D 200 \
      portfolio-print.html body.pdf

Then merge the two engineering reports in as appendices: body pages 1-14,
then assets/docs/turret-tracker/ATT-01-case-study.pdf (9 pp),
then body page 15, then assets/docs/mechanical-crane/white-crane-design-report.pdf (10 pp).

If the body page count changes, update the two `data-page` values in the
Contents list (Appendix A / Appendix B) to match.
