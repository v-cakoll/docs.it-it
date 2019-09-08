---
title: Mapping tra vincoli XML Schema (XSD) univoci e vincoli di dataset
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 4aa94dfaf088a2a934c8901e2720f166d3a38dae
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784417"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a>Mapping tra vincoli XML Schema (XSD) univoci e vincoli di dataset
In uno schema XSD (XML Schema Definition Language), l'elemento **Unique** specifica il vincolo di univocità per un elemento o un attributo. Durante il processo di conversione di un XML Schema in uno schema relazionale, viene eseguito il mapping del vincolo univoco specificato su un elemento o un attributo dell'XML Schema a un vincolo univoco del tipo <xref:System.Data.DataTable> nel tipo <xref:System.Data.DataSet> corrispondente generato.  
  
 Nella tabella seguente vengono descritti gli attributi **msdata** che è possibile specificare nell'elemento **Unique** .  
  
|Nome attributo|Descrizione|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Se questo attributo viene specificato, il relativo valore viene usato come nome del vincolo. In caso contrario, l'attributo **Name** fornisce il valore del nome del vincolo.|  
|**msdata:PrimaryKey**|Se `PrimaryKey="true"` è presente nell'elemento **Unique** , viene creato un vincolo unique con la proprietà **IsPrimaryKey** impostata su **true**.|  
  
 Nell'esempio seguente viene illustrato un XML Schema che utilizza l'elemento **Unique** per specificare un vincolo di univocità.  
  
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
  
 L'elemento **Unique** nello schema specifica che per tutti gli elementi **Customers** in un'istanza del documento, il valore dell'elemento figlio **CustomerID** deve essere univoco. Durante la compilazione del **set di dati**, il processo di mapping legge questo schema e genera la tabella seguente:  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 Il processo di mapping crea anche un vincolo UNIQUE nella colonna **CustomerID** , come illustrato nel set di **dati**seguente. Per semplicità vengono mostrate solo le proprietà rilevanti.  
  
```  
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
  
 Nel **set di dati** generato la proprietà **IsPrimaryKey** è impostata su **false** per il vincolo UNIQUE. La proprietà **Unique** della colonna indica che i valori della colonna **CustomerID** devono essere univoci, ma possono essere un riferimento null, come specificato dalla proprietà **AllowDBNull** della colonna.  
  
 Se si modifica lo schema e si imposta il valore dell'attributo **msdata: PrimaryKey** facoltativo su **true**, viene creato il vincolo UNIQUE nella tabella. La proprietà della colonna **AllowDBNull** è impostata su **false**e la proprietà **IsPrimaryKey** del vincolo è impostata su **true**, rendendo quindi la colonna **CustomerID** una colonna chiave primaria.  
  
 È possibile specificare un vincolo univoco per una combinazione di elementi o attributi nell'XML Schema. Nell'esempio seguente viene illustrato come specificare che una combinazione di valori **CustomerID** e **CompanyName** deve essere univoca per tutti **i clienti** in qualsiasi istanza, aggiungendo un altro elemento **xs: Field** nello schema.  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 Si tratta del vincolo creato nel **set di dati**risultante.  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a>Vedere anche

- [Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generazione di relazioni tra DataSet da XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
