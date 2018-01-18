---
title: Mapping tra vincoli keyref XML Schema (XSD) e vincoli di dataset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e364efe0856a5291fc8157ef6ab185c2438a3347
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>Mapping tra vincoli keyref XML Schema (XSD) e vincoli di dataset
Il **keyref** elemento consente di stabilire collegamenti tra elementi all'interno di un documento. Questo elemento ha quindi una funzione simile a quella della relazione di chiave esterna in un database relazionale. Se uno schema viene specificato il **keyref** elemento, l'elemento viene convertito durante il processo di mapping dello schema per un vincolo di chiave esterna corrispondente alle colonne nelle tabelle del <xref:System.Data.DataSet>. Per impostazione predefinita, il **keyref** elemento genera anche una relazione, con la **ParentTable**, **ChildTable**, **ParentColumn**e  **ChildColumn** proprietà specificate per la relazione.  
  
 Nella tabella seguente vengono la **msdata** attributi in cui è possibile specificare il **keyref** elemento.  
  
|Nome attributo|Descrizione|  
|--------------------|-----------------|  
|**msdata:ConstraintOnly**|Se **ConstraintOnly = "true"** viene specificata per il **keyref** elemento nello schema, viene creato un vincolo, ma è stata creata alcuna relazione. Se questo attributo non è specificato (o è impostata su **False**), vengono creati sia il vincolo che la relazione nel **DataSet**.|  
|**msdata:ConstraintName**|Se il **ConstraintName** attributo viene specificato, il relativo valore viene utilizzato come nome del vincolo. In caso contrario, il **nome** attributo del **keyref** elemento nello schema fornisce il nome del vincolo nel **DataSet**.|  
|**msdata:UpdateRule**|Se il **UpdateRule** attributo viene specificato nella **keyref** elemento nello schema, il relativo valore è assegnato al **UpdateRule** proprietà vincolo nel  **Set di dati**. In caso contrario il **UpdateRule** è impostata su **Cascade**.|  
|**msdata:DeleteRule**|Se il **DeleteRule** attributo viene specificato nella **keyref** elemento nello schema, il relativo valore è assegnato al **DeleteRule** proprietà vincolo nel  **Set di dati**. In caso contrario il **DeleteRule** è impostata su **Cascade**.|  
|**msdata:AcceptRejectRule**|Se il **AcceptRejectRule** attributo viene specificato nella **keyref** elemento nello schema, il relativo valore è assegnato al **AcceptRejectRule** proprietà vincolo nel  **Set di dati**. In caso contrario il **AcceptRejectRule** è impostata su **Nessuno**.|  
  
 Nell'esempio seguente contiene uno schema che specifica il **chiave** e **keyref** le relazioni tra il **OrderNumber** elemento figlio dell'elemento di **ordine**  elemento e **OrderNo** elemento figlio dell'elemento di **OrderDetail** elemento.  
  
 Nell'esempio il **OrderNumber** elemento figlio dell'elemento di **OrderDetail** elemento fa riferimento al **OrderNo** elemento chiave figlio dell'elemento il **ordine**elemento.  
  
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
  
 Il processo di mapping dello schema di XML Schema definition language (XSD) produce il seguente **DataSet** con due tabelle:  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 Inoltre, il **DataSet** definisce i vincoli seguenti:  
  
-   Un vincolo unique per la **ordine** tabella.  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
-   Una relazione tra il **ordine** e **OrderDetail** tabelle. Il **Nested** è impostata su **False** perché i due elementi non annidati nello schema.  
  
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
  
-   Un vincolo di chiave esterna nella **OrderDetail** tabella.  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [Generazione di relazioni tra DataSet da XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
