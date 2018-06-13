---
title: Vincoli e relazioni di XML Schema
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 4b62b6bafa9ceeafd250e722314c4bd6c594bf82
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759842"
---
# <a name="xml-schema-constraints-and-relationships"></a>Vincoli e relazioni di XML Schema
In uno schema di XML Schema definition language (XSD), è possibile specificare vincoli (univoci, vincoli key e keyref) e le relazioni (mediante il **msdata: Relationship** annotazione). In questo argomento viene spiegato come vengono interpretati i vincoli e le relazioni specificati in XML Schema per generare il tipo <xref:System.Data.DataSet>.  
  
 In generale, in uno Schema XML, specificare il **msdata: Relationship** annotazione, se si desidera generare solo le relazioni nel **DataSet**. Per ulteriori informazioni, vedere [la generazione di relazioni tra DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md). Specifica dei vincoli (univoci, key e keyref) se si desidera generare vincoli nel **DataSet**. Notare che i vincoli key e keyref vengono usati anche per generare relazioni, come spiegato successivamente in questo argomento.  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a>Generazione di una relazione dai vincoli key e keyref  
 Anziché specificare il **msdata: Relationship** annotazione, è possibile specificare vincoli key e keyref vengono utilizzati durante il processo di mapping di XML Schema per generare il nonsoloivincoli,maanchelarelazione **Set di dati**. Tuttavia, se si specifica `msdata:ConstraintOnly="true"` nel **keyref** elemento, il **DataSet** includerà solo i vincoli e non includerà la relazione.  
  
 Nell'esempio seguente viene illustrato uno Schema XML che include **ordine** e **OrderDetail** elementi, che non sono annidati. Nello schema vengono specificati anche i vincoli key e keyref.  
  
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
  
 Il **DataSet** che viene generato durante il processo di mapping include di XML Schema di **ordine** e **OrderDetail** tabelle. Inoltre, il **DataSet** include vincoli e relazioni. Nell'esempio seguente vengono illustrati tali vincoli e relazioni. Si noti che lo schema non specifica il **msdata: Relationship** annotazione; al contrario, i vincoli key e keyref vengono utilizzati per generare la relazione.  
  
```  
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
  
 Nell'esempio di schema precedente, il **ordine** e **OrderDetail** elementi non annidati. Nell'esempio di schema seguente tali elementi sono annidati. Tuttavia, non **msdata: Relationship** annotazione è specificata; pertanto, si presuppone che una relazione implicita. Per ulteriori informazioni, vedere [mappa implicito le relazioni tra elementi nidificati dello Schema](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md). Nello schema vengono specificati anche i vincoli key e keyref.  
  
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
  
 Il **DataSet** risultante dal processo di mapping di XML Schema include due tabelle:  
  
```  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 Il **DataSet** include anche le due relazioni (una basata sul **msdata: Relationship** annotazione e l'altra basata sui vincoli key e keyref) e diversi vincoli. Nell'esempio seguente vengono illustrati i vincoli e le relazioni.  
  
```  
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
  
 Se un vincolo keyref che fa riferimento a una tabella nidificata contiene il **msdata: IsNested = "true"** annotazione, il **DataSet** creerà un'unica relazione annidata basata sul vincolo keyref e vincolo univoco/key correlato.  
  
## <a name="see-also"></a>Vedere anche  
 [Derivazione della struttura relazionale di DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
