---
title: Mapping tra vincoli di chiave XML Schema (XSD) e vincoli di dataset
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: 46a980f06198c6f06bb13824c65cfb5309eec154
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034229"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a>Mapping tra vincoli di chiave XML Schema (XSD) e vincoli di dataset
In uno schema, è possibile specificare un vincolo di chiave su un elemento o attributo mediante la **chiave** elemento. È necessario che nell'elemento o nell'attributo per cui viene specificato il vincolo siano presenti valori univoci in qualsiasi istanza dello schema e che non sia presente alcun valore null.  
  
 Il vincolo key è simile al vincolo univoco, ma nella colonna per cui viene specificato un vincolo key non sono consentiti valori null.  
  
 La tabella seguente descrive la **msdata** attributi che è possibile specificare nel **chiave** elemento.  
  
|Nome attributo|Descrizione|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Se questo attributo viene specificato, il relativo valore viene usato come nome del vincolo. In caso contrario, il **nome** attributo fornisce il valore del nome del vincolo.|  
|**msdata:PrimaryKey**|Se `PrimaryKey="true"` è presente, il **IsPrimaryKey** vincolo viene impostata su **true**, rendendo così una chiave primaria. Il **AllowDBNull** colonna viene impostata su **false**, perché le chiavi primarie non sono consentiti valori null.|  
  
 Durante la conversione dello schema in cui viene specificato un vincolo di chiave, il processo di mapping consente di creare un vincolo unique nella tabella con il **AllowDBNull** proprietà column impostata sulla **false** per ogni colonna di vincolo. Il **IsPrimaryKey** del vincolo univoco viene inoltre impostata su **false** a meno che non è stato specificato `msdata:PrimaryKey="true"` sulla **chiave** elemento. Queste impostazioni sono identiche a quelle di un vincolo univoco nello schema in cui `PrimaryKey="true"`.  
  
 Nell'esempio di schema seguente, il **key** elemento specifica il vincolo di chiave per il **CustomerID** elemento.  
  
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
  
 Il **chiave** elemento specifica che i valori del **CustomerID** elemento figlio dell'elemento il **clienti** elemento deve contenere valori univoci e non sono consentiti valori null. Durante la conversione dello schema XSD (XML Schema Definition Language), la seguente tabella viene creata dal processo di mapping:  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 Il mapping di XML Schema crea anche un **UniqueConstraint** nel **CustomerID** colonna, come illustrato di seguito <xref:System.Data.DataSet>. Per semplicità vengono mostrate solo le proprietà rilevanti.  
  
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
  
 Nel **set di dati** che viene generato, il **IsPrimaryKey** proprietà del **UniqueConstraint** è impostata su **true** perché lo schema specifica `msdata:PrimaryKey="true"` nella **chiave** elemento.  
  
 Il valore del **ConstraintName** proprietà delle **UniqueConstraint** nel **set di dati** è il valore della **msdata: ConstraintName** attributo specificato nella **chiave** elemento nello schema.  
  
## <a name="see-also"></a>Vedere anche

- [Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generazione di relazioni tra DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
