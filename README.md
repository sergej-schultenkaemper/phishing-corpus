# Multimodal Phishing Ccorpus
The phishing data has been collected from Reddit and reported by Germany's consumer protection organization (Verbraucherzentrale). The dataset contains 2,353 phishing examples, featuring both German and English content.


## Dataset Statistics

### General Statistics
- Total Posts: 2,353
- Total Images: 3,838
- Average Images per Post: 1.63
- Language Distribution:
  - English: 2,042 (86.8%)
  - German: 218 (9.3%)

### Content Analysis
- Images with Redaction: 698 (29.7%)
- Posts with Attacker Information: 942 (40.0%)
- Phishing Posts:
  - Annotated: 1,538 (65.4%)
  - Based on Images: 1,758 (74.7%)
  - Based on Images & Comments: 1,971 (83.8%)
- Average Word Length: 150.49 characters

### Content Distribution
- Messenger: 1,069 (45.4%)
- Email: 628 (26.7%)
- Website: 411 (17.5%)
- Letter: 97 (4.1%)

## Data Structure

Each entry contains:

```json
{
    "id": "string",
    "title": "string",
    "permalink": "string",
    "created_utc": "number",
    "author": "string",
    "images": ["array"],
    "number_of_images": "integer",
    "number_of_comments": "integer",
    "phishing_analysis": {
        "images_content_related": "boolean",
        "is_phishing_based_on_images": "boolean",
        "is_phishing_based_on_comments": "boolean",
        "is_phishing_based_on_images_and_comments": "boolean",
        "confidence": "string"
    },
    "text_extraction_and_analysis": {
        "images_content_related": "boolean",
        "is_redacted": "boolean",
        "language": "string",
        "content_type": "string",
        "extracted_text": "string",
        "phishing_features": ["array"],
        "domain": ["array"],
        "sensitive_information": {
            "attacker_data": {
                "names": ["array"],
                "addresses": ["array"],
                "phone_numbers": ["array"],
                "email_addresses": ["array"]
            }
        }
    },
    "annotation": {
        "phishing_label": "boolean",
        "text_accuracy": "string",
        "was_cancelled": "boolean"
    }
}
