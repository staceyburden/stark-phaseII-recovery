# Stark Aerospace — R95 Technical Candidate Change Log

**TEST CANDIDATE ONLY — NOT AN APPROVED PRODUCTION MASTER.**

Date: 2026-11-06. Scope: only the nine authorized R94 technical defects. D1, D2 and D3 remain pending; R94-V1 formulas are unchanged.

## Source and preservation controls

- Source: `/workspace/attachments/b52490b9-18fe-4022-801c-433ebe3e9317/Stark_R94_Completed_Protected_Master.xlsx`.
- Audited and verified source SHA-256: `0599606e59875c4e4fb50d03508a4e9774c46960a75e5482f00c35c5386dbaa6`.
- Exact source hash matched before changes and after all corrections/tests. A mismatch would stop the build; no mismatch occurred.
- Candidate: `/workspace/work/final_r95/Stark_R95_TEST.xlsx`.
- Final candidate SHA-256: `aa467dbbeef4a234848b2dc2b0dc3a6a3dd2bed3851b9e27b51a025b474d2271`.
- Retained three original sheets, 37 question texts, all 504 formula locations, 12 charts, existing styles, input data and protections. No worksheets were added, removed, renamed or reorganized.
- Exactly **38 formula texts changed**: Company E10:E29 (20), Stark E10:E26 (17), Dashboard A5 (1). All other **466 formulas are identical** to R94. No formula was added or removed.
- No assessment risk-counting, action-closure, question, exposure/confidence governance or completion-policy change was made. INVALID / INVALID INPUT are input-error diagnostics, not a new scored risk classification.

## Controlled technical changes

| Audit issue | Affected cells / parts | Exact modification | Reason | Executed test result / limitation |
|---|---|---|---|---|
| R94-01 | All nine original list validations on three sheets | Set showErrorMessage=1 and errorStyle=stop; add explanatory error title/text. Preserve all original choices and blank settings. | Enable existing dropdown blocking on direct invalid entry. | PASS: all nine definitions verified. Live Excel typing/paste enforcement NOT VERIFIED. |
| R94-01 | 02 COMPANY E10:E29; 03 STARK E10:E26 | Require explicit N/A match; unmatched nonblank values and input errors return INVALID, with IFERROR guard. Replace shared formulas only at these existing formula locations with equivalent explicit row formulas. | Stop malformed values silently becoming valid N/A. | PASS: 222 invalid-value cases, plus 185 valid/blank classification cases. |
| R94-01 | 01 DASHBOARD A5 and A5:D5 CF | Wrap unchanged original banner formula with COUNTIF on the two E ranges: any INVALID returns INVALID INPUT. Extend existing RED banner rule to this diagnostic. | Prevent malformed classifications producing a valid-looking GREEN/AMBER/RED assessment banner. | PASS: all 37 rows and six malformed values each produce diagnostic banner. Valid/blank scenario behavior unchanged. |
| R94-01 | Assessment D10:E29 / D10:E26 | Add priority1 invalid-classification font warning using the existing warning differential style. | Make invalid input visible at its source. | PASS: predicate checks; rendered native Excel appearance NOT VERIFIED. |
| R94-02 | chart6.xml, chart8.xml, chart10.xml, chart12.xml; Company/Stark charts2/4 | Remove only numeric value-axis max elements (12 for identified; 5 for overdue), allowing automatic upper bounds. Keep all series, sources, colors, titles, legends, labels, anchors and other axis properties. | Accommodate full 20/17-question populations. | PASS: 60 chart/scenario source-capacity checks; all12 chart definitions preserved except these bounds and authorized refreshed caches. |
| R94-03 | Dashboard A41:P64; N41:N64 | Copy existing odd/even row39/40 style IDs, row height/custom-height metadata, alignment, wrapping, borders, fonts/fills and date number formats. Add B:C, D:F, H:K, L:M and O:P merges on each row (120 merges). | Complete the existing 37-record priority presentation. | PASS: styles/date formats/row heights and all120 added non-overlapping merges verified; all existing formulas retained. Native render/print NOT VERIFIED. |
| R94-04 | Company D10:D29; Stark D10:D26 | Give existing contradiction rule priority3, ahead of classification fonts. Retain relative order among other original active rules while making priority values unique. | Ensure Clear/N/A plus Blocked warning wins the conflicting font property. | PASS: all four explicit conflict cases,740 classification transitions and740 progress-status transitions at predicate level. Native displayed colors NOT VERIFIED. |
| R94-05 | Company I10:I29; Stark I10:I26 | Add two date validations: serials1–2958465, Stop alert, allowBlank=1, explanatory input/error prompts. | Restrict direct input to Excel's supported positive date range while preserving optional dates. | PASS: definitions and input coverage verified; live Excel validation and paste bypass NOT VERIFIED. |
| R94-05 | Same target-date ranges | Add priority2 invalid-date warning: IFERROR(AND(I<>"",OR(NOT(ISNUMBER(I)),I<=0,I>2958465)),TRUE). Reuse existing warning font. | Explicitly flag populated text, zero/negative, out-of-range and error dates. | PASS: 296 date cases across all37 questions. Text-date overdue counting remains native-unverified under R94-V1. |
| R94-05 | Same ranges, existing overdue CF | Add I>0 to the existing numeric overdue warning; retain Critical/High, ISNUMBER, I<TODAY and not Verified Closed tests. Do not alter overdue COUNTIFS or target fallback formulas. | Align zero-date warnings with existing positive-date overdue counting. | PASS: zero gets invalid warning only, and contributes0 overdue; past/today/future/missing cases reconcile. |
| R94-06 | J7 and E10:E29/E10:E26 CF on two assessment sheets | Remove exactly four obsolete rules: two J7>0 and two E=UNKNOWN rules. | J7 has no formula/value; E never emitted UNKNOWN. Neither rule feeds any formula or chart. | PASS: unreachable/disconnected state verified before removal; no obsolete rule remains. Total rules remain42 after four new technical diagnostic rules. |
| R94-07 | workbook.xml calcPr | Set calcMode=auto, fullCalcOnLoad=1, forceFullCalc=1 and calcOnSave=1; retain calcId. | Request full recalculation on subsequent open/save. | PASS: all four settings verified. Native Excel execution NOT VERIFIED. |
| R94-07 | All504 formula cached results; numeric/string chart caches | Recalculate and save a separate scratch copy with LibreOfficeDev26.8; compare all504 baseline values to formulas1.3.4; transplant only verified cached values/types and76 chart cached points into original candidate XML. | Refresh saved audit-date caches without taking a whole-workbook LibreOffice rewrite or changing chart designs. | PASS: engines agree on all504 baseline outputs; final saved candidate caches verified against the saved engine copy. This is compatible-engine evidence, not native Excel certification. |
| R94-08 | 03 STARK local Print_Area name | Extend '03 STARK'!$A$1:$K$26 to '03 STARK'!$A$1:$K$28. | Include the existing scoring guide. | PASS: name/range verified; native pagination/print preview NOT VERIFIED. |
| R94-09 | Dashboard Recovery Plan Required validation | Change sqref M10:R10 to M10:P10, matching the existing intended merged input. | Remove excess validation on locked Q10:R10. | PASS: exact range verified. |

## Exact formula modifications

Company E10 before (same row-relative pattern across all37 questions):

```excel
=IF(D10="","",IF(D10="Critical","Critical",IF(D10="High","High",IF(D10="Clear","Clear","N/A"))))
```

Company E10 after (translated row-relative in each existing E cell):

```excel
=IFERROR(IF(D10="","",IF(D10="Critical","Critical",IF(D10="High","High",IF(D10="Clear","Clear",IF(D10="N/A","N/A","INVALID"))))),"INVALID")
```

Dashboard A5 before:

```excel
=IF(COUNTA('02 COMPANY'!D10:D29)+COUNTA('03 STARK'!D10:D26)=0,"NOT ASSESSED",IF(OR($E$5="Confirmed Interruption",$AA$70+$AA$71>0),"RED",IF(OR($E$5="Potential Interruption",$AA$72>0),"AMBER","GREEN")))
```

Dashboard A5 after:

```excel
=IF(COUNTIF('02 COMPANY'!E10:E29,"INVALID")+COUNTIF('03 STARK'!E10:E26,"INVALID")>0,"INVALID INPUT",IF(COUNTA('02 COMPANY'!D10:D29)+COUNTA('03 STARK'!D10:D26)=0,"NOT ASSESSED",IF(OR($E$5="Confirmed Interruption",$AA$70+$AA$71>0),"RED",IF(OR($E$5="Potential Interruption",$AA$72>0),"AMBER","GREEN"))))
```

All37 G action recommendation formulas, all37 L owner fallbacks, all37 N date fallbacks, all37 O progress fallbacks, ranking helpers and risk/closure/overdue counting formulas remain unchanged. In particular no L/O change was made based on third-party blank coercion.

## Preservation and verification evidence

The final package has the same35 ZIP members. Only workbook.xml, three worksheet parts and12 chart parts differ:16 changed parts,19 byte-identical parts. For charts, direct canonical comparison proves all non-cache content is unchanged after allowing only the four specified numeric-axis max removals. styles.xml, sharedStrings.xml, drawings/anchors, relationship files, calculation chain and all other package members are byte-identical. The source workbook retains its original hash.

Final validation record counts: 3232 total; 3216 PASS; 0 FAIL; 3 DECISION REQUIRED; 13 NOT VERIFIED. These are method-scoped test records, not native Excel certifications. Detailed evidence: `/workspace/work/r95/Stark_R95_Validation_Evidence.csv`.

## Deferred controls

- **R94-D1:** partial assessment/all-N/A completion and GREEN policy pending; unchanged.
- **R94-D2:** reassessment versus verified closure/evidence policy pending; unchanged.
- **R94-D3:** manual executive indicator governance and dynamic leadership-summary expectations pending; unchanged.
- **R94-V1:** native Excel blank owner/progress and stored-text-date COUNTIFS behavior still NOT VERIFIED. Independent compatible-engine probes were performed and are recorded in the validation report; they do not replace native confirmation.

## Delivery and release status

This is **Stark_R95_TEST.xlsx**, a technical working candidate only. It has not been promoted or declared production-ready. Approval of this candidate does not resolve D1–D3 or waive native Excel verification.

The three deliverables exist and can be opened/read in this execution workspace at `/workspace/work/final_r95`. Designated download-directory check: `OSError: [Errno 30] Read-only file system: '/codex'`. Workspace paths are not claimed to be downloadable attachments.
