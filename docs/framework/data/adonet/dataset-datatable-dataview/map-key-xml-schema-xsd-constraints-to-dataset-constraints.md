---
title: Mapping tra vincoli di chiave XML Schema (XSD) e vincoli di dataset
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: 5ebf333b065157fa9497cc1471a45698663638e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150935"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a>Mapping tra vincoli di chiave XML Schema (XSD) e vincoli di dataset
In uno schema, è possibile specificare un vincolo di chiave su un elemento o un attributo utilizzando l'elemento **key.** È necessario che nell'elemento o nell'attributo per cui viene specificato il vincolo siano presenti valori univoci in qualsiasi istanza dello schema e che non sia presente alcun valore null.  
  
 Il vincolo key è simile al vincolo univoco, ma nella colonna per cui viene specificato un vincolo key non sono consentiti valori null.  
  
 Nella tabella seguente vengono descritti gli attributi **msdata** che è possibile specificare nell'elemento **key.**  
  
|Nome attributo|Descrizione|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Se questo attributo viene specificato, il relativo valore viene usato come nome del vincolo. In caso contrario, l'attributo **name** fornisce il valore del nome del vincolo.|  
|**msdata:PrimaryKey**|Se `PrimaryKey="true"` è presente, la proprietà del vincolo **IsPrimaryKey** è impostata su **true**, rendendola una chiave primaria. La proprietà della colonna **AllowDBNull** è impostata su **false**, perché le chiavi primarie non possono avere valori null.|  
  
 Nella conversione dello schema in cui viene specificato un vincolo di chiave, il processo di mapping crea un vincolo univoco nella tabella con la proprietà di colonna **AllowDBNull** impostata su **false** per ogni colonna nel vincolo. Anche la proprietà **IsPrimaryKey** del vincolo univoco è `msdata:PrimaryKey="true"` impostata su **false,** a meno che non sia stato specificato nell'elemento **chiave.** Queste impostazioni sono identiche a quelle di un vincolo univoco nello schema in cui `PrimaryKey="true"`.  
  
 Nell'esempio di schema seguente, l'elemento **key** specifica il vincolo di chiave per il **CustomerID** elemento.  
  
```xml  
<xs:schema id="cod"  
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
        <xs:element name="CompanyName" type="xs:string" minOccurs="0" />  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:key  msdata:PrimaryKey="true"  
       msdata:ConstraintName="KeyCustID"  
          name="KeyConstCustomerID" >  
     <xs:selector xpath=".//Customers" />  
     <xs:field xpath="CustomerID" />  
    </xs:key>  
 </xs:element>  
</xs:schema>
```  
  
 L'elemento **key** specifica che i valori dell'elemento figlio **CustomerID** dell'elemento **Customers** devono avere valori univoci e non possono avere valori null. Durante la conversione dello schema XSD (XML Schema Definition Language), la seguente tabella viene creata dal processo di mapping:  
  
```text  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 Il mapping dello schema XML crea inoltre un **uniqueConstraint** nella <xref:System.Data.DataSet>colonna **CustomerID,** come illustrato di seguito. Per semplicità vengono mostrate solo le proprietà rilevanti.  
  
```text  
      DataSetName: MyDataSet  
TableName: customers  
  ColumnName: CustomerID  
      AllowDBNull: False  
      Unique: True  
  ConstraintName: KeyCustID  
      Table: customers  
      Columns: CustomerID
      IsPrimaryKey: True  
```  
  
 Nel **DataSet** generato, la proprietà **IsPrimaryKey** di **UniqueConstraint** viene impostata `msdata:PrimaryKey="true"` su **true** perché lo schema specifica nell'elemento **key.**  
  
 Il valore della proprietà **ConstraintName** di **UniqueConstraint** nel **DataSet** è il valore dell'attributo **msdata:ConstraintName** specificato nell'elemento **key** nello schema.  
  
## <a name="see-also"></a>Vedere anche

- [Mapping tra vincoli XML Schema (XSD) e vincoli di dataset](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generazione di relazioni tra dataset da XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
