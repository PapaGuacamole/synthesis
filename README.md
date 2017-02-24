# synthesis v1.3
WIP set of tools for the Synthesis skill in [Achaea](https://www.achaea.com). Download the xml [here](https://raw.githubusercontent.com/PapaGuacamole/synthesis/master/synthesis.xml).

### Functionality
- automatically survey the current area for rooms of the correct environment that have not already have all three primes extracted in the current day
- automatically walk to the nearest room to your current location that meets the criteria above and begin extraction
- adds shops in otherwise extractable locations and stores them in external table to persist between sessions, then automatically excludes them from future surveys
- makes use of [Svof](https://github.com/svof/svof/releases)'s doadd if available, otherwise uses inbuilt queueing system.

### Aliases
| Alias  | Description |
| :-----------: | ------------- |
| extract | toggle auto-extracting (also accepts 'on' and 'off' as arguments) |
| esurvey | check current area for rooms which are the correct environment and have not been fully extracted in the current day |
| enext | walk to nearest room listed in esurvey |
| eload | manually load the stored list of shop room IDs |
| esave | manually save the stored list of shop room IDs |

### Future developments
- rift tracking
- batch synthesis of metals
- batch transmutation of minerals
- integration with other Achaea curing/queueing systems

### Requirements
[Mudlet](http://www.mudlet.org) v2.1 or greater (v3.0+ recommended)
[Mudlet-Mapper](https://github.com/IRE-Mudlet-Mapping/ire-mapping-script)

### Changelog
**v1.3**
- fixed issue with syn.ref.shops being recursive
- fixed issue with re-entering a previously logged shop resetting syn.ref.shops
- began work on bulk processing scripts

**v1.2**
- added changelog
- added in shop detection and marking to syn.f.enteredroom
- syn.area added as fourth argument to syn.extracted[room] for statistic gathering
- created *syn.ref.shops* to be populated with known shops
- added *syn.f.load()* and *syn.f.save()* to allow *syn.ref.shops* to persist through sessions
- *syn.f.load()* automatically called if *syn.ref.shops* is empty
- *syn.f.save()* automatically called when a new entry is made to the table
- added *esave* and *eload* aliases

**v1.1**
- rearranged scripts
- removed *syn.rw* namespace
- added check for gmcp and gmcp.Room before trying to populate *syn.area*

**v1.0**
- initial release