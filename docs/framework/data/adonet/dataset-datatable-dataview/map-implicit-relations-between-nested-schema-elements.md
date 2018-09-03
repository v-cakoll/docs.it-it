---
title: Mapping di relazioni implicite tra elementi di schemi annidati
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: 3c0b5356479d31a3caad8438618e7cf7dc4e10e8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485573"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a>Mapping di relazioni implicite tra elementi di schemi annidati
È possibile che in uno schema XSD (XML Schema Definition Language) siano presenti tipi complessi annidati uno all'interno dell'altro. In questo caso, le impostazioni di mapping predefinite vengono applicate dal processo di mapping e nel tipo <xref:System.Data.DataSet> vengono creati i seguenti elementi:  
  
-   Una tabella per ogni tipo complesso (padre e figlio).  
  
-   Se è presente alcun vincolo univoco dell'elemento padre, una primaria chiave colonna aggiuntiva per ogni definizione di tabella denominata *NomeTabella*ID dove *NomeTabella* è il nome della tabella padre.  
  
-   Un vincolo di chiave primaria nella tabella padre che identifica la colonna aggiuntiva come chiave primaria (impostando il **IsPrimaryKey** proprietà **True**). Il vincolo viene denominato Constraint*#* in cui *#* è 1, 2, 3 e così via. Il nome predefinito del primo vincolo, ad esempio, è Constraint1.  
  
-   Un vincolo di chiave esterna nella tabella figlio che consenta di identificare la colonna aggiuntiva come chiave esterna contenente riferimenti alla chiave primaria della tabella padre. Il vincolo viene denominato *ParentTable_ChildTable* in cui *ParentTable* è il nome della tabella padre e *ChildTable* è il nome della tabella figlio.  
  
-   Una relazione di dati tra le tabelle padre e figlio.  
  
 L'esempio seguente mostra uno schema in cui **OrderDetail** è un elemento figlio del **ordine**.  
  
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
  
 Il processo di mapping di XML Schema consente di creare il codice seguente nel **set di dati**:  
  
-   Un' **ordine** e un **OrderDetail** tabella.  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
-   Un vincolo unique per la **ordine** tabella. Si noti che il **IsPrimaryKey** è impostata su **True**.  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
-   Un vincolo di chiave esterna nella **OrderDetail** tabella.  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
-   Una relazione tra il **ordine** e **OrderDetail** tabelle. Il **Nested** per questa relazione è impostata su **True** perché i **Order** e **OrderDetail** elementi sono annidati nello schema .  
  
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
 [Generazione di relazioni tra DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
