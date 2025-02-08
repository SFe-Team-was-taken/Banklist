# Banklist

Banklist is the official standardisation of SFLIST, a term used to describe file formats that describe how multiple legacy SF2.0x banks can be used together. Banklist is designed to work with both legacy SF2.0x and SFe, with the specification being planned for integration into SFe with version 4.2.

The Banklist reference implementation is in development and is based on the BSD-licensed SFLIST reference implementation by Christopher Snowhill available [here](https://gist.github.com/kode54/a7bb01a0db3f2e996145b77f0ca510d5).

### Original readme for SFLIST JSON reference implementation

If fileName specifies another sflist json file, no other arguments will be processed for that block,
and the contents of that file will be parsed and included.

SoundFont load priority is the same as the original SFList, in that files listed first will be overridden by files listed later. Nested .sflist.json loading has the same rules. Basically, first come, first loaded. Except that BASS treats first items in the list as higher priority, so I guess reverse the order when preparing the list for BASS?

Adding an integer priority value may be useful to some people, but I'm not sure if ipt's such a good idea.

patchMappings:
As many items as is necessary. SFZ ignores and therefore does not require the "source" argument.
Depending on how the loading operation is intended, "bank" or "program" may be optional. For source,
"bank" is assumed to be 'all banks' if not specified, and "program" is assumed to be 'all presets'
if not specified. For destination, "program" is assumed to be 'all presets' only if not present and
if source is not specified, while "bank" must be present, and is assumed to be the base bank if
loading all presets and banks from the source.

gain:
floating point, decibels, optional argument.

channels:
array of one or more numbers in range of 1-48, also optional.