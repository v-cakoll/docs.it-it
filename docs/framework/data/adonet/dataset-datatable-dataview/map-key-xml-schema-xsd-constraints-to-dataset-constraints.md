---
title: Mapping tra vincoli di chiave XML Schema (XSD) e vincoli di dataset
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: d6fcdae77c2f2ac07ea5cd16baf07cd5de36d25b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203473"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a>Mapping tra vincoli di chiave XML Schema (XSD) e vincoli di dataset
In uno schema è possibile specificare un vincolo di chiave per un elemento o un attributo usando l'elemento **Key** . È necessario che nell'elemento o nell'attributo per cui viene specificato il vincolo siano presenti valori univoci in qualsiasi istanza dello schema e che non sia presente alcun valore null.  
  
 Il vincolo key è simile al vincolo univoco, ma nella colonna per cui viene specificato un vincolo key non sono consentiti valori null.  
  
 Nella tabella seguente vengono descritti gli attributi **msdata** che è possibile specificare nell'elemento **Key** .  
  
|Nome attributo|Descrizione|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Se questo attributo viene specificato, il relativo valore viene usato come nome del vincolo. In caso contrario, l'attributo **Name** fornisce il valore del nome del vincolo.|  
|**msdata:PrimaryKey**|Se `PrimaryKey="true"` è presente, la proprietà del vincolo **IsPrimaryKey** è impostata su **true**, rendendola pertanto una chiave primaria. La proprietà della colonna **AllowDBNull** è impostata su **false**, in quanto le chiavi primarie non possono contenere valori null.|  
  
 Nella conversione dello schema in cui viene specificato un vincolo di chiave, il processo di mapping crea un vincolo UNIQUE nella tabella con la proprietà della colonna **AllowDBNull** impostata su **false** per ogni colonna nel vincolo. Anche la proprietà **IsPrimaryKey** del vincolo UNIQUE è impostata su **false** , a meno che non sia `msdata:PrimaryKey="true"` stato specificato sull'elemento **Key** . Queste impostazioni sono identiche a quelle di un vincolo univoco nello schema in cui `PrimaryKey="true"`.  
  
 Nell'esempio di schema seguente l'elemento **Key** specifica il vincolo key nell'elemento **CustomerID** .  
  
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
  
 L'elemento **Key** specifica che i valori dell'elemento figlio **CustomerID** dell'elemento **Customers** devono contenere valori univoci e non possono avere valori null. Durante la conversione dello schema XSD (XML Schema Definition Language), la seguente tabella viene creata dal processo di mapping:  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 Il mapping di XML Schema crea anche un oggetto **UniqueConstraint** sulla colonna **CustomerID** , come illustrato di seguito <xref:System.Data.DataSet>. Per semplicità vengono mostrate solo le proprietà rilevanti.  
  
```  
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
  
 Nel **set di dati** generato la proprietà **IsPrimaryKey** di **UniqueConstraint** è impostata su **true** perché lo schema specifica `msdata:PrimaryKey="true"` nell'elemento **Key** .  
  
 Il valore della proprietà **ConstraintName** di **UniqueConstraint** nel **DataSet** corrisponde al valore dell'attributo **msdata: ConstraintName** specificato nell'elemento **Key** nello schema.  
  
## <a name="see-also"></a>Vedere anche

- [Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generazione di relazioni tra DataSet da XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
