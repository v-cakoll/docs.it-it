---
title: Mapping di relazioni specificate per elementi annidati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c23e951ee2fd6f5956ab41d4425c9e8af8f12b95
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="map-relations-specified-for-nested-elements"></a>Mapping di relazioni specificate per elementi annidati
Uno schema può includere un **msdata: Relationship** annotazione per specificare in modo esplicito il mapping tra qualsiasi due elementi nello schema. I due elementi specificati **msdata: Relationship** possono essere annidati nello schema, ma non è necessario essere. Il processo di mapping utilizza **msdata: Relationship** nello schema per generare la relazione chiave primaria/esterna chiave tra le due colonne.  
  
 Nell'esempio seguente viene illustrato un XML Schema in cui il **OrderDetail** elemento è un elemento figlio di **ordine**. Il **msdata: Relationship** identifica la relazione padre-figlio e specifica che il **OrderNumber** colonna dell'oggetto risultante **ordine** tabella è correlata al **OrderNo** colonna dell'oggetto risultante **OrderDetail** tabella.  
  
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
  
-   Un **ordine** e **OrderDetail** tabella.  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
-   Una relazione tra il **ordine** e **OrderDetail** tabelle. Il **Nested** per questa relazione è impostata su **True** perché il **ordine** e **OrderDetail** elementi sono annidati nello schema .  
  
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
 [Generazione di relazioni tra DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
