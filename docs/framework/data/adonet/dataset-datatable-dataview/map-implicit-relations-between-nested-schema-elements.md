---
title: Mapping di relazioni implicite tra elementi di schemi annidati
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: dc5b81fd06f2860283c8c5fa028af4b945e2b1e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150963"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a>Mapping di relazioni implicite tra elementi di schemi annidati
È possibile che in uno schema XSD (XML Schema Definition Language) siano presenti tipi complessi annidati uno all'interno dell'altro. In questo caso, le impostazioni di mapping predefinite vengono applicate dal processo di mapping e nel tipo <xref:System.Data.DataSet> vengono creati i seguenti elementi:  
  
- Una tabella per ogni tipo complesso (padre e figlio).  
  
- Se nell'elemento padre non esiste alcun vincolo univoco, una colonna di chiave primaria aggiuntiva per ogni definizione di tabella denominata *NomeTabella*_Id dove *NomeTabella* è il nome della tabella padre.  
  
- Un vincolo di chiave primaria nella tabella padre che identifica la colonna aggiuntiva come chiave primaria (impostando la proprietà **IsPrimaryKey** su **True**). Il vincolo viene denominato Constraint\#, dove \# rappresenta 1, 2, 3 e così via. Il nome predefinito del primo vincolo, ad esempio, è Constraint1.  
  
- Un vincolo di chiave esterna nella tabella figlio che consenta di identificare la colonna aggiuntiva come chiave esterna contenente riferimenti alla chiave primaria della tabella padre. Il vincolo è denominato *ParentTable_ChildTable* dove *ParentTable* è il nome della tabella padre e *ChildTable* è il nome della tabella figlio.  
  
- Una relazione di dati tra le tabelle padre e figlio.  
  
 Nell'esempio seguente viene illustrato uno schema in cui **OrderDetail** è un elemento figlio **Order**.  
  
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
  
 Il processo di mapping dello schema XML crea quanto segue nel **DataSet**:  
  
- Una tabella **Order** e **OrderDetail.**  
  
    ```text  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
- Un vincolo univoco nella tabella **Order.** Si noti che la proprietà **IsPrimaryKey** è impostata su **True**.  
  
    ```text  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id
    IsPrimaryKey: True  
    ```  
  
- Un vincolo di chiave esterna nella tabella **OrderDetail.**  
  
    ```text  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id
    RelatedTable: Order  
    RelatedColumns: Order_Id
    ```  
  
- Relazione tra le tabelle **Order** e **OrderDetail.** Il **Nested** proprietà per questa relazione è impostata su **True** perché il **Order** e **OrderDetail** elementi sono annidati nello schema.  
  
    ```text  
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

- [Generazione di relazioni tra dataset da XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Mapping tra vincoli XML Schema (XSD) e vincoli di dataset](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
