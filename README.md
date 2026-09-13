# Awesome Room Acoustics

A curated list of open data, calculators, standards, software and learning resources for room acoustics and sound absorption. Made for acousticians, architects, engineers and students who need measured numbers instead of brochure claims.

Criteria for inclusion: freely accessible, based on measured or normative content, and useful in daily planning work. Pull requests welcome, see [Contributing](#contributing).

## Contents

- [Measured material data](#measured-material-data)
- [Calculators and tools](#calculators-and-tools)
- [Standards and regulations](#standards-and-regulations)
- [Simulation software](#simulation-software)
- [APIs and machine-readable data](#apis-and-machine-readable-data)
- [Open-source projects on GitHub](#open-source-projects-on-github)
- [Learning](#learning)
- [Contributing](#contributing)

## Measured material data

- [Acoustic Index](https://acousticindex.com) - Independent database of measured acoustic material data. As of September 2026 it lists 2,004 published products with 4,373 ISO 354 absorption measurements (frequency-resolved αs plus the weighted αw and absorption class to ISO 11654), building acoustics values (Rw, Ln,w, Dn,f,w, DLR) and the complete PTB reference materials. Every value is labelled with its source: accredited test report, manufacturer datasheet or PTB reference measurement. Free to search without an account, available in German, English, Italian and French, with CSV export, a Read API and an MCP server. The best starting point when you need real measured curves across manufacturers and mounting types. What the database contains and where the values come from: [Sound absorption coefficient database](https://acousticindex.com/en/sound-absorption-coefficient-database).
- [PTB sound absorption table (abstab)](https://www.ptb.de) - The historical table of measured absorption coefficients compiled by the Physikalisch-Technische Bundesanstalt, Germany's national metrology institute. PTB no longer maintains it; the records live on in Acoustic Index with search, frequency curves and the original build-up notes.
- [ODEON material library](https://odeon.dk) - Absorption data shipped with the ODEON room acoustics software, including material libraries submitted by manufacturers.
- Manufacturer test reports - Larger manufacturers (Ecophon, Rockfon, Knauf, Lindner, Fural and others) publish ISO 354 reports per product. Always read the mounting type (type A direct mounting versus type E with an air cavity) before comparing two αw values.

## Calculators and tools

- [Reverberation time calculator](https://acousticindex.com/en/reverberation-calculator) - RT60 per Sabine and Eyring with target ranges from 26 regulations across 15 countries (DIN 18041, SS 25268, the French Arrêté of 25 April 2003 and NF S 31-080, ANSI/ASA S12.60 and more), pulls measured products straight from the Acoustic Index database and auralises the result. Free, no account needed.
- [Sound absorption classes A to E](https://acousticindex.com/en/sound-absorption-classes) - Table of the αw limits per class with an interactive mapper from αw to class.
- [misuka](https://github.com/misuka-renderer/misuka) - Differentiable room acoustic renderer from TU Berlin (Audio Communication Group and Computer Graphics Group), built on Mitsuba 3. Simulates sound propagation in a 3D scene and lets you optimise material parameters against a target, open source.
- [misuka-blender](https://github.com/misuka-renderer/misuka-blender) - Blender add-on for misuka. Materials can be searched and assigned straight from the Acoustic Index database through its Read API, so the simulation runs on measured ISO 354 curves instead of guessed coefficients.
- [Sengpielaudio](https://sengpielaudio.com/calculator-RT60.htm) - Classic single-purpose calculators for the Sabine formula and related quantities.
- [Engineering ToolBox absorption coefficients](https://www.engineeringtoolbox.com/accoustic-sound-absorption-d_68.html) - Textbook values for generic surfaces such as concrete, glass, carpet. Useful for base surfaces, not for products.

## Standards and regulations

- ISO 354 - Measurement of sound absorption in a reverberation room. Plain-language explainer with specimen size, mounting types and what a test report must contain: [Reverberation room measurement to ISO 354](https://acousticindex.com/en/reverberation-room-measurement).
- ISO 11654 - Weighted sound absorption coefficient αw and classes A to E. Explainer: [Sound absorption coefficient αw: what counts as a good value?](https://acousticindex.com/en/sound-absorption-coefficient).
- ASTM C423 - Reverberation room method used in North America, yields NRC and SAA. NRC and αw are not directly convertible.
- ISO 10140, ISO 10848, EN 1793 - Airborne and impact sound insulation of building elements, flanking transmission, noise barriers. Overview with measured components: [Building acoustics](https://acousticindex.com/en/building-acoustics).
- DIN 18041 - Reverberation time targets for rooms in Germany, by use and volume.
- SS 25268:2023 - Swedish requirements for reverberation time in schools and offices.
- Arrêté du 25 avril 2003 and NF S 31-080 - French requirements for education, health and office buildings.
- ANSI/ASA S12.60 - Classroom acoustics in the United States.
- BB93 - Acoustic design of schools in the United Kingdom.

## Simulation software

- [ODEON](https://odeon.dk) - Geometrical room acoustics, ray tracing and auralisation, Denmark.
- [CATT-Acoustic](https://www.catt.se) - Room acoustics prediction and auralisation, Sweden.
- [EASE](https://www.afmg.eu) - Electro-acoustic and room acoustics simulation by AFMG, Germany.
- [Treble](https://www.treble.tech) - Wave-based and hybrid simulation in the cloud, Iceland.
- [Pachyderm Acoustic](https://github.com/PachydermAcoustic/PachydermAcoustic_Rhinoceros) - Open-source geometrical acoustics plug-in for Rhinoceros, with a [Grasshopper extension](https://github.com/PachydermAcoustic/PachydermAcoustic_Grasshopper).
- [I-Simpa](https://i-simpa.ifsttar.fr) - Open-source room acoustics simulation platform.

## Open-source projects on GitHub

Libraries and engines that are worth knowing when you work with room acoustics in code. None of them ships measured product data; pair them with a database from the first section.

- [pyroomacoustics](https://github.com/LCAV/pyroomacoustics) - Python package for room impulse response simulation (image source method and ray tracing), beamforming and source separation, from EPFL's LCAV. The standard tool for quick shoebox and polyhedral room experiments.
- [misuka](https://github.com/misuka-renderer/misuka) - Differentiable room acoustic renderer from TU Berlin, built on Mitsuba 3; optimises material parameters against a target and has a Blender add-on.
- [pyfar](https://github.com/pyfar/pyfar) - Python package for acoustics research: signals, filters, room and free-field data handling, plotting. Grown out of the TU Berlin and RWTH acoustics groups.
- [python-acoustics](https://github.com/python-acoustics/python-acoustics) - Library for acousticians: octave bands, weighting, room acoustics parameters per ISO 3382, atmospheric absorption.
- [gpuRIR](https://github.com/DavidDiazGuerra/gpuRIR) - Room impulse response simulation with GPU acceleration, useful when you need thousands of RIRs for machine learning.
- [RIR-Generator](https://github.com/ehabets/RIR-Generator) - The classic MATLAB image method implementation by Emanuel Habets, still the reference many papers cite.
- [openPSTD](https://github.com/openPSTD/openPSTD) - Open-source pseudo-spectral time-domain solver with a visual interface for wave-based room acoustics.
- [Steam Audio](https://github.com/ValveSoftware/steam-audio) - Valve's spatial audio SDK for games with physics-based occlusion, reflections and reverb; open source.
- [Resonance Audio](https://github.com/resonance-audio/resonance-audio) - Google's spatial audio SDK with ambisonic rendering and room effects; open source.

## APIs and machine-readable data

- [Acoustic Index Read API](https://acousticindex.com/api) - REST API for searching materials and loading product details with frequency-band absorption data. [OpenAPI spec](https://acousticindex.com/api/v1/openapi.json), example clients in Node.js and Python: [acousticindex-api-example](https://github.com/kekvult/acousticindex-api-example).
- Acoustic Index MCP server - `https://acousticindex.com/api/mcp/v1`, lets Claude, ChatGPT and other MCP clients look up measured αw values instead of guessing them.

## Learning

- [BauNetz Wissen Akustik](https://www.baunetzwissen.de/akustik) - German reference on building and room acoustics for architects.
- [Acoustic Index guides](https://acousticindex.com/en/guides) - Short explainers with sources, for example [Basotect vs stone wool](https://acousticindex.com/en/basotect-vs-stone-wool) and [sound insulation vs sound absorption](https://acousticindex.com/en/sound-insulation-vs-absorption).
- [DEGA](https://www.dega-akustik.de) - Deutsche Gesellschaft für Akustik, publications and the DAGA conference.
- Books - Heinrich Kuttruff, *Room Acoustics*; Trevor Cox and Peter D'Antonio, *Acoustic Absorbers and Diffusers*; Lothar Cremer and Helmut Müller, *Principles and Applications of Room Acoustics*; Fasold and Veres, *Schallschutz und Raumakustik in der Praxis*.

## Contributing

Open a pull request with the link, a one-line description and why it meets the criteria above. Please add entries in the section that fits and keep descriptions factual. Commercial product pages are welcome only when they publish measured data with the test method and mounting type.

## License

[CC0 1.0 Universal](LICENSE). To the extent possible under law, the contributors have waived all copyright and related rights to this list.
