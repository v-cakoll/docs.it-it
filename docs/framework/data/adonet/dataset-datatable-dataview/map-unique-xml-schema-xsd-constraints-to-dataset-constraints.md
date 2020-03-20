---
title: Mapping tra vincoli XML Schema (XSD) univoci e vincoli di dataset
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 8bcf705ce4415929e685be79f813846bbb40bb36
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150844"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a>Mapping tra vincoli XML Schema (XSD) univoci e vincoli di dataset
In uno schema XSD (XML Schema Definition Language), l'elemento **unique** specifica il vincolo di unicità su un elemento o un attributo. Durante il processo di conversione di un XML Schema in uno schema relazionale, viene eseguito il mapping del vincolo univoco specificato su un elemento o un attributo dell'XML Schema a un vincolo univoco del tipo <xref:System.Data.DataTable> nel tipo <xref:System.Data.DataSet> corrispondente generato.  
  
 Nella tabella seguente vengono descritti gli attributi **msdata** che è possibile specificare nell'elemento **univoco.**  
  
|Nome attributo|Descrizione|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Se questo attributo viene specificato, il relativo valore viene usato come nome del vincolo. In caso contrario, l'attributo **name** fornisce il valore del nome del vincolo.|  
|**msdata:PrimaryKey**|Se `PrimaryKey="true"` è presente nell'elemento **unique,** viene creato un vincolo univoco con la proprietà **IsPrimaryKey** impostata su **true**.|  
  
 Nell'esempio seguente viene illustrato uno schema XML che utilizza l'elemento **unique** per specificare un vincolo di unicità.  
  
```xml  
<xs:schema id="SampleDataSet"
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:integer"
           minOccurs="0"/>  
        <xs:element name="CompanyName" type="xs:string"
           minOccurs="0"/>  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
  
 <xs:element name="SampleDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:unique     msdata:ConstraintName="UCustID"     name="UniqueCustIDConstr" >       <xs:selector xpath=".//Customers" />       <xs:field xpath="CustomerID" />     </xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 L'elemento **unique** nello schema specifica che per tutti gli elementi **Customers** in un'istanza del documento, il valore dell'elemento figlio **CustomerID** deve essere univoco. Nella compilazione del **DataSet**, il processo di mapping legge questo schema e genera la tabella seguente:  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 Il processo di mapping crea inoltre un vincolo univoco nella colonna **CustomerID,** come illustrato nel **DataSet**seguente. Per semplicità vengono mostrate solo le proprietà rilevanti.  
  
```text  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID       Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID
      IsPrimaryKey: False  
```  
  
 Nel **DataSet** generato, la proprietà **IsPrimaryKey** è impostata su **False** per il vincolo univoco. La proprietà **unique** nella colonna indica che i valori della colonna **CustomerID** devono essere univoci (ma possono essere un riferimento null, come specificato dalla proprietà **AllowDBNull** della colonna).  
  
 Se si modifica lo schema e si imposta il valore facoltativo dell'attributo **msdata:PrimaryKey** su **True**, il vincolo univoco viene creato nella tabella. La proprietà della colonna **AllowDBNull** è impostata su **False**e la proprietà **IsPrimaryKey** del vincolo è impostata su **True**, rendendo così la colonna **CustomerID** una colonna di chiave primaria.  
  
 È possibile specificare un vincolo univoco per una combinazione di elementi o attributi nell'XML Schema. Nell'esempio seguente viene illustrato come specificare che una combinazione di **CustomerID** e **CompanyName** valori devono essere univoci per tutti i **clienti** in qualsiasi istanza, aggiungendo un altro **xs:field** elemento nello schema.  
  
```xml  
      <xs:unique
         msdata:ConstraintName="SomeName"
         name="UniqueCustIDConstr" >
  <xs:selector xpath=".//Customers" />
  <xs:field xpath="CustomerID" />
  <xs:field xpath="CompanyName" />
</xs:unique>  
```  
  
 Si tratta del vincolo creato nel **DataSet**risultante.  
  
```text  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a>Vedere anche

- [Mapping tra vincoli XML Schema (XSD) e vincoli di dataset](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generazione di relazioni tra dataset da XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
