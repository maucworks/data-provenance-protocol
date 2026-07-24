# Data Provenance Protocol (DPP)

Open, domein-onafhankelijk protocol voor cryptografisch verifieerbare dataherkomst op internet. Manifest + hashes + handtekening + chaining.
Zelfstandig te verifiëren, zonder platform, server, of terug te gaan naar de bron.

## Aanleiding

Data-uitwisseling via internet mist een generiek protocol voor verifieerbare herkomst. TLS en DNSSEC beveiligen de verbinding, niet het object. DPP voegt de ontbrekende laag toe: persistent proof of origin.

Vijf EU-verordeningen treden in 2026 in werking die provenance vereisen zonder technisch protocol: AI Act, Cyber Resilience Act, Digital Product Passport, Data Act, CSRD.

## Plan

Looptijd: september 2026 – februari 2027 (6 maanden, 26 weken). SIDN Pioniers.

### Fasen

| Fase | Wat | Wanneer |
|------|-----|---------|
| 1. Specificatie v1.0 | Protocol-document: manifest-formaat (JSON), signing (Sigstore/GPG/PKCS#7), verificatiesemantiek, domein-extensie-model, chaining. CC0, als Internet-Draft. | sep–okt 2026 |
| 2. DPP CLI | Python-tool op PyPI (GPLv3+). Vijf commando's: init, add, sign, verify, report. Domein-onafhankelijk. Testdekking ≥80%. | okt–dec 2026 |
| 3. Web verificatie-demo | Statische GitHub Pages-pagina (MIT). Upload manifest + bestanden, verificatie in browser via Web Crypto API. Geen server, geen account. | nov–dec 2026 |
| 4. BIM demonstrator | ifckit integreert DPP-manifest bij IFC-generatie. Workflow: woningtype parametriseren, IFC genereren, DPP-levering met multi-party signing. | nov 2026–jan 2027 |
| 5. GIS demonstrator | onderlegger.mauc.nl integreert DPP collection-manifest. Haalt data uit Kadaster, PDOK, KLIC, DSO en legt per bron vast: URL, tijdstip, response-hash. | nov 2026–jan 2027 |
| 6. Documentatie + afronding | Handleiding, voorbeelden, blogpost. CodeSupply-positioneringsdocument. | jan–feb 2027 |

### Twee modi

| Modus | Wat het bewijst | Wie tekent |
|-------|----------------|------------|
| Server-side | "Deze data komt van bron X" | Dataleverancier |
| Client-side | "Dit is wat ik ontving van bron Y, op T" | Dataverzamelaar |

### Resultaten

1. Specificatie v1.0 (CC0): Internet-Draft, JSON manifest, signing, verificatie, chaining
2. DPP CLI op PyPI (GPLv3+): init, add, sign, verify, report
3. Web verificatie-demo (MIT): GitHub Pages, verificatie in browser
4. BIM demonstrator: ifckit + DPP, multi-party signing
5. GIS demonstrator: onderlegger.mauc.nl + DPP, signed collection-manifest
6. CodeSupply positioneringsdocument

Succescriterium: een derde partij kan zonder uitleg de specificatie lezen, de CLI installeren en een eigen manifest maken voor eigen data, ongeacht domein.
