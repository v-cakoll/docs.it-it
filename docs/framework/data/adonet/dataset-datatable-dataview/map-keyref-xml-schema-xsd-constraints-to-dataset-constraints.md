---
title: Mapping tra vincoli keyref XML Schema (XSD) e vincoli di dataset
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 902b79b73f494ced0f54b29babff1b2e767bd47a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150883"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>Mapping tra vincoli keyref XML Schema (XSD) e vincoli di dataset
L'elemento **keyref** consente di stabilire collegamenti tra gli elementi all'interno di un documento. Questo elemento ha quindi una funzione simile a quella della relazione di chiave esterna in un database relazionale. Se uno schema specifica l'elemento **keyref,** l'elemento viene convertito durante il processo di mapping <xref:System.Data.DataSet>dello schema in un vincolo di chiave esterna corrispondente nelle colonne delle tabelle dell'oggetto . Per impostazione predefinita, l'elemento **keyref** genera anche una relazione con le proprietà **ParentTable**, **ChildTable**, **ParentColumn**e **ChildColumn** specificate nella relazione.  
  
 Nella tabella seguente vengono descritti gli attributi **msdata** che è possibile specificare nell'elemento **keyref.**  
  
|Nome attributo|Descrizione|  
|--------------------|-----------------|  
|**msdata:ConstraintOnly**|Se nell'elemento **keyref** dello schema viene specificato **"true",** viene creato un vincolo, ma non viene creata alcuna relazione. Se questo attributo non è specificato (o è impostato su **False**), sia il vincolo che la relazione vengono creati nel **DataSet**.|  
|**msdata:ConstraintName**|Se viene specificato l'attributo **ConstraintName,** il relativo valore viene utilizzato come nome del vincolo. In caso contrario, l'attributo **name** dell'elemento **keyref** nello schema fornisce il nome del vincolo nel **DataSet**.|  
|**msdata:UpdateRule**|Se l'attributo **UpdateRule** viene specificato nell'elemento **keyref** dello schema, il relativo valore viene assegnato alla proprietà del vincolo **UpdateRule** nel **DataSet**. In caso contrario, la proprietà **UpdateRule** viene impostata su **Cascade**.|  
|**msdata:DeleteRule**|Se l'attributo **DeleteRule** viene specificato nell'elemento **keyref** dello schema, il relativo valore viene assegnato alla proprietà del vincolo **DeleteRule** nel **DataSet**. In caso contrario, la proprietà **DeleteRule** viene impostata su **Cascade**.|  
|**msdata:AcceptRejectRule**|Se l'attributo **AcceptRejectRule** viene specificato nell'elemento **keyref** dello schema, il relativo valore viene assegnato alla proprietà del vincolo **AcceptRejectRule** nel **DataSet**. In caso contrario, la proprietà **AcceptRejectRule** viene impostata su **None**.|  
  
 L'esempio seguente contiene uno schema che specifica le relazioni **key** e **keyref** tra l'elemento figlio **OrderNumber** dell'elemento **Order** e l'elemento figlio **OrderNo** dell'elemento **OrderDetail.**  
  
 Nell'esempio, l'elemento figlio **OrderNumber** dell'elemento **OrderDetail** fa riferimento all'elemento figlio **chiave OrderNo** dell'elemento **Order.**  
  
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
  
 Il processo di mapping dello schema XSD (XML Schema Definition Language) produce il DataSet seguente con due tabelle:The XML Schema Definition Language (XSD) schema mapping process produces the following **DataSet** with two tables:  
  
```text  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 Inoltre, il DataSet definisce i vincoli seguenti:In addition, the **DataSet** defines the following constraints:  
  
- Un vincolo univoco nella tabella **Order.**  
  
    ```text
              Table: Order  
    Columns: OrderNumber
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- Relazione tra le tabelle **Order** e **OrderDetail.** Il **Nested** proprietà è impostata su **False** perché i due elementi non sono annidati nello schema.  
  
    ```text
              ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
- Un vincolo di chiave esterna nella tabella **OrderDetail.**  
  
    ```text  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo
    RelatedTable: Order  
    RelatedColumns: OrderNumber
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Mapping tra vincoli XML Schema (XSD) e vincoli di dataset](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generazione di relazioni tra dataset da XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
