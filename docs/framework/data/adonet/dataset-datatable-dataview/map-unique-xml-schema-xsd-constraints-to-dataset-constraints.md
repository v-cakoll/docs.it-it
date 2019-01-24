---
title: Mapping tra vincoli XML Schema (XSD) univoci e vincoli di dataset
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: c35dcadfb40fcb73104af7ee7456e64a68c9e023
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677068"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a>Mapping tra vincoli XML Schema (XSD) univoci e vincoli di dataset
In uno schema di XML Schema definition language (XSD), il **univoco** elemento specifica il vincolo di univocità su un elemento o attributo. Durante il processo di conversione di un XML Schema in uno schema relazionale, viene eseguito il mapping del vincolo univoco specificato su un elemento o un attributo dell'XML Schema a un vincolo univoco del tipo <xref:System.Data.DataTable> nel tipo <xref:System.Data.DataSet> corrispondente generato.  
  
 La tabella seguente descrive la **msdata** attributi che è possibile specificare nel **univoco** elemento.  
  
|Nome attributo|Descrizione|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Se questo attributo viene specificato, il relativo valore viene usato come nome del vincolo. In caso contrario, il **nome** attributo fornisce il valore del nome del vincolo.|  
|**msdata:PrimaryKey**|Se `PrimaryKey="true"` è presente nel **univoco** elemento, un vincolo unique viene creato con il **IsPrimaryKey** impostata su **true**.|  
  
 Nell'esempio seguente viene illustrato un XML Schema che utilizza il **univoco** elemento per specificare un vincolo di univocità.  
  
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
  
 Il **univoco** elemento nello schema specifica che per tutte le **clienti** elementi in un documento di istanza, il valore della **CustomerID** elemento figlio deve essere univoco. Creazione di **set di dati**, il processo di mapping legge questo schema e genera la tabella seguente:  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 Il processo di mapping crea anche un vincolo unique nel **CustomerID** colonna, come illustrato di seguito **DataSet**. Per semplicità vengono mostrate solo le proprietà rilevanti.  
  
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
  
 Nel **set di dati** che viene generato, il **IsPrimaryKey** viene impostata su **False** per il vincolo univoco. Il **univoci** proprietà sulla colonna indica che il **CustomerID** valori di colonna devono essere univoci (ma possono anche essere un riferimento null, come specificato dal **AllowDBNull** proprietà della colonna).  
  
 Se si modifica lo schema e impostare l'opzione facoltativa **msdata: PrimaryKey** al valore dell'attributo **True**, viene creato il vincolo unique nella tabella. Il **AllowDBNull** colonna viene impostata su **False**e il **IsPrimaryKey** proprietà del vincolo viene impostata su **True**, rendendo il **CustomerID** colonna di una colonna chiave primaria.  
  
 È possibile specificare un vincolo univoco per una combinazione di elementi o attributi nell'XML Schema. Nell'esempio seguente viene illustrato come specificare che una combinazione di **CustomerID** e **CompanyName** valori devono essere univoci per tutti i **clienti** in qualsiasi istanza da aggiunta di un'altra **xs: field** elemento nello schema.  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 Questo è il vincolo creato nel risultante **set di dati**.  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a>Vedere anche
- [Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generazione di relazioni tra DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
