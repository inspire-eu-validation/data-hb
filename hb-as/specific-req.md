# Habitats and Biotopes theme-specific requirements

**Purpose**: Verify that the features provided in the dataset adhere to the theme-specific requirements specified in the INSPIRE application schema.

**Prerequisites**

**Test method**

The following check is performed for all features in the dataset.

* Check that at least one habitat type according to a (pan-european) [referenceHabitatTypeScheme](#referenceHabitatTypeScheme) listed in the [ReferenceHabitatTypeSchemeValue](http://inspire.ec.europa.eu/codelist/ReferenceHabitatTypeSchemeValue) code list is available (This encoding is intended to allow for queries on habitat types on a pan-European harmonized level).


**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (2)
* [TG DS-HB](./README.md#ref_TG_DS_HB) 5.3.1.2

**Test type**: Automatic

**Notes** 

IR Requirement Annex IV Section 17.5: It is mandatory to make available at least one habitat type according to a (pan-european) referenceHabitatTypeScheme listed in the ReferenceHabitatTypeSchemeValue code list. This encoding is intended to allow for queries on habitat types on a pan-European harmonized level.

Verify that the theme-specific requirements that are specified in the UML model of the application schema are met, i.e. validate features against the theme-specific requirements. For unmet theme-specific requirements report [constraintViolation](#constraintViolation).

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
constraintViolation <a name="constraintViolation"/>  |  XML document '$filename', $featureType '$gmlid': The constraint '$constraint' is violated.

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                                               |  XPath expression				|Multiplicity       |Voidable
---------------------------------------------------------- | -------------------------------|-------------------|---------
referenceHabitatTypeScheme <a name="referenceHabitatTypeScheme"></a> | //schema-element(hb:Habitat)/hb:habitat/hb:HabitatTypeCoverType/hb:referenceHabitatTypeScheme/@xlink:href | 1 (1..* for the parent) | No
