---
title: Mapping tra vincoli di chiave XML Schema (XSD) e vincoli di dataset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6b999e6b1d6d73f107b7e1f4cb0d7e14c099a1f6
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a>Mapping tra vincoli di chiave XML Schema (XSD) e vincoli di dataset
In uno schema, è possibile specificare un vincolo di chiave su un elemento o attributo mediante la **chiave** elemento. È necessario che nell'elemento o nell'attributo per cui viene specificato il vincolo siano presenti valori univoci in qualsiasi istanza dello schema e che non sia presente alcun valore null.  
  
 Il vincolo key è simile al vincolo univoco, ma nella colonna per cui viene specificato un vincolo key non sono consentiti valori null.  
  
 Nella tabella seguente vengono illustrati il **msdata** gli attributi che è possibile specificare nel **chiave** elemento.  
  
|Nome attributo|Descrizione|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Se questo attributo viene specificato, il relativo valore viene usato come nome del vincolo. In caso contrario, il **nome** attributo fornisce il valore del nome del vincolo.|  
|**msdata:PrimaryKey**|Se `PrimaryKey="true"` è presente, il **IsPrimaryKey** vincolo è impostata su **true**, rendendo così una chiave primaria. Il **AllowDBNull** colonna è impostata su **false**, perché le chiavi primarie non sono consentiti valori null.|  
  
 Durante la conversione dello schema in cui è stato specificato un vincolo di chiave, il processo di mapping consente di creare un vincolo unique nella tabella con il **AllowDBNull** proprietà column impostata sulla **false** per ogni colonna di vincolo. Il **IsPrimaryKey** anche proprietà del vincolo unique è impostata su **false** a meno che non è stato specificato `msdata:PrimaryKey="true"` sul **chiave** elemento. Queste impostazioni sono identiche a quelle di un vincolo univoco nello schema in cui `PrimaryKey="true"`.  
  
 Nell'esempio di schema seguente, il **chiave** elemento specifica il vincolo di chiave per la **CustomerID** elemento.  
  
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
  
 Il **chiave** elemento specifica che i valori del **CustomerID** elemento figlio dell'elemento di **clienti** elemento deve contenere valori univoci e non può contenere valori null. Durante la conversione dello schema XSD (XML Schema Definition Language), la seguente tabella viene creata dal processo di mapping:  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 Il mapping di XML Schema crea anche un **UniqueConstraint** sul **CustomerID** colonna, come illustrato di seguito <xref:System.Data.DataSet>. Per semplicità vengono mostrate solo le proprietà rilevanti.  
  
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
  
 Nel **DataSet** generato, il **IsPrimaryKey** proprietà del **UniqueConstraint** è impostato su **true** perché lo schema specifica `msdata:PrimaryKey="true"` nel **chiave** elemento.  
  
 Il valore della **ConstraintName** proprietà del **UniqueConstraint** nel **set di dati** è il valore della **msdata: ConstraintName** attributo specificato nella **chiave** elemento nello schema.  
  
## <a name="see-also"></a>Vedere anche  
 [Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [Generazione di relazioni tra DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
