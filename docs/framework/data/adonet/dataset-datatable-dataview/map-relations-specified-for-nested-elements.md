---
title: Mapping di relazioni specificate per elementi annidati
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: e8cdf73b6277abdaab1256ca87e615a5e25e7336
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786094"
---
# <a name="map-relations-specified-for-nested-elements"></a>Mapping di relazioni specificate per elementi annidati
Uno schema può includere un'annotazione **msdata: Relationship** per specificare in modo esplicito il mapping tra due elementi qualsiasi nello schema. I due elementi specificati in **msdata: Relationship** possono essere annidati nello schema, ma non devono essere. Il processo di mapping utilizza **msdata: Relationship** nello schema per generare la relazione di chiave primaria/chiave esterna tra le due colonne.  
  
 Nell'esempio seguente viene illustrato un XML Schema in cui l'elemento **OrderDetail** è un elemento figlio di **Order**. La relazione **msdata:** identifica questa relazione padre-figlio e specifica che la colonna **OrderNumber** della tabella **Order** risultante è correlata alla colonna **OrderNo** della tabella **OrderDetail** risultante.  
  
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
          <xs:annotation>  
           <xs:appinfo>  
            <msdata:Relationship name="OrdODRelation"   
                                msdata:parent="Order"   
                                msdata:child="OrderDetail"   
                                msdata:parentkey="OrderNumber"   
                                msdata:childkey="OrderNo"/>  
           </xs:appinfo>  
          </xs:annotation>  
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
  
 Il processo di mapping di XML Schema consente di creare nell'oggetto <xref:System.Data.DataSet> i seguenti elementi:  
  
- Un **ordine** e una tabella **OrderDetail** .  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- Relazione tra le tabelle **Order** e **OrderDetail** . La proprietà **Nested** per questa relazione è impostata su **true** perché gli elementi **Order** e **OrderDetail** sono annidati nello schema.  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 Il processo di mapping non consente di creare alcun vincolo.  
  
## <a name="see-also"></a>Vedere anche

- [Generazione di relazioni tra DataSet da XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
