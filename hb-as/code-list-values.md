# Code list values

**Purpose**: Verify whether all attributes whose value type is a code list take the values set out therein

**Prerequisites**

**Test method**

When an attribute has a code list as its type, verify that the values comply with the definitions and include the values set out in Annex II, III and IV of the Implementing Rule. To pass this test verify that any instance of an attribute:

* takes only values explicitly specified in the INSPIRE code list register when the code list‘s extensibility is 'none'.
* takes only a value explicitly specified in the INSPIRE code list register or shall take a value that is narrower (i.e. more specific) than those explicitly specified in the application schema when the code list‘s extensibility is 'narrower'.
* takes values explicitly specified in the INSPIRE code list register when the code list‘s extensibility is 'open' or if a value is not one of the values listed in the code list register check that any extensions do not overlap with the code lists that are defined in Annexes II, III and IV of the Implementing Rule and that all extensions conform to the requirements (This last check is a manual test).

The following checks are performed for every feature in the dataset, for the not extensible codelists:

* Check that all the [referenceHabitatTypeId](#referenceHabitatTypeId) elements has a xlink:href attribute pointing to a [valid value](#validValue1). If the check fails report [disallowedCodeListValue](#disallowedCodeListValue).

* Check that all the [referenceHabitatTypeScheme](#referenceHabitatTypeScheme) elements has a xlink:href attribute pointing to a [valid value](#validValue2). If the check fails report [disallowedCodeListValue](#disallowedCodeListValue).

* Check that all the [qualifierLocalName](#qualifierLocalName) elements (if present) has a xlink:href attribute pointing to a [valid value](#validValue3). If the check fails report [disallowedCodeListValue](#disallowedCodeListValue).

* Check that all the [referenceSpeciesId](#referenceSpeciesId) elements has a xlink:href attribute pointing to a [valid value](#validValue4). If the check fails report [disallowedCodeListValue](#disallowedCodeListValue).

* Check that all the [referenceSpeciesScheme](#referenceSpeciesScheme) elements has a xlink:href attribute pointing to a [valid value](#validValue5). If the check fails report [disallowedCodeListValue](#disallowedCodeListValue).


| <a name="validValue1"></a> Valid values for xlink:href attribute of [referenceHabitatTypeId](#referenceHabitatTypeId) element are available in the INSPIRE Registry.<br>Note: The following codelists are externally governed.| 
| ---- | 
| http://inspire.ec.europa.eu/codelist/EunisHabitatTypeCodeValue <br> http://inspire.ec.europa.eu/codelist/HabitatsDirectiveCodeValue <br> http://inspire.ec.europa.eu/codelist/MarineStrategyFrameworkDirectiveCodeValue |

| <a name="validValue2"></a> Valid values for xlink:href attribute of [referenceHabitatTypeScheme](#referenceHabitatTypeScheme) element are available in the INSPIRE Registry| 
| ---- | 
| http://inspire.ec.europa.eu/codelist/ReferenceHabitatTypeSchemeValue | 

| <a name="validValue3"></a> Valid values for xlink:href attribute of [qualifierLocalName](#qualifierLocalName) element are available in the INSPIRE Registry| 
| ---- | 
| http://inspire.ec.europa.eu/codelist/QualifierLocalNameValue | 

| <a name="validValue4"></a> Valid values for xlink:href attribute of [referenceSpeciesId](#referenceSpeciesId) element are available in the INSPIRE Registry. <br> Note: The following codelists are externally governed.| 
| ---- | 
| http://inspire.ec.europa.eu/codelist/EuNomenCodeValue <br> http://inspire.ec.europa.eu/codelist/EunisSpeciesCodeValue <br> http://inspire.ec.europa.eu/codelist/NatureDirectivesCodeValue |

| <a name="validValue5"></a> Valid values for xlink:href attribute of [referenceSpeciesScheme](#referenceSpeciesScheme) element are available in the INSPIRE Registry| 
| ---- | 
| http://inspire.ec.europa.eu/codelist/ReferenceSpeciesSchemeValue | 


**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (1)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (3)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (1)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (2)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (3)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (4)

**Test type**: Automated + Manual check (if required)

**Notes**

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
disallowedCodeListValue <a name="disallowedCodeListValue"/> | XML document '$filename', $featureType '$gmlid': The property '$propertyName' has a value '$value' that is not one of the allowed values listed at $codelist. Please note that the URIs of all code list values from the INSPIRE Registry shall be referenced using the http protocol. 

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                                               |  XPath expression				|Multiplicity       |Voidable
---------------------------------------------------------- | -------------------------------|-------------------|---------
referenceHabitatTypeId <a name="referenceHabitatTypeId"></a> | //schema-element(hb:Habitat)/hb:HabitatTypeCoverType/hb:referenceHabitatTypeId/@xlink:href | 1 (1..* for the parent) | No
referenceHabitatTypeScheme <a name="referenceHabitatTypeScheme"></a> | //schema-element(hb:Habitat)/hb:HabitatTypeCoverType/hb:referenceHabitatTypeScheme/@xlink:href | 1 (1..* for the parent) | No
qualifierLocalName <a name ="qualifierLocalName"></a> | //schema-element(hb:Habitat)/hb:habitatSpecies/hb:HabitatSpeciesType/hb:localSpeciesName/hb:LocalNameType/hb:qualifierLocalName/@xlink:href | 1 (0..\* for the parent) | Yes
qualifierLocalName <a name ="qualifierLocalName"></a> | //schema-element(hb:Habitat)/hb:habitat/hb:HabitatTypeCoverType/hb:localHabitatName/hb:LocalNameType/hb:qualifierLocalName/@xlink:href | 1 (0..1 for the parent) | Yes
qualifierLocalName <a name ="qualifierLocalName"></a> | //schema-element(hb:Habitat)/hb:habitatVegetation/hb:HabitatVegetationType/hb:localVegetationName/hb:LocalNameType/hb:qualifierLocalName/@xlink:href | 1 (0..\* for the parent) | Yes
referenceSpeciesId <a name="referenceSpeciesId"></a>  | //schema-element(hb:Habitat)/hb:habitatSpecies/hb:HabitatSpeciesType/hb:referenceSpeciesId/@xlink:href | 1 (0..\* for the parent) | No
referenceSpeciesScheme <a name="referenceSpeciesScheme"></a> | //schema-element(hb:Habitat)/hb:habitatSpecies/hb:HabitatSpeciesType/hb:referenceSpeciesScheme/@xlink:href | 1 (0..\* for the parent) | No
