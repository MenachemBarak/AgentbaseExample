# Rental Counter (Subteam)

The **Rental Counter** is the customer-facing front desk of the **Metro Airport
Branch**, part of the Airport Branches Group in West Region Operations at
DriveEasy Car Rental. It is the human face of the company: the place where a
confirmed reservation becomes a customer driving off the lot.

## Overview
The Rental Counter staffs the terminal-side desk where arriving customers — many
stepping off the airport shuttle — are checked in and out. The subteam owns the
**pickup** moment of the rental lifecycle (reserve -> pickup -> in-use -> return
-> invoice) and the first-line handoff back at return. It is the leaf of the org
hierarchy: a small, tightly-run shift crew with no subteams beneath it.

## How it works
- Customers arrive with a booking; the counter pulls the reservation from the
  **booking system** on the counter terminals.
- Associates verify driver's license and payment, confirm the vehicle class
  (economy, compact, SUV, luxury, van), and offer upgrades, extras, and
  protection priced by the **pricing engine**.
- Keys and the rental agreement are issued; the customer is directed to a staged
  vehicle (readied by the Vehicle Prep subteam) or, at drop-off, passed to
  Returns & Inspection.
- Long support chats and customer rental history reach the desk already
  compressed and deduped via **headroom**, so the team sees one clean history per
  customer instead of re-fetching transcripts.
- Shifts run on a published rota; the Counter Team Lead opens, balances queues,
  and closes the till.

## Purpose & goals
- Turn every reservation into a fast, friendly, error-free pickup.
- Keep counter wait times low even at peak flight-arrival waves.
- Capture accurate license, payment, and vehicle data so the downstream return
  and invoicing stages close without dispute.
- Hand off smoothly to Vehicle Prep and Returns & Inspection.

This subteam is a leaf — it contains roles (Counter Team Lead and Rental Counter
Associate), not further subteams. See `roles.md`.
