---
Title: Mapping ISO-19139_che to DCAT-AP Switzerland
Category: Library
Template: document
Tags: publish
Date: 2018-01-30
Slug: iso-19139-che-dcat
Summary:
Lang: en
toc_run: true
---
This documentation describes the mapping from ISO-19139_che to [DCAT-AP Switzerland](/en/library/ch-dcat-ap.html).
ISO-19139_che is a standard used by [Geocat](https://www.geocat.ch), a data source from which opendata.swiss harvests datasets.

In this documentation we focus on the XML serialization of ISO-19139_che and therefore describe the mapping in form of XPath (if not noted differently).

[Example XML serialization of an ISO-19139_che dataset](https://www.geocat.ch/geonetwork/srv/ger/xml.metadata.get?uuid=c5bc9d6b-cafb-4617-97d7-868ab4cd5506)

<a name="definition-of-identifier"></a>
#### Definition of `dct:identifier`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Identifier|
|ISO-19139_che XPath|//gmd:fileIdentifier/gco:CharacterString + '@' organization-slug (configuration of the harvester)|
|Description| |


Example of ISO-19139_che:
```xml
<gmd:fileIdentifier>
  <gco:CharacterString>93814e81-2466-4690-b54d-c1d958f1c3b8</gco:CharacterString>
</gmd:fileIdentifier>
```

<a name="definition-of-title"></a>
#### Definition of `dct:title`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Pagetitle |
|ISO-19139_che XPath|	//gmd:identificationInfo//gmd:citation//gmd:title//gmd:textGroup/gmd:LocalisedCharacterString|
|Description| |


Example:
```xml
<gmd:title xsi:type="gmd:PT_FreeText_PropertyType">
  <gco:CharacterString>Lärmbelastung durch Eisenbahnverkehr (Lr_Nacht)</gco:CharacterString>
  <gmd:PT_FreeText>
    <gmd:textGroup>
      <gmd:LocalisedCharacterString locale="#FR">
        Exposition au bruit du trafic ferroviaire (Lr_nuit)
      </gmd:LocalisedCharacterString>
    </gmd:textGroup>
    <gmd:textGroup>
      <gmd:LocalisedCharacterString locale="#DE">Lärmbelastung durch Eisenbahnverkehr (Lr_Nacht)</gmd:LocalisedCharacterString>
    </gmd:textGroup>
    <gmd:textGroup>
      <gmd:LocalisedCharacterString locale="#EN">Nighttime railway noise exposure</gmd:LocalisedCharacterString>
    </gmd:textGroup>
    <gmd:textGroup>
      <gmd:LocalisedCharacterString locale="#IT">
        Esposizione al rumore del traffico ferroviario (Lr_notte)
      </gmd:LocalisedCharacterString>
    </gmd:textGroup>
    <gmd:textGroup>
      <gmd:LocalisedCharacterString locale="#RM">
        Grevezza da canera tras il traffic da viafier durant la notg
      </gmd:LocalisedCharacterString>
    </gmd:textGroup>
  </gmd:PT_FreeText>
</gmd:title>
```

<a name="definition-of-description"></a>
#### Definition of `dct:description`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Description |
|ISO-19139_che XPath|//gmd:identificationInfo//gmd:abstract//gmd:textGroup/gmd:LocalisedCharacterString|
|Description| |


Example:
```xml
<gmd:description xsi:type="gmd:PT_FreeText_PropertyType">
  <gco:CharacterString>Schweiz</gco:CharacterString>
  <gmd:PT_FreeText>
    <gmd:textGroup>
      <gmd:LocalisedCharacterString locale="#EN">Schweiz</gmd:LocalisedCharacterString>
    </gmd:textGroup>
    <gmd:textGroup>
      <gmd:LocalisedCharacterString locale="#DE">Schweiz</gmd:LocalisedCharacterString>
    </gmd:textGroup>
    <gmd:textGroup>
      <gmd:LocalisedCharacterString locale="#FR">Schweiz</gmd:LocalisedCharacterString>
    </gmd:textGroup>
    <gmd:textGroup>
      <gmd:LocalisedCharacterString locale="#IT">Schweiz</gmd:LocalisedCharacterString>
    </gmd:textGroup>
    <gmd:textGroup>
      <gmd:LocalisedCharacterString locale="#RM">Schweiz</gmd:LocalisedCharacterString>
    </gmd:textGroup>
  </gmd:PT_FreeText>
</gmd:description>
```

<a name="definition-of-issued"></a>
#### Definition of `dct:issued`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Issued date |
|ISO-19139_che XPath| <ul><li>///gmd:identificationInfo//gmd:citation//gmd:CI_Date[.//gmd:CI_DateTypeCode/@codeListValue = "publication"]//gco:Date or gco:DateTime</li><li>//gmd:identificationInfo//gmd:citation//gmd:CI_Date[.//gmd:CI_DateTypeCode/@codeListValue = "creation"]//gco:Date or gco:DateTime</li><li>//gmd:identificationInfo//gmd:citation//gmd:CI_Date[.//gmd:CI_DateTypeCode/@codeListValue = "revision"]//gco:Date or gco:DateTime</li></ul> The first found date is taken in the order defined above.|
|Description| |


Example:
```xml
<gmd:CI_DateTypeCode codeListValue="revision" codeList="http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19139_Schemas/resources/codelist/ML_gmxCodelists.xml#CI_DateTypeCode"/>
```

<a name="definition-of-modified"></a>
#### Definition of `dct:modified`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Modified date|
|ISO-19139_che XPath|//gmd:identificationInfo//gmd:citation//gmd:CI_Date[.//gmd:CI_DateTypeCode/@codeListValue = "revision"]//gco:Date or gco:DateTime|
|Description| |


Example:
```xml
<gco:Date>2011-12-31</gco:Date>
<gco:DateTime>2009-01-01T00:00:00</gco:DateTime>
```

<a name="definition-of-publisher"></a>
#### Definition of `dct:publisher`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Publishers|
|ISO-19139_che XPath|The first one in the following order:<ul><li>//gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "publisher"]//gmd:organisationName/gco:CharacterString</li><li>//gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "owner"]//gmd:organisationName/gco:CharacterString</li><li>//gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "pointOfContact"]//gmd:organisationName/gco:CharacterString</li><li>//gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "distributor"]//gmd:organisationName/gco:CharacterString</li><li>//gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "custodian"]//gmd:organisationName/gco:CharacterString</li><li>//gmd:contact//che:CHE_CI_ResponsibleParty//gmd:organisationName/gco:CharacterString</li></ul>|
|Description| |


Example:
```xml<gmd:pointOfContact xlink:show="embed">
<che:CHE_CI_ResponsibleParty xmlns:geonet="http://www.fao.org/geonetwork" gco:isoType="gmd:CI_ResponsibleParty">
<gmd:organisationName xsi:type="gmd:PT_FreeText_PropertyType">...</gmd:organisationName>
<gmd:positionName xsi:type="gmd:PT_FreeText_PropertyType">...</gmd:positionName>
<gmd:contactInfo>
<gmd:CI_Contact>
<gmd:phone>...</gmd:phone>
<gmd:address>...</gmd:address>
<gmd:onlineResource>...</gmd:onlineResource>
</gmd:CI_Contact>
</gmd:contactInfo>
<gmd:role>
<gmd:CI_RoleCode codeList="http://www.isotc211.org/2005/resources/codeList.xml#CI_RoleCode" codeListValue="pointOfContact"/>
</gmd:role>
<che:individualLastName>...</che:individualLastName>
<che:organisationAcronym xsi:type="gmd:PT_FreeText_PropertyType">...</che:organisationAcronym>
</che:CHE_CI_ResponsibleParty>
</gmd:pointOfContact>
```

<a name="definition-of-contactPoint"></a>
#### Definition of `dcat:contactPoint`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Contact points |
|ISO-19139_che XPath|The first one in the following order:<ul><li>//gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "pointOfContact"]//gmd:address//gmd:electronicMailAddress/gco:CharacterString</li><li>//gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "owner"]//gmd:address//gmd:electronicMailAddress/gco:CharacterString</li><li>//gmd:identificationInfo//gmd:pointOfContact
[.//gmd:CI_RoleCode/@codeListValue = "publisher"]//gmd:address//gmd:electronicMailAddress/gco:CharacterString</li><li>//gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "distributor"]//gmd:address//gmd:electronicMailAddress/gco:CharacterString</li><li>//gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "custodian"]//gmd:address//gmd:electronicMailAddress/gco:CharacterString</li><li>//gmd:contact//che:CHE_CI_ResponsibleParty//gmd:address//gmd:electronicMailAddress/gco:CharacterString</li></ul>|
|Description| |


Example:
```xml
<gmd:pointOfContact xlink:show="embed">
  <che:CHE_CI_ResponsibleParty xmlns:geonet="http://www.fao.org/geonetwork" gco:isoType="gmd:CI_ResponsibleParty">
    <gmd:organisationName xsi:type="gmd:PT_FreeText_PropertyType">
      <gco:CharacterString>Bundesamt für Umwelt</gco:CharacterString>
      <gmd:PT_FreeText>...</gmd:PT_FreeText>
    </gmd:organisationName>
    <gmd:positionName xsi:type="gmd:PT_FreeText_PropertyType">
      <gco:CharacterString>Abteilung Lärm und NIS</gco:CharacterString>
      <gmd:PT_FreeText>...</gmd:PT_FreeText>
    </gmd:positionName>
    <gmd:contactInfo>
      <gmd:CI_Contact>...</gmd:CI_Contact>
    </gmd:contactInfo>
    <gmd:role>
      <gmd:CI_RoleCode codeList="http://www.isotc211.org/2005/resources/codeList.xml#CI_RoleCode" codeListValue="pointOfContact"/>
    </gmd:role>
    <che:individualLastName>
      <gco:CharacterString>BAFU noise</gco:CharacterString>
    </che:individualLastName>
    <che:organisationAcronym xsi:type="gmd:PT_FreeText_PropertyType">
      <gco:CharacterString>BAFU</gco:CharacterString>      <gmd:PT_FreeText>...</gmd:PT_FreeText>
    </che:organisationAcronym>
  </che:CHE_CI_ResponsibleParty>
</gmd:pointOfContact>
```

<a name="definition-of-theme"></a>
#### Definition of `dcat:theme`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Categories|
|ISO-19139_che XPath|//gmd:identificationInfo//gmd:topicCategory/gmd:MD_TopicCategoryCode<ul><li>biota => http://opendata.swiss/themes/agriculture</li><li>society => http://opendata.swiss/themes/culture</li><li>health => http://opendata.swiss/themes/health</li><li>transportation => http://opendata.swiss/themes/mobility</li><li>intelligenceMilitary => http://opendata.swiss/themes/public-order</li><li>farming => http://opendata.swiss/themes/agriculture</li><li>economy => http://opendata.swiss/themes/national-economy</li><li>utilitiesCommunication_Energy => http://opendata.swiss/themes/energy</li></ul>Everything else is mapped to  http://opendata.swiss/themes/territory .<br> Additionally get all records in category http://opendata.swiss/themes/geography <br> see [documnetation of all categories](http://www.ech.ch/vechweb/page?p=dossier&documentNumber=eCH-0166)|
|Description| |


Example:
```xml
<gmd:topicCategory>
  <gmd:MD_TopicCategoryCode>environment</gmd:MD_TopicCategoryCode>
</gmd:topicCategory>
```

<a name="definition-of-language"></a>
#### Definition of `dct:language`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Languages|
|ISO-19139_che XPath|//gmd:identificationInfo//gmd:language/gmd:LanguageCode|
|Description| |

TODO: Is this mapping still correct? could not find any CharacterString in gmd:language

Example:
```xml
<gmd:language>
<gmd:LanguageCode codeList="http://www.loc.gov/standards/iso639-2/" codeListValue="ger"/>
</gmd:language>
```

<a name="definition-of-distribution"></a>
#### Definition of `dcat:distribution`
See [distributions documentation below](#distributions)

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Resources |
|ISO-19139_che XPath| <ul><li>//gmd:distributionInfo/gmd:MD_Distribution[//gmd:transferOptions//gmd:CI_OnlineResource//gmd:protocol/gco:CharacterString/text() = <ul><li>"WWW:DOWNLOAD-1.0-http–download" </li><li>"OGC:WMTS-http-get-capabilities" </li><li>"OGC:WMS-http-get-map" </li><li>"OGDC:WMS-http-get-capabilities" </li><li>"OGC:WFS-http-get-capabilities" </li><li>"WWW:DOWNLOAD-URL"]</li></ul><li>//gmd:identificationInfo//srv:containsOperations/srv:SV_OperationMetadata[.//srv:operationName//gco:CharacterString/text()]</li></ul> see below under "Distributions" |
|Description| |


Example:
```xml
<gmd:distributionInfo>
  <gmd:MD_Distribution>
    <gmd:distributionFormat xlink:show="embed">...</gmd:distributionFormat>
    <gmd:transferOptions>
      <gmd:MD_DigitalTransferOptions>
        <gmd:onLine>
          <gmd:CI_OnlineResource>
            <gmd:linkage xsi:type="che:PT_FreeURL_PropertyType">...</gmd:linkage>
            <gmd:protocol>
              <gco:CharacterString>WWW:LINK-1.0-http--link</gco:CharacterString>
            </gmd:protocol>
            <gmd:description xsi:type="gmd:PT_FreeText_PropertyType">...</gmd:description>
            <gmd:function>...</gmd:function>
          </gmd:CI_OnlineResource>
        </gmd:onLine>
      </gmd:MD_DigitalTransferOptions>
    </gmd:transferOptions>
  </gmd:MD_Distribution>
</gmd:distributionInfo>
```

<a name="definition-of-relation"></a>
#### Definition of `dct:relation`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Further information |
|ISO-19139_che XPath|(//gmd:distributionInfo/gmd:MD_Distribution//gmd:transferOptions//gmd:CI_OnlineResource[.//gmd:protocol/gco:CharacterString/text() = "WWW:LINK-1.0-http--link"]//che:LocalisedURL)[position()>1] Every first link of the online resources gets put as landingPage, every additional link gets put into the relations.|
|Description| |


Example:
```xml
<gmd:distributionInfo>
  <gmd:MD_Distribution>
    <gmd:distributionFormat xlink:show="embed">...</gmd:distributionFormat>
    <gmd:transferOptions>
      <gmd:MD_DigitalTransferOptions>
        <gmd:onLine>
          <gmd:CI_OnlineResource>
            <gmd:linkage xsi:type="che:PT_FreeURL_PropertyType">...</gmd:linkage>
            <gmd:protocol>
              <gco:CharacterString>WWW:LINK-1.0-http--link</gco:CharacterString>
            </gmd:protocol>
            <gmd:description xsi:type="gmd:PT_FreeText_PropertyType">...</gmd:description>
            <gmd:function>...</gmd:function>
          </gmd:CI_OnlineResource>
        </gmd:onLine>
      </gmd:MD_DigitalTransferOptions>
    </gmd:transferOptions>
  </gmd:MD_Distribution>
</gmd:distributionInfo>
```

<a name="definition-of-keyword"></a>
#### Definition of `dcat:keyword`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Keywords of the dataset |
|ISO-19139_che XPath|//gmd:identificationInfo//gmd:descriptiveKeywords//gmd:keyword//gmd:textGroup//gmd:LocalisedCharacterString|
|Description| |


Example:
```xml
<gmd:identificationInfo>
  <che:CHE_MD_DataIdentification gco:isoType="gmd:MD_DataIdentification">
      <gmd:citation>...</gmd:citation>
      <gmd:abstract xsi:type="gmd:PT_FreeText_PropertyType">...</gmd:abstract>
      <gmd:purpose xsi:type="gmd:PT_FreeText_PropertyType">...</gmd:purpose>
      <gmd:status>...</gmd:status>
      <gmd:pointOfContact xlink:show="embed">...</gmd:pointOfContact>
      <gmd:resourceMaintenance>...</gmd:resourceMaintenance>
      <gmd:descriptiveKeywords>
        <gmd:MD_Keywords>
          <gmd:keyword xsi:type="gmd:PT_FreeText_PropertyType">
            <gmd:PT_FreeText>
              <gmd:textGroup>
                <gmd:LocalisedCharacterString locale="#DE">e-geo.ch Geoportal</gmd:LocalisedCharacterString>
              </gmd:textGroup>
            </gmd:PT_FreeText>
          </gmd:keyword>
          <gmd:type>...</gmd:type>
          <gmd:thesaurusName>...</gmd:thesaurusName>
        </gmd:MD_Keywords>
      </gmd:descriptiveKeywords>
    <gmd:spatialRepresentationType>...</gmd:spatialRepresentationType>
    <gmd:language>...</gmd:language>
    <gmd:characterSet>...</gmd:characterSet>
    <gmd:topicCategory>...</gmd:topicCategory>
    <gmd:extent xlink:show="embed">...</gmd:extent>
    <che:basicGeodataID>...</che:basicGeodataID>
    <che:basicGeodataIDType>...</che:basicGeodataIDType>
  </che:CHE_MD_DataIdentification>
</gmd:identificationInfo>
```

<a name="definition-of-landingPage"></a>
#### Definition of `dcat:landingPage`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Landing page|
|ISO-19139_che XPath|//gmd:distributionInfo/gmd:MD_Distribution//gmd:transferOptions//gmd:CI_OnlineResource[.//gmd:protocol/gco:CharacterString/text() = "WWW:LINK-1.0-http--link"]//che:LocalisedURL|
|Description| |


Example:
```xml
<gmd:distributionInfo>
  <gmd:MD_Distribution>
    <gmd:distributionFormat xlink:show="embed">...</gmd:distributionFormat>
    <gmd:transferOptions>
      <gmd:MD_DigitalTransferOptions>
        <gmd:onLine>
          <gmd:CI_OnlineResource>
            <gmd:linkage xsi:type="che:PT_FreeURL_PropertyType">...</gmd:linkage>
            <gmd:protocol>
              <gco:CharacterString>WWW:LINK-1.0-http--link</gco:CharacterString>
            </gmd:protocol>
            <gmd:description xsi:type="gmd:PT_FreeText_PropertyType">...</gmd:description>
            <gmd:function>...</gmd:function>
          </gmd:CI_OnlineResource>
        </gmd:onLine>
      </gmd:MD_DigitalTransferOptions>
    </gmd:transferOptions>
  </gmd:MD_Distribution>
</gmd:distributionInfo>
```

<a name="definition-of-spatial"></a>
#### Definition of `dct:spatial`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss|Currently not implemented |
|ISO-19139_che XPath| -|
|Description| |


<a name="definition-of-coverage"></a>
#### Definition of `dct:coverage`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss|Currently not implemented|
|ISO-19139_che XPath| -|
|Description| |


<a name="definition-of-temporal"></a>
#### Definition of `dct:temporal`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Temporal coverage |
|ISO-19139_che XPath|<ul><li>//gmd:identificationInfo//gmd:extent//gmd:temporalElement//gml:TimePeriod/gml:beginPosition</li><li>//gmd:identificationInfo//gmd:extent//gmd:temporalElement//gml:TimePeriod/gml:endPosition</li>|
|Description| |

TODO: Example missing

Example:
```xml
missing
```

<a name="definition-of-accrualPeriodicity"></a>
#### Definition of `dct:accrualPeriodicity`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Update interval |
|ISO-19139_che XPath|//gmd:identificationInfo//che:CHE_MD_MaintenanceInformation/gmd:maintenanceAndUpdateFrequency/gmd:MD_MaintenanceFrequencyCode/@codeListValue<ul><li>continual => http://purl.org/cld/freq/continuous</li><li>daily => http://purl.org/cld/freq/daily</li><li>weekly => http://purl.org/cld/freq/weekly</li><li>fortnightly => http://purl.org/cld/freq/biweekly</li><li>monthly => http://purl.org/cld/freq/monthly</li><li>quarterly => http://purl.org/cld/freq/quarterly</li><li>biannually =>http://purl.org/cld/freq/semiannual</li><li>annually => http://purl.org/cld/freq/annual</li><li>asNeeded => http://purl.org/cld/freq/completelyIrregular</li><li>irregular => http://purl.org/cld/freq/completelyIrregular</li><li>notPlanned => http://purl.org/cld/freq/completelyIrregular</li><li>unknown => http://purl.org/cld/freq/completelyIrregular</li></ul> |
|Description| |


Example:
```xml
<gmd:identificationInfo>
  <che:CHE_MD_DataIdentification gco:isoType="gmd:MD_DataIdentification">
    <gmd:citation>...</gmd:citation>
    <gmd:abstract xsi:type="gmd:PT_FreeText_PropertyType">...</gmd:abstract>
    <gmd:purpose xsi:type="gmd:PT_FreeText_PropertyType">...</gmd:purpose>
    <gmd:status>...</gmd:status>
    <gmd:pointOfContact xlink:show="embed">...</gmd:pointOfContact>
    <gmd:resourceMaintenance>
      <che:CHE_MD_MaintenanceInformation gco:isoType="gmd:MD_MaintenanceInformation">
        <gmd:maintenanceAndUpdateFrequency>
          <gmd:MD_MaintenanceFrequencyCode codeList="http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19139_Schemas/resources/codelist/ML_gmxCodelists.xml#MD_MaintenanceFrequencyCode" codeListValue="userDefined"/>
        </gmd:maintenanceAndUpdateFrequency>
        <gmd:userDefinedMaintenanceFrequency>...</gmd:userDefinedMaintenanceFrequency>
        <che:appraisal>...</che:appraisal>
      </che:CHE_MD_MaintenanceInformation>
    </gmd:resourceMaintenance>
    <gmd:descriptiveKeywords>...</gmd:descriptiveKeywords>
    <gmd:spatialRepresentationType>...</gmd:spatialRepresentationType>
    <gmd:language>...</gmd:language>
    <gmd:characterSet>...</gmd:characterSet>
    <gmd:topicCategory>...</gmd:topicCategory>
    <gmd:extent xlink:show="embed">...</gmd:extent>
    <che:basicGeodataID>...</che:basicGeodataID>
    <che:basicGeodataIDType>...</che:basicGeodataIDType>
  </che:CHE_MD_DataIdentification>
</gmd:identificationInfo>
```

<a name="definition-of-seeAlso"></a>
#### Definition of `rdfs:seeAlso`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| - |
|ISO-19139_che XPath|Currently not implemented|
|Description| |


<a name="distributions" id="distributions"></a>
# Distributions

<a name="definition-of-dcp-title"></a>
#### Definition of `dct:title`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Pagetitle |
|ISO-19139_che XPath|<ul><li>For geodata: derived from protocol(//gmd:transferOptions//gmd:CI_OnlineResource//gmd:protocol/gco:CharacterString) and name (.//gmd:distributionInfo//gmd:transferOptions/gmd:name)</li><li>In geoservices: .//srv:operationName/gco:CharacterString</li></ul>|
|Description| |


Example:
```xml
<gmd:transferOptions>
  <gmd:MD_DigitalTransferOptions>
    <gmd:onLine>
      <gmd:CI_OnlineResource>
        <gmd:linkage xsi:type="che:PT_FreeURL_PropertyType">...</gmd:linkage>
        <gmd:protocol>
          <gco:CharacterString>WWW:LINK-1.0-http--link</gco:CharacterString>
        </gmd:protocol>
        <gmd:description xsi:type="gmd:PT_FreeText_PropertyType">...</gmd:description>
        <gmd:function>...</gmd:function>
      </gmd:CI_OnlineResource>
      </gmd:onLine>
  </gmd:MD_DigitalTransferOptions>
</gmd:transferOptions>
```

<a name="definition-of-dcp-description"></a>
#### Definition of `dct:description`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Description |
|ISO-19139_che XPath|<ul><li>.//gmd:transferOptions//gmd:CI_OnlineResource//gmd:description//gmd:LocalisedCharacterString</li><li>In geoservices: Description of dataset</li></ul>|
|Description| |


Example:
```xml
<gmd:description xsi:type="gmd:PT_FreeText_PropertyType">
  <gco:CharacterString>Download Server von geo.admin.ch</gco:CharacterString>
  <gmd:PT_FreeText>
    <gmd:textGroup>
      <gmd:LocalisedCharacterString locale="#DE">Download Server von geo.admin.ch</gmd:LocalisedCharacterString>
    </gmd:textGroup>
    <gmd:textGroup>
      <gmd:LocalisedCharacterString locale="#FR">Serveur de téléchargement de geo.admin.ch</gmd:LocalisedCharacterString>
    </gmd:textGroup>
    <gmd:textGroup>
      <gmd:LocalisedCharacterString locale="#EN">Download server from geo.admin.ch</gmd:LocalisedCharacterString>
    </gmd:textGroup>
    <gmd:textGroup>
      <gmd:LocalisedCharacterString locale="#IT">Server di download di geo.admin.ch</gmd:LocalisedCharacterString>
    </gmd:textGroup>
  </gmd:PT_FreeText>
</gmd:description>
```

<a name="definition-of-dcp-language"></a>
#### Definition of `dct:language`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Languages |
|ISO-19139_che XPath|Locales from  .//gmd:transferOptions//gmd:CI_OnlineResource//che:LocalisedURL|
|Description| |


Example:
```xml
<gmd:CI_OnlineResource>
  <gmd:linkage xsi:type="che:PT_FreeURL_PropertyType">
  <gmd:URL>...</gmd:URL>
  <che:PT_FreeURL>
    <che:URLGroup>
      <che:LocalisedURL locale="#EN">
        https://www.bafu.admin.ch/bafu/en/home/office/divisions-sections/noise-and-nir-division.html
      </che:LocalisedURL>
      </che:URLGroup>
  </che:PT_FreeURL>
  </gmd:linkage>
  <gmd:protocol>...</gmd:protocol>
</gmd:CI_OnlineResource>
```

<a name="definition-of-dcp-issued"></a>
#### Definition of `dct:issued`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| - |
|ISO-19139_che XPath|issued from dataset|
|Description| |


<a name="definition-of-dcp-modified"></a>
#### Definition of `dct:modified`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| - |
|ISO-19139_che XPath|modified from dataset|
|Description| |


<a name="definition-of-dcp-accessURL"></a>
#### Definition of `dcat:accessURL`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Access URL |
|ISO-19139_che XPath|<ul><li>.//gmd:transferOptions//gmd:CI_OnlineResource[.//gmd:protocol/gco:CharacterString/text() = "OGC:WMTS-http-get-capabilities"]//che:LocalisedURL</li><li>.//gmd:transferOptions//gmd:CI_OnlineResource[.//gmd:protocol/gco:CharacterString/text() = "OGC:WMS-http-get-map"]//che:LocalisedURL</li><li>.//gmd:transferOptions//gmd:CI_OnlineResource[.//gmd:protocol/gco:CharacterString/text() = "OGC:WMS-http-get-capabilities"]//che:LocalisedURL</li><li>.//gmd:transferOptions//gmd:CI_OnlineResource[.//gmd:protocol/gco:CharacterString/text() = "OGC:WFS-http-get-capabilities"]//che:LocalisedURL</li><li>.//gmd:transferOptions//gmd:CI_OnlineResource[.//gmd:protocol/gco:CharacterString/text() = "CHTOPO:specialised-geoportal"]//che:LocalisedURL</li><li>.//gmd:transferOptions//gmd:CI_OnlineResource[.//gmd:protocol/gco:CharacterString/text() = "WWW:LINK-1.0-http–link"]//che:LocalisedURL</li><li>.//gmd:transferOptions//gmd:CI_OnlineResource[.//gmd:protocol/gco:CharacterString/text() = "WWW:DOWNLOAD-1.0-http--download"]//che:LocalisedURL</li><li>.//gmd:transferOptions//gmd:CI_OnlineResource[.//gmd:protocol/gco:CharacterString/text() = "WWW:DOWNLOAD-URL"]//che:LocalisedURL</li><li>.//srv:connectPoint//gmd:linkage//che:LocalisedURL</li></ul>|
|Description| |


Example:
```xml
<gmd:CI_OnlineResource>
  <gmd:linkage xsi:type="che:PT_FreeURL_PropertyType">
  <gmd:URL>...</gmd:URL>
  <che:PT_FreeURL>
    <che:URLGroup>
      <che:LocalisedURL locale="#EN">
        https://www.bafu.admin.ch/bafu/en/home/office/divisions-sections/noise-and-nir-division.html
      </che:LocalisedURL>
      </che:URLGroup>
  </che:PT_FreeURL>
  </gmd:linkage>
  <gmd:protocol>...</gmd:protocol>
</gmd:CI_OnlineResource>
```

<a name="definition-of-dcp-rights"></a>
#### Definition of `dct:rights`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Terms of use |
|ISO-19139_che XPath|The first one in the following order:<ul><li>//gmd:resourceConstraints//gmd:otherConstraints//gmd:LocalicedCharacterString</li><li>//gmd:linkage//che:LocalisedURL</li></ul>This applies to texts in DE and FR: <ul><li>NonCommercialAllowed-CommercialAllowed-ReferenceNotRequired<ul><li>Freie Nutzung</li><li>Utilisation libre</li></ul></li><li>NonCommercialAllowed-CommercialAllowed-ReferenceRequired<ul><li>Freie Nutzung. Quellenangabe ist Pflicht.</li><li>Utilisation libre. Obligation d’indiquer la source.</li></ul></li><li>NonCommercialAllowed-CommercialWithPermission-ReferenceNotRequired<ul><li>Freie Nutzung. Kommerzielle Nutzung nur mit Bewilligung des Datenlieferanten zulässig.</li><li>Utilisation libre. Utilisation à des fins commerciales uniquement avec l’autorisation du fournisseur des données.</li></ul></li><li>NonCommercialAllowed-CommercialWithPermission-ReferenceRequired<ul><li>Freie Nutzung. Quellenangabe ist Pflicht. Kommerzielle Nutzung nur mit Bewilligung des Datenlieferanten zulässig.</li><li>Utilisation libre. Obligation d’indiquer la source. Utilisation commerciale uniquement avec l’autorisation du fournisseur des données.</li></ul></li></ul>|
|Description| |

Example:
```xml
<gmd:otherConstraints xsi:type="gmd:PT_FreeText_PropertyType">
    <gco:CharacterString>Freie Nutzung</gco:CharacterString>
    <gmd:PT_FreeText>
      <gmd:textGroup>
        <gmd:LocalisedCharacterString locale="#DE">Freie Nutzung</gmd:LocalisedCharacterString>
      </gmd:textGroup>
    </gmd:PT_FreeText>
</gmd:otherConstraints>
```

<a name="definition-of-dcp-license"></a>
#### Definition of `dct:license`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Currently not implemented |
|ISO-19139_che XPath| - |
|Description| |


<a name="definition-of-dcp-identifier"></a>
#### Definition of `dct:identifier`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Currently not implemented |
|ISO-19139_che XPath| - |
|Description| |


<a name="definition-of-dcp-downloadURL"></a>
#### Definition of `dcat:downloadURL`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Download |
|ISO-19139_che XPath|.//gmd:transferOptions//gmd:CI_OnlineResource[.//gmd:protocol/gco:CharacterString/text()[contains(.,"WWW:DOWNLOAD")]]//che:LocalisedURL|
|Description| |


Example:
```xml
<gmd:CI_OnlineResource>
  <gmd:linkage xsi:type="che:PT_FreeURL_PropertyType">
    <che:PT_FreeURL>
      <che:URLGroup>
        <che:LocalisedURL locale="#DE">http://data.geo.admin.ch/ch.blw.klimaeignung-kulturland/data.zip</che:LocalisedURL>
      </che:URLGroup>
    </che:PT_FreeURL>
  </gmd:linkage>
  <gmd:protocol>
    <gco:CharacterString>WWW:DOWNLOAD-URL</gco:CharacterString>
  </gmd:protocol>
  <gmd:description xsi:type="gmd:PT_FreeText_PropertyType">...</gmd:description>
  <gmd:function>...</gmd:function>
</gmd:CI_OnlineResource>
```

<a name="definition-of-dcp-byteSize"></a>
#### Definition of `dcat:byteSize`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Currently not implemented|
|ISO-19139_che XPath| - |
|Description| |


<a name="definition-of-dcp-mediaType"></a>
#### Definition of `dcat:mediaType`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Format |
|ISO-19139_che XPath|<ul><li>.//gmd:distributionInfo//gmd:distributionFormat//gmd:name/gco:CharacterString</li><li>//gmd:identificationInfo//srv:serviceType/gco:LocalName</li></ul>|
|Description| |


Example:
```xml
<gmd:distributionFormat xlink:show="embed">
  <gmd:MD_Format>
    <gmd:name>
      <gco:CharacterString>GeoTIFF</gco:CharacterString>
    </gmd:name>
    <gmd:version>...</gmd:version>
  </gmd:MD_Format>
</gmd:distributionFormat>
```

<a name="definition-of-dcp-format"></a>
#### Definition of `dct:format`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Currently not implemented |
|ISO-19139_che XPath| - |
|Description| |


<a name="definition-of-dcp-coverage"></a>
#### Definition of `dct:coverage`

|             |             |
|-------------|-------------|
|Display name on opendata.swiss| Currently not implemented |
|ISO-19139_che XPath| - |
|Description| |


