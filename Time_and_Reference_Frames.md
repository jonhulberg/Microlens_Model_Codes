## Reference frames and time standards

This page lists the reference frames and time standards used by each microlensing modeling code, with focus on parallax calculations.
The table below contains the input time system, how time is handled for parallax calculations, and the parallax reference frame (i.e., the observer position center).

| Code           | Input time system      | Time handling for parallax | Parallax frame    | Refs. |
|----------------|------------------------|----------------------------|-------------------|-------|
| BAGLE          | MJD                    | BJD_TDB                    | Heliocentric?     | [1](https://rpoleski.github.io/MulensModel/MulensModel.mulensdata.html)      |
| VBM / RTModel  | HJD' (JD' can be used) | Internally JD <-> HJD      | SSB (Barycentric) |       |
| MulensModel    | Any (if no parallax)   | BJD_TDB                    | SSB (Barycentric) -- Geocentric |       |
| pyLIMA         | JD                     | Depends on dataset?        | SSB (Barycentric) | [1](https://pylima.readthedocs.io/en/latest/source/Conventions.html) |
| eesunhong      | ... | | Heliocentric
| muLAN          | HJD                    | MJD_TDB                    | 
| microlux       | ...
| microjax       | ... | | Heliocentric

Regarding the microlensing surveys, the time system from OGLE are in Julian Date (JD), while MOA and KMTNet use Heliocentric Julian Date (HJD).
*I will still double check that and extend it for the other surveys and space telescopes.*

Obs: Time difference between heliocentric and SSB is ~1 sec.

Obs2: BJD_TDB stands for Barycentric Julian Date, Barycentric Dynamic Time. It is the time coordinate in the SSB frame, used for calculating planetary ephemerides and is a relativistic, coordinate time. TDB differs from TT by periodic terms (up to ~1.6 milliseconds) due to relativistic effects.

### To-Do List:

- Double checking with code developers
- Add links in the Refs. column
- Add a column for parallax parametrization?
- Make a separate table for survey conventions for `t_0`
- Write notes about the conventions and how to convert from one another
- Check DE430 (default) and more recent kernels, how much they affect the Earth position

<!-- Internal notes (to be deleted...) -->
<!-- Raphael: It seems that in retrieving the ephemeris, everyone is converging to barycentric... -->
<!-- Radek's notes about JPL Horizons output format: -->
<!-- https://github.com/rpoleski/MulensModel/blob/73008fb1ed7f3504fa4ae55e0ecf1257eeb0a83a/documents/Horizons_notes.md -->
<!-- Jessica notes about survey conventions -->
<!-- ``OGLE uses heliocentric (not SSB), MOA uses geocentric JD, KMTNet uses heliocentric.'' -->
<!-- MulensModel notes about astropy's get_body_barycentric() function -->
<!-- Seems that get_body_barycentric depends on time system, but there is no way to set BJD part of BJD_TDB in astropy.Time(). The option *format* above indicates if the first argument of Time() is a float indicating JD or e.g., a string in the form '1999-01-01T00:00:00.123' - this would be value 'fits'. Hence, the user has to provide BJD times (or at least HJD). -->

