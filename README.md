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

Libraries, engines and datasets that are worth knowing when you work with room acoustics in code. None of them ships measured product data; pair them with a database from the first section.

### Simulation and room impulse responses

- [pyroomacoustics](https://github.com/LCAV/pyroomacoustics) - Python package for room impulse response simulation (image source method and ray tracing), beamforming and source separation, from EPFL's LCAV. The standard tool for quick shoebox and polyhedral room experiments.
- [misuka](https://github.com/misuka-renderer/misuka) - Differentiable room acoustic renderer from TU Berlin, built on Mitsuba 3; optimises material parameters against a target and has a Blender add-on.
- [Seiche](https://github.com/SeicheAcoustics/Seiche) - Open-source desktop application that simulates and analyses the acoustics of a 3D mesh through a graphical interface, aimed at designers rather than programmers.
- [PFFDTD](https://github.com/bsxfun/pffdtd) - Multi-GPU finite difference time domain simulator for 3D room acoustics with frequency-dependent impedance boundaries and a voxelisation pipeline.
- [edg-acoustics](https://github.com/Building-acoustics-TU-Eindhoven/edg-acoustics) - Wave-based room acoustics solver from TU Eindhoven using the nodal discontinuous Galerkin method on tetrahedral meshes, for the frequency range where ray tracing breaks down.
- [EVERTims](https://github.com/EVERTims/evertims) - Real-time beam tracing engine with a Blender add-on and a JUCE auralisation client, so a room model can be listened to while it is being drawn.
- [Auralization Toolbox](https://github.com/AppliedAcousticsChalmers/auralization-toolbox) - MATLAB toolbox from Chalmers that turns sound fields sampled from FDTD, FEM or BEM simulations into binaural or ambisonic audio.
- [rir-generator](https://github.com/audiolabs/rir-generator) - Maintained Python and C port of the Habets image source room impulse response generator, on PyPI with documentation and tests.
- [RIR-Generator](https://github.com/ehabets/RIR-Generator) - The original MATLAB image method implementation by Emanuel Habets, still the reference many papers cite.
- [gpuRIR](https://github.com/DavidDiazGuerra/gpuRIR) - Room impulse response simulation with GPU acceleration, useful when you need thousands of RIRs for machine learning.
- [openPSTD](https://github.com/openPSTD/openPSTD) - Open-source pseudo-spectral time-domain solver with a visual interface for wave-based room acoustics.
- [Steam Audio](https://github.com/ValveSoftware/steam-audio) - Valve's spatial audio SDK for games with physics-based occlusion, reflections and reverb; open source.
- [Resonance Audio](https://github.com/resonance-audio/resonance-audio) - Google's spatial audio SDK with ambisonic rendering and room effects; open source.

### Measurement and analysis

- [pyfar](https://github.com/pyfar/pyfar) - Python package for acoustics research: signals, filters, room and free-field data handling, plotting. Grown out of the TU Berlin and RWTH acoustics groups.
- [pyrato](https://github.com/pyfar/pyrato) - Room acoustics tools from the pyfar project for energy decay curves and ISO 3382 parameters from measured impulse responses.
- [PyTTa](https://github.com/PyTTAmaster/PyTTa) - Measurement and analysis toolbox for technical acoustics with sweep-based frequency response measurement, octave filtering and room acoustic parameters, from the Federal University of Santa Maria.
- [Broom](https://github.com/DanielRudrich/Broom) - Browser tool that generates a sine sweep, deconvolves the recording and lets you trim and fade the resulting room impulse response without installing anything.
- [Open Sound Meter](https://github.com/psmokotnin/osm) - Real-time FFT measurement application showing transfer function, phase, coherence and impulse response for tuning rooms and sound systems.

### Standards and material models

- [phonometry](https://github.com/jmrplens/phonometry) - Python library that implements acoustic standards from their text: IEC 61260 filters, IEC 61672 levels, ISO 3382 room parameters, ISO 717 ratings, EN 12354 building acoustics prediction and ISO 9613 outdoor propagation, each checked against normative values in CI.
- [acoustic-toolbox](https://github.com/Universite-Gustave-Eiffel/acoustic-toolbox) - Maintained continuation of python-acoustics with modules for octave bands, weightings and propagation, kept current by Université Gustave Eiffel.
- [python-acoustics](https://github.com/python-acoustics/python-acoustics) - The original library for acousticians: octave bands, weighting, room acoustics parameters per ISO 3382, atmospheric absorption. No longer maintained, see acoustic-toolbox.
- [tmm](https://github.com/rinaldipp/tmm) - Transfer matrix toolbox for multilayer absorbers: porous layers, air cavities, membranes, perforated and slotted panels, with normal, angular and diffuse incidence absorption. Predicts curves from a build-up; it does not replace a measurement.
- [Porous Absorber Calculator](https://github.com/ChrisWhealy/porous_absorber) - Browser calculator in Rust and WebAssembly for rigid-backed porous absorbers, slotted, perforated and microperforated panels, with the physics documented per device type.
- [stipa](https://github.com/zawi01/stipa) - MATLAB implementation of the speech transmission index for public address per IEC 60268-16, generating the test signal and computing STI by the direct method.
- [acoustic_reliefs](https://github.com/mickey1356/acoustic_reliefs) - Optimisation of diffuser surface reliefs from ETH Zurich, published at SIGGRAPH Asia.

### Datasets

- [room-impulse-responses](https://github.com/Graphi07/room-impulse-responses) - Curated index of publicly available measured room impulse response datasets (BUT ReverbDB, Aachen AIR, MIT IR Survey, OpenAIR, Arni and more) with licences and download scripts.
- [dEchorate](https://github.com/Chutlhu/dEchorate) - Measured RIR dataset with annotated early reflections in a room whose surfaces can be switched between absorbing and reflecting.
- [MeshRIR](https://github.com/sh01k/MeshRIR) - Room impulse responses measured on dense microphone grids, for sound field analysis and interpolation, CC-BY 4.0.

## Learning

- [BauNetz Wissen Akustik](https://www.baunetzwissen.de/akustik) - German reference on building and room acoustics for architects.
- [Acoustic Index guides](https://acousticindex.com/en/guides) - Short explainers with sources, for example [Basotect vs stone wool](https://acousticindex.com/en/basotect-vs-stone-wool) and [sound insulation vs sound absorption](https://acousticindex.com/en/sound-insulation-vs-absorption).
- [DEGA](https://www.dega-akustik.de) - Deutsche Gesellschaft für Akustik, publications and the DAGA conference.
- [Digital learning platform for acoustics](https://github.com/Building-acoustics-TU-Eindhoven/digital-learning-platform-for-acoustics) - Open Jupyter Book course material on room and building acoustics from TU Eindhoven, CC-BY 4.0.
- Books - Heinrich Kuttruff, *Room Acoustics*; Trevor Cox and Peter D'Antonio, *Acoustic Absorbers and Diffusers*; Lothar Cremer and Helmut Müller, *Principles and Applications of Room Acoustics*; Fasold and Veres, *Schallschutz und Raumakustik in der Praxis*.

## Contributing

Open a pull request with the link, a one-line description and why it meets the criteria above. Please add entries in the section that fits and keep descriptions factual. Commercial product pages are welcome only when they publish measured data with the test method and mounting type.

## License

[CC0 1.0 Universal](LICENSE). To the extent possible under law, the contributors have waived all copyright and related rights to this list.
