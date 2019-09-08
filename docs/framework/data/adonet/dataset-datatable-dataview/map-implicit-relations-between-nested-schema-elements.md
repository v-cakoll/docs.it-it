---
title: Mapping di relazioni implicite tra elementi di schemi annidati
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: f4b1b9e45f0cda976719b991c336463e0af05f12
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784432"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a>Mapping di relazioni implicite tra elementi di schemi annidati
È possibile che in uno schema XSD (XML Schema Definition Language) siano presenti tipi complessi annidati uno all'interno dell'altro. In questo caso, le impostazioni di mapping predefinite vengono applicate dal processo di mapping e nel tipo <xref:System.Data.DataSet> vengono creati i seguenti elementi:  
  
- Una tabella per ogni tipo complesso (padre e figlio).  
  
- Se nell'elemento padre non è presente alcun vincolo UNIQUE, una colonna chiave primaria aggiuntiva per ogni definizione di tabella denominata *TableName*_Id dove *TableName* è il nome della tabella padre.  
  
- Un vincolo PRIMARY KEY nella tabella padre che identifica la colonna aggiuntiva come chiave primaria, impostando la proprietà **IsPrimaryKey** su **true**. Il vincolo viene denominato Constraint\#, dove \# rappresenta 1, 2, 3 e così via. Il nome predefinito del primo vincolo, ad esempio, è Constraint1.  
  
- Un vincolo di chiave esterna nella tabella figlio che consenta di identificare la colonna aggiuntiva come chiave esterna contenente riferimenti alla chiave primaria della tabella padre. Il vincolo è denominato *ParentTable_ChildTable* , dove *ParentTable* è il nome della tabella padre e *ChildTable* è il nome della tabella figlio.  
  
- Una relazione di dati tra le tabelle padre e figlio.  
  
 Nell'esempio seguente viene illustrato uno schema in cui **OrderDetail** è un elemento figlio di **Order**.  
  
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
            <xs:element name="OrderNumber" type="xs:string" />  
            <xs:element name="EmpNumber" type="xs:string" />  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:string" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:sequence>  
         </xs:complexType>  
       </xs:element>  
     </xs:choice>  
   </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 Il processo di mapping di XML Schema crea quanto segue nel **set di dati**:  
  
- Un **ordine** e una tabella **OrderDetail** .  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
- Vincolo UNIQUE nella tabella **Order** . Si noti che la proprietà **IsPrimaryKey** è impostata su **true**.  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
- Vincolo FOREIGN KEY nella tabella **OrderDetail** .  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
- Relazione tra le tabelle **Order** e **OrderDetail** . La proprietà **Nested** per questa relazione è impostata su **true** perché gli elementi **Order** e **OrderDetail** sono annidati nello schema.  
  
    ```  
    ParentTable: Order  
    ParentColumns: Order_Id   
    ChildTable: OrderDetail  
    ChildColumns: Order_Id   
    ParentKeyConstraint: Constraint1  
    ChildKeyConstraint: Order_OrderDetail  
    RelationName: Order_OrderDetail  
    Nested: True  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Generazione di relazioni tra DataSet da XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
