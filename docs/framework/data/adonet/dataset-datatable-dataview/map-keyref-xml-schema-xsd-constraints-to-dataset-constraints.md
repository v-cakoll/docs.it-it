---
title: Mapping tra vincoli keyref XML Schema (XSD) e vincoli di dataset
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: b5ffe69886b08903feab4373b1cd5c5244b3b3b9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784517"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>Mapping tra vincoli keyref XML Schema (XSD) e vincoli di dataset
L'elemento **keyref** consente di stabilire collegamenti tra gli elementi all'interno di un documento. Questo elemento ha quindi una funzione simile a quella della relazione di chiave esterna in un database relazionale. Se uno schema specifica l'elemento **keyref** , l'elemento viene convertito durante il processo di mapping dello schema in un vincolo di chiave esterna corrispondente sulle colonne delle tabelle di <xref:System.Data.DataSet>. Per impostazione predefinita, l'elemento **keyref** genera anche una relazione, con le proprietà **ParentTable**, **ChildTable**, **parentColumn**e **ChildColumn vengono specificate** specificate nella relazione.  
  
 Nella tabella seguente vengono descritti gli attributi **msdata** che è possibile specificare nell'elemento **keyref** .  
  
|Nome attributo|Descrizione|  
|--------------------|-----------------|  
|**msdata:ConstraintOnly**|Se **ConstraintOnly = "true"** viene specificato nell'elemento **keyref** dello schema, viene creato un vincolo, ma non viene creata alcuna relazione. Se questo attributo non viene specificato (o è impostato su **false**), nel **set di dati**vengono creati sia il vincolo che la relazione.|  
|**msdata:ConstraintName**|Se viene specificato l'attributo **ConstraintName** , il relativo valore viene usato come nome del vincolo. In caso contrario, l'attributo **Name** dell'elemento **keyref** nello schema fornisce il nome del vincolo nel **set di dati**.|  
|**msdata:UpdateRule**|Se l'attributo **UpdateRule** viene specificato nell'elemento **keyref** dello schema, il relativo valore viene assegnato alla proprietà Constraint **UpdateRule** nel **set di dati**. In caso contrario, la proprietà **UpdateRule** viene impostata su **Cascade**.|  
|**msdata:DeleteRule**|Se l'attributo **DeleteRule** viene specificato nell'elemento **keyref** dello schema, il relativo valore viene assegnato alla proprietà Constraint **DeleteRule** nel **set di dati**. In caso contrario, la proprietà **DeleteRule** viene impostata su **Cascade**.|  
|**msdata:AcceptRejectRule**|Se l'attributo **AcceptRejectRule** viene specificato nell'elemento **keyref** dello schema, il relativo valore viene assegnato alla proprietà Constraint **AcceptRejectRule** nel **set di dati**. In caso contrario, la proprietà **AcceptRejectRule** è impostata su **None**.|  
  
 Nell'esempio seguente è contenuto uno schema che specifica le relazioni **Key** e **keyref** tra l'elemento figlio **OrderNumber** dell'elemento **Order** e l'elemento figlio **OrderNo** di **OrderDetail** elemento.  
  
 Nell'esempio, l'elemento figlio **OrderNumber** dell'elemento **OrderDetail** si riferisce all'elemento figlio Key **OrderNo** dell'elemento **Order** .  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="OrderDetail">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNo" type="xs:integer" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 Il processo di mapping dello schema XSD (XML Schema Definition Language) produce il **set di dati** seguente con due tabelle:  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 Inoltre, il **set di dati** definisce i vincoli seguenti:  
  
- Vincolo UNIQUE nella tabella **Order** .  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- Relazione tra le tabelle **Order** e **OrderDetail** . La proprietà **nidificata** è impostata su **false** perché i due elementi non sono annidati nello schema.  
  
    ```  
              ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
- Vincolo FOREIGN KEY nella tabella **OrderDetail** .  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generazione di relazioni tra DataSet da XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
