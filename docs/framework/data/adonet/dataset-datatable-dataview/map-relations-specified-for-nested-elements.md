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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9866b556f2ba09cef7616fea4a2a6d8135e6b8e8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="map-relations-specified-for-nested-elements"></a><span data-ttu-id="9c1e2-102">Mapping di relazioni specificate per elementi annidati</span><span class="sxs-lookup"><span data-stu-id="9c1e2-102">Map Relations Specified for Nested Elements</span></span>
<span data-ttu-id="9c1e2-103">Uno schema può includere un **msdata: Relationship** annotazione per specificare in modo esplicito il mapping tra qualsiasi due elementi nello schema.</span><span class="sxs-lookup"><span data-stu-id="9c1e2-103">A schema can include an **msdata:Relationship** annotation to explicitly specify the mapping between any two elements in the schema.</span></span> <span data-ttu-id="9c1e2-104">I due elementi specificati **msdata: Relationship** possono essere annidati nello schema, ma non è necessario essere.</span><span class="sxs-lookup"><span data-stu-id="9c1e2-104">The two elements specified in **msdata:Relationship** can be nested in the schema, but do not have to be.</span></span> <span data-ttu-id="9c1e2-105">Il processo di mapping utilizza **msdata: Relationship** nello schema per generare la relazione chiave primaria/esterna chiave tra le due colonne.</span><span class="sxs-lookup"><span data-stu-id="9c1e2-105">The mapping process uses **msdata:Relationship** in the schema to generate the primary key/foreign key relationship between the two columns.</span></span>  
  
 <span data-ttu-id="9c1e2-106">Nell'esempio seguente viene illustrato un XML Schema in cui il **OrderDetail** elemento è un elemento figlio di **ordine**.</span><span class="sxs-lookup"><span data-stu-id="9c1e2-106">The following example shows an XML Schema in which the **OrderDetail** element is a child element of **Order**.</span></span> <span data-ttu-id="9c1e2-107">Il **msdata: Relationship** identifica la relazione padre-figlio e specifica che il **OrderNumber** colonna dell'oggetto risultante **ordine** tabella è correlata al **OrderNo** colonna dell'oggetto risultante **OrderDetail** tabella.</span><span class="sxs-lookup"><span data-stu-id="9c1e2-107">The **msdata:Relationship** identifies this parent-child relationship and specifies that the **OrderNumber** column of the resulting **Order** table is related to the **OrderNo** column of the resulting **OrderDetail** table.</span></span>  
  
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
  
 <span data-ttu-id="9c1e2-108">Il processo di mapping di XML Schema consente di creare nell'oggetto <xref:System.Data.DataSet> i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="9c1e2-108">The XML Schema mapping process creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
-   <span data-ttu-id="9c1e2-109">Un **ordine** e **OrderDetail** tabella.</span><span class="sxs-lookup"><span data-stu-id="9c1e2-109">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
-   <span data-ttu-id="9c1e2-110">Una relazione tra il **ordine** e **OrderDetail** tabelle.</span><span class="sxs-lookup"><span data-stu-id="9c1e2-110">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="9c1e2-111">Il **Nested** per questa relazione è impostata su **True** perché il **ordine** e **OrderDetail** elementi sono annidati nello schema .</span><span class="sxs-lookup"><span data-stu-id="9c1e2-111">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 <span data-ttu-id="9c1e2-112">Il processo di mapping non consente di creare alcun vincolo.</span><span class="sxs-lookup"><span data-stu-id="9c1e2-112">The mapping process does not create any constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c1e2-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c1e2-113">See Also</span></span>  
 [<span data-ttu-id="9c1e2-114">La generazione di relazioni tra DataSet da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="9c1e2-114">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="9c1e2-115">Vincoli di mapping XML Schema (XSD) e vincoli di DataSet</span><span class="sxs-lookup"><span data-stu-id="9c1e2-115">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="9c1e2-116">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="9c1e2-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
