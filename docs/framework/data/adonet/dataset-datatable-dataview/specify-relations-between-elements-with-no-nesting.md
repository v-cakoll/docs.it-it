---
title: Specifica di relazioni tra elementi senza alcun annidamento
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: d04a3d946b87c7203497313c6e21a75ef69f50eb
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45526558"
---
# <a name="specify-relations-between-elements-with-no-nesting"></a><span data-ttu-id="a6f06-102">Specifica di relazioni tra elementi senza alcun annidamento</span><span class="sxs-lookup"><span data-stu-id="a6f06-102">Specify Relations Between Elements with No Nesting</span></span>
<span data-ttu-id="a6f06-103">Se gli elementi non sono annidati, non viene creata alcuna relazione implicita.</span><span class="sxs-lookup"><span data-stu-id="a6f06-103">When elements are not nested, no implicit relations are created.</span></span> <span data-ttu-id="a6f06-104">Tuttavia, è possibile specificare esplicitamente relazioni tra gli elementi non annidati mediante il **msdata: Relationship** annotazione.</span><span class="sxs-lookup"><span data-stu-id="a6f06-104">You can, however, explicitly specify relations between elements that are not nested by using the **msdata:Relationship** annotation.</span></span>  
  
 <span data-ttu-id="a6f06-105">Nell'esempio seguente viene illustrato un XML Schema in cui il **msdata: Relationship** annotazione viene specificata tra la **ordine** e **OrderDetail** elementi, che non sono annidati.</span><span class="sxs-lookup"><span data-stu-id="a6f06-105">The following example shows an XML Schema in which the **msdata:Relationship** annotation is specified between the **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="a6f06-106">Il **msdata: Relationship** annotazione viene specificata come elemento figlio delle **Schema** elemento.</span><span class="sxs-lookup"><span data-stu-id="a6f06-106">The **msdata:Relationship** annotation is specified as the child element of the **Schema** element.</span></span>  
  
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
           <xs:element name="OrderNo" type="xs:string" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNumber" type="xs:string" />  
           <xs:element name="EmpNumber" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  </xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrderDetailRelation"  
                            msdata:parent="Order"   
                            msdata:child="OrderDetail"   
                            msdata:parentkey="OrderNumber"   
                            msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
</xs:schema>  
```  
  
 <span data-ttu-id="a6f06-107">Il processo di mapping dello schema di XML Schema definition language (XSD) crea un <xref:System.Data.DataSet> con **ordine** e **OrderDetail** tabelle e una relazione specificata tra queste due tabelle, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a6f06-107">The XML Schema definition language (XSD) schema mapping process creates a <xref:System.Data.DataSet> with **Order** and **OrderDetail** tables and a relationship specified between these two tables, as shown below.</span></span>  
  
```  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber   
ChildTable: OrderDetail  
ChildColumns: OrderNo   
Nested: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="a6f06-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6f06-108">See Also</span></span>  
 [<span data-ttu-id="a6f06-109">Generazione di relazioni tra DataSet da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="a6f06-109">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="a6f06-110">Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet</span><span class="sxs-lookup"><span data-stu-id="a6f06-110">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="a6f06-111">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="a6f06-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
