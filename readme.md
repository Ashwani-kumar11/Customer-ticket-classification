 Task 2 – Entity Extraction from Support Tickets
Extracts products, dates, and complaint keywords/phrases from customer support tickets using predefined lists and NLP for issue analysis.

 Objective
Extract entities (e.g., products, dates, complaints) from tickets like: "My Nexus Pulse Smartwatch is malfunctioning. It stopped working on 10 June 2025. No response from support." in JSON format.

 Components
 1. Data Preparation

Input: Unstructured ticket texts.
Preprocessing: Lowercased for matching.

 2. Entity Extraction

Matches products and complaints from predefined lists.
Uses NLP (spaCy) for NER and complaint term detection.
Extracts dates via regex (DD Month YYYY).
Outputs JSON with products, dates, complaint_keywords.

 3. Entities

Products: Nexus Pulse Smartwatch, Quantum Radiance Camera, Tasty Treasures Blender, Freshly Foundations Vacuum, Critter Creations Pet Feeder, Quantum Radiance Lamp.
Complaints: Single words (e.g., malfunction, defective, late); phrases (e.g., no response, charged twice, setup fails).
Dates: Format like "10 June 2025".
 4. Testing

Tests five tickets covering malfunctions, delivery, payment, account, and installation issues.
Validates JSON output for accuracy.


 Running the System
 1. Install Requirements

Python 3.8+
spaCy and en_core_web_sm model

 2. Test Tickets

Malfunction/Support: Nexus Pulse Smartwatch malfunctioning, stopped working, no response from support on 10 June 2025.Output: Products: ["Nexus Pulse Smartwatch"], Dates: ["10 June 2025"], Complaints: ["malfunction", "stop", "no response", "not working"]
Delivery: Ordered Quantum Radiance Camera, got Tasty Treasures Blender, 12 days late, 15 May 2025.Output: Products: ["Quantum Radiance Camera", "Tasty Treasures Blender"], Dates: ["15 May 2025"], Complaints: ["late", "mixed up", "wrong item"]
Payment/Account: Charged twice for Freshly Foundations Vacuum, can’t log in, showing blocked, 01 July 2025.Output: Products: ["Freshly Foundations Vacuum"], Dates: ["01 July 2025"], Complaints: ["charged twice", "can’t log in", "showing blocked"]
Installation: Critter Creations Pet Feeder setup fails, not working, 20 June 2025.Output: Products: ["Critter Creations Pet Feeder"], Dates: ["20 June 2025"], Complaints: ["setup fails", "not working"]
Multiple Issues: Quantum Radiance Lamp defective, debited incorrectly, no response from support, 05 & 07 June 2025.Output: Products: ["Quantum Radiance Lamp"], Dates: ["05 June 2025", "07 June 2025"], Complaints: ["defective", "stop", "debited incorrectly", "no response", "not working"]


 Dependencies

Python 3.8+
spaCy (en_core_web_sm)

 Notes

Update product/complaint lists for new data.
NER may mislabel products; prioritizes predefined lists.
Optimize NLP for large datasets.
Future: Add complaint frequency analysis, custom NER, or urgency classification.
