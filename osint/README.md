# OSINT — Open Source Intelligence

Finding, aggregating, and analyzing publicly available information. AI dramatically accelerates every phase.

---

## Phases

1. **Collection** — Gathering raw data from public sources
2. **Processing** — Cleaning, normalizing, deduplicating
3. **Analysis** — Finding patterns, connections, meaning
4. **Dissemination** — Presenting the picture

AI assists most at phases 2 and 3 — the parts that used to take humans hours.

---

## Target Types

### Person OSINT
- Social media footprint
- Professional history (LinkedIn, company sites)
- Public records (court filings, property records, voter rolls)
- Contact information
- Associates and relationships
- Location patterns

### Organization OSINT
- Domain and subdomain enumeration
- Employee enumeration
- Technology stack (Shodan, Wappalyzer, job postings)
- Financial filings
- Physical locations
- Suppliers and partners

### Technical OSINT
- IP ranges and ASN mapping
- Certificate transparency logs
- GitHub / code repository leaks
- Paste site monitoring
- Dark web mentions

---

## AI Augmentation

### Entity extraction at scale
```python
# Feed large documents to LLM, extract structured entities
prompt = """
From the following text, extract all:
- Person names and their roles
- Organizations mentioned
- Locations
- Dates and events
- Email addresses and phone numbers

Return as JSON.

Text: {document}
"""
```

### Relationship mapping
```python
prompt = """
Based on these data points about [target], identify:
1. Known associates and relationships
2. Likely locations at different times
3. Professional timeline
4. Interests and hobbies
5. Potential vulnerabilities for social engineering

Data: {osint_data}
"""
```

### Pattern recognition
```python
prompt = """
Analyze these social media posts from [target] and identify:
- Daily schedule patterns
- Recurring locations
- Relationships
- Current emotional state
- Topics of concern

Posts: {posts}
"""
```

---

## Tools

| Tool | Purpose |
|------|---------|
| Maltego | Graph-based OSINT and link analysis |
| Shodan | Internet-facing device search |
| theHarvester | Email, subdomain, hostname collection |
| Recon-ng | Web reconnaissance framework |
| SpiderFoot | Automated OSINT collection |
| OSINT Framework | curated resource directory |
| Censys | Internet-wide scanning and search |
