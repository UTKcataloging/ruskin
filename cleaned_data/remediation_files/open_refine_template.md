# OpenRefine Template for Photographs of the Ruskin Cooperative Association (migration)

---

## Prefix

```
<?xml version="1.0" encoding="UTF-8"?>
<modsCollection xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
```

## Row Template

```
<mods>
<identifier type="local">{{cells["adminDB"].value}}</identifier>
<identifier type="pid">{{cells["PID"].value}}</identifier>
<identifier type="spc">{{cells["spc_identifier"].value}}</identifier>
<titleInfo><title>{{cells["title"].value}}</title></titleInfo>
{{if(isBlank(cells["abstract"].value),'', '<abstract>' + cells['abstract'].value + '</abstract>')}}
{{'<originInfo>' + if(isBlank(cells['dateCreated'].value), '', '<dateCreated>' + cells['dateCreated'].value + '</dateCreated>') + if(isBlank(cells['date_edtf'].value), '', '<dateCreated encoding="edtf" keyDate="yes">' + cells['date_edtf'].value + '</dateCreated>') + if(isBlank(cells['date_start'].value), '', '<dateCreated encoding="edtf" qualifier="' + cells['date_qualifier'].value + '" keyDate="yes" point="start">' + cells['date_start'].value + '</dateCreated>') + if(isBlank(cells['date_end'].value), '', '<dateCreated encoding="edtf" qualifier="' + cells['date_qualifier'].value + '" point="end">' + cells['date_end'].value + '</dateCreated>') + '</originInfo>'}}
{{if(isBlank(cells['note_date'].value), '', '<note>' + cells['note_date'].value + '</note>')}}
<name><namePart>Unknown</namePart><role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/pht">Photographer</roleTerm></role></name>
<subject authority="lcsh" valueURI="http://id.loc.gov/authorities/subjects/sh85028258"><topic>Collective settlements</topic></subject>
<subject authority="naf" valueURI="http://id.loc.gov/authorities/names/nr93003802"><name><namePart>Ruskin Co-operative Association</namePart></name></subject>
{{if(isBlank(cells['subject3'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject3_URI'].value + '"><topic>' + cells['subject3'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject4'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject4_URI'].value + '"><topic>' + cells['subject4'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_geo'].value), '', '<subject authority="geonames" valueURI="' + cells['subject_geo_URI'].value + '"><geographic>' + cells['subject_geo'].value + '</geographic><cartographics><coordinates>' + cells['coordinates'].value + '</coordinates></cartographics></subject>')}}
{{if(isBlank(cells['subject_geo2'].value), '', '<subject authority="naf" valueURI="' + cells['subject_geo2_URI'].value + '"><geographic>' + cells['subject_geo2'].value + '</geographic><cartographics><coordinates>' + cells['coordinates2'].value + '</coordinates></cartographics></subject>')}}
<physicalDescription><form authority="aat" valueURI="{{cells['form_URI'].value}}">{{cells['form'].value}}</form><internetMediaType>{{cells['internetMediaType'].value}}</internetMediaType></physicalDescription>
<typeOfResource>{{cells['typeOfResource'].value}}</typeOfResource>
<language><languageTerm type="text" authority="iso639-2b">English</languageTerm></language>
<relatedItem displayLabel="Project" type="host"><titleInfo><title>{{cells['digital_collection'].value}}</title></titleInfo></relatedItem>
<relatedItem displayLabel="Collection" type="host"><titleInfo><title>{{cells['archival_collection'].value}}</title></titleInfo><identifier>{{cells['collection_identifier'].value}}</identifier><location><url>{{cells['ARK'].value}}</url></location></relatedItem>
<location><physicalLocation valueURI="{{cells['repository_URI'].value}}">{{cells['repository'].value}}</physicalLocation></location>
<recordInfo><recordContentSource valueURI="{{cells['recordsource_URI'].value}}">{{cells['record_source'].value}}</recordContentSource></recordInfo>
<accessCondition type="use and reproduction" xlink:href="{{cells['rights_URI'].value}}">{{cells['rights'].value}}</accessCondition>
</mods>
```

## Row Separator

**LEAVE BLANK**

## Suffix

```
</modsCollection>
```