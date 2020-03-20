---
title: Vincoli e relazioni di XML Schema
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 2388d7c277ba1f01bea8d419e5aedf487b843ed7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150714"
---
# <a name="xml-schema-constraints-and-relationships"></a>Vincoli e relazioni di XML Schema
In uno schema XSD (XML Schema Definition Language) è possibile specificare vincoli (vincoli univoci, chiave e keyref) e relazioni (utilizzando l'annotazione **msdata:Relationship).** In questo argomento viene spiegato come vengono interpretati i vincoli e le relazioni specificati in XML Schema per generare il tipo <xref:System.Data.DataSet>.  
  
 In generale, in uno schema XML si specifica l'annotazione **msdata:Relationship** se si desidera generare solo relazioni nel **DataSet**. Per ulteriori informazioni, vedere [Generazione di relazioni con DataSet da XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md). Specificare i vincoli (univoco, key e keyref) se si desidera generare vincoli nel **DataSet**. Notare che i vincoli key e keyref vengono usati anche per generare relazioni, come spiegato successivamente in questo argomento.  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a>Generazione di una relazione dai vincoli key e keyref  
 Anziché specificare l'annotazione **msdata:Relationship,** è possibile specificare i vincoli key e keyref, utilizzati durante il processo di mapping dello schema XML per generare non solo i vincoli, ma anche la relazione nel **DataSet**. Tuttavia, se `msdata:ConstraintOnly="true"` si specifica nell'elemento **keyref,** il **DataSet** includerà solo i vincoli e non includerà la relazione.  
  
 Nell'esempio seguente viene illustrato uno schema XML che include gli elementi **Order** e **OrderDetail,** che non sono annidati. Nello schema vengono specificati anche i vincoli key e keyref.  
  
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
  
 Il **DataSet** generato durante il processo di mapping dello schema XML include le tabelle **Order** e **OrderDetail.** Inoltre, il **DataSet** include relazioni e vincoli. Nell'esempio seguente vengono illustrati tali vincoli e relazioni. Si noti che lo schema non specifica l'annotazione **msdata:Relationship;** i vincoli key e keyref vengono invece utilizzati per generare la relazione.  
  
```text
....ConstraintName: OrderNumberKey  
....Type: UniqueConstraint  
....Table: Order  
....Columns: OrderNumber  
....IsPrimaryKey: False  
  
....ConstraintName: OrderNoRef  
....Type: ForeignKeyConstraint  
....Table: OrderDetail  
....Columns: OrderNo  
....RelatedTable: Order  
....RelatedColumns: OrderNumber  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
```  
  
 Nell'esempio di schema precedente, gli elementi **Order** e **OrderDetail** non sono annidati. Nell'esempio di schema seguente tali elementi sono annidati. Tuttavia, non viene specificata alcuna annotazione **msdata:Relationship;** pertanto, viene considerata una relazione implicita. Per ulteriori informazioni, vedere [Eseguire il mapping di relazioni implicite tra elementi dello schema annidati](map-implicit-relations-between-nested-schema-elements.md). Nello schema vengono specificati anche i vincoli key e keyref.  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:integer" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
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
  
 Il DataSet risultante dal processo di mapping dello schema XML include due tabelle:The **DataSet** resulting from the XML Schema mapping process includes two tables:  
  
```text  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 Il **DataSet** include anche le due relazioni (una basata sull'annotazione **msdata:relationship** e l'altra in base ai vincoli key e keyref) e varie vincoli. Nell'esempio seguente vengono illustrati i vincoli e le relazioni.  
  
```text
..RelationName: Order_OrderDetail  
..ParentTable: Order  
..ParentColumns: Order_Id  
..ChildTable: OrderDetail  
..ChildColumns: Order_Id  
..ParentKeyConstraint: Constraint1  
..ChildKeyConstraint: Order_OrderDetail  
..Nested: True  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
  
..ConstraintName: OrderNumberKey  
..Type: UniqueConstraint  
..Table: Order  
..Columns: OrderNumber  
..IsPrimaryKey: False  
  
..ConstraintName: Constraint1  
..Type: UniqueConstraint  
..Table: Order  
..Columns: Order_Id  
..IsPrimaryKey: True  
  
..ConstraintName: Order_OrderDetail  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: Order_Id  
..RelatedTable: Order  
..RelatedColumns: Order_Id  
  
..ConstraintName: OrderNoRef  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: OrderNo  
..RelatedTable: Order  
..RelatedColumns: OrderNumber  
```  
  
 Se un vincolo keyref che fa riferimento a una tabella nidificata contiene l'annotazione **msdata:IsNested "true",** il **DataSet** creerà una singola relazione nidificata basata sul vincolo keyref e sul vincolo univoco/chiave correlato.  
  
## <a name="see-also"></a>Vedere anche

- [Derivazione della struttura relazionale di dataset da XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
