# Web Panel Mockup — Feedback Analysis & Response

**Client:** Cygnet Texkimp  
**Feedback from:** James Pearce  
**Date:** 13 May 2026  
**Prepared by:** Cleverence Team

---

## Summary

James reviewed the first demo version of the customized Cleverence web panel and provided feedback across all major sections. His overall response was positive ("Looks great. Looking much more like what we need for our application."). Below is a point-by-point analysis of each feedback item (starting from item 5, as items 1–4 are general/informational and addressed separately).

---

## Feedback Analysis

| # | Section | James's Feedback | Action | Our Response | Status |
|---|---------|-----------------|--------|--------------|--------|
| 5 | **Stock Overview — All Bobbins** | On selection of a bobbin, display all information including OPC winder data: run length, run time, winder calculated weight, diameter | **Will do — update mockup** | The bobbin detail view currently shows Serial Number, Winder Position, Skid, Weight, Creel Position, and Status. We will add the following OPC-sourced fields to the detail view: **Run Length (m)**, **Run Time**, **Winder Calculated Weight (kg)**, and **Diameter (mm)**. These fields will appear in a dedicated "Winding Data" section within the bobbin detail page. | Ready to implement |
| 6 | **Stock Overview — Winder Positions** | Display latest winder data: run length, run time, winder calculated weight, diameter | **Will do — update mockup** | The Winder Positions tab currently shows Position ID, Status, Current Bobbin, Thread Type, Speed, Last Doff, and Last Doff Time. We will add columns for **Run Length (m)**, **Run Time**, **Winder Calculated Weight (kg)**, and **Diameter (mm)** to show the latest OPC data per position. | Ready to implement |
| 7 | **Stock Overview — Skids** | Only ever 0, 1, or 2 bobbins on a skid. Clicking on a skid should list its bobbins | **Will do — update mockup** | Good clarification on the 0/1/2 constraint — this simplifies the display. We will add a clickable drill-down on each skid row that opens a detail view listing the bobbin(s) currently loaded, with their serial numbers, weights, and winder origin. | Ready to implement |
| 8 | **Stock Overview — Creel Positions** | Add length in metres | **Will do — update mockup** | We will add a **Length (m)** column to the Creel Positions table, showing the winding length of the bobbin loaded at each position. | Ready to implement |
| 9 | **Winder Doffing — Warehouse label** | Rename "Warehouse" to "Winding Hall" | **Will do — update mockup** | Simple text rename. Anywhere the mockup currently says "Warehouse" in the context of Winder Doffing documents, it will be changed to **"Winding Hall"**. | Ready to implement |
| 10 | **Winder Doffing — Expected vs Actual Quantity** | "Expected Quantity" should show winder-calculated weight (kg). Length (m) should be written to Expected Quantity instead of Actual Quantity. Actual Quantity should be empty on the receiving document. Question for Serge: can we use Expected instead of Actual? | **Needs clarification from Serge** | This is a platform-level question about how the Receiving document type handles Expected vs Actual Quantity fields. The mockup can reflect whichever approach is confirmed. **We need Serge to confirm:** can the receiving document be configured so that the scanner app writes to Expected Quantity (with the winder-calculated weight in kg), leaving Actual Quantity empty on creation? Once confirmed, we update the mockup accordingly. | Awaiting Serge |
| 11 | **Skid Loading** | Should show which winder position the bobbin came from | **Will do — update mockup** | We will add a **Winder Position** column to the Skid Loading document list and document detail view. This data comes from the bobbin record created during Winder Doffing (Operation 1) and will be looked up automatically. | Ready to implement |
| 12 | **Weighing** | Could have 2 line items per document because the skid is weighed (gross weight via OPC), then net weight per bobbin is calculated | **Will do — update mockup + needs discussion** | This is a structural change. The current mockup assumes 1 bobbin = 1 document. James is saying the weighing operation weighs the entire skid and then calculates net weight per bobbin. We will update the Weighing document detail to show: (1) **Gross Weight** of the skid, (2) a line for each bobbin on the skid (1 or 2 lines) with its **Calculated Net Weight**. **Discussion point:** the net weight calculation depends on the split method — is it proportional by winding length (as described in the spec), or equal split? The spec says proportional. We will reflect that in the mockup. | Ready to implement |
| 13 | **Put Away** | "Is this Creel loading?" | **Confirmed — no change needed** | Yes, Put Away = Creel Loading. The operation name "Put Away" is standard Cleverence terminology. We can add a subtitle or parenthetical **(Creel Loading)** in the mockup for clarity if James prefers. No functional change. | Done |
| 14 | **Picking, Internal Transfer & Stock Taking** | Not sure what these would be in Cygnet's application, but they may have a purpose | **No change — keep as-is** | These are standard operations kept available for future use. Picking could be used for dispatching bobbins to customers. Internal Transfer for moving stock between areas. Stock Taking for periodic inventory checks. No changes needed in the mockup — they remain available but are not customized. | No action needed |
| 15 | **Write Off** | Good. The reason could be a dropdown choice | **Will do — update mockup** | We will update the Write Off form in the mockup to show the Reason field as a **dropdown** with pre-defined choices (e.g. Damaged, Defective, Expired, Quality Reject, Other). The actual choices are configured in the scanner app, but the web panel form will mirror them. | Ready to implement |

---

## Items Requiring Decisions

| Item | Question | Who Decides | Urgency |
|------|----------|-------------|---------|
| Expected vs Actual Quantity (item 10) | Can the receiving document write to Expected Quantity instead of Actual Quantity? | Serge | Before next mockup iteration |
| Put Away label (item 13) | Does James want "(Creel Loading)" added as a subtitle? | James | Low — cosmetic |
| Weighing net weight split method (item 12) | Proportional by winding length (per spec) or equal split? | James to confirm | Before implementing weighing detail |

---

## Next Steps

1. Implement all "Ready to implement" changes in the mockup (items 5, 6, 7, 8, 9, 11, 12, 15)
2. Send question about Expected vs Actual Quantity to Serge
3. Share updated mockup with James for second round of review
4. Address items 1–4 (General section) in a separate response to James

---

*Cleverence Team — May 2026*
