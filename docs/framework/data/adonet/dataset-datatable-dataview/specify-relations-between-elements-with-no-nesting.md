---
title: Specifica di relazioni tra elementi senza alcun annidamento
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: bee427c6cdf76792773ea827c8772b276ff29c31
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150818"
---
# <a name="specify-relations-between-elements-with-no-nesting"></a><span data-ttu-id="41215-102">Specifica di relazioni tra elementi senza alcun annidamento</span><span class="sxs-lookup"><span data-stu-id="41215-102">Specify Relations Between Elements with No Nesting</span></span>
<span data-ttu-id="41215-103">Se gli elementi non sono annidati, non viene creata alcuna relazione implicita.</span><span class="sxs-lookup"><span data-stu-id="41215-103">When elements are not nested, no implicit relations are created.</span></span> <span data-ttu-id="41215-104">È tuttavia possibile specificare in modo esplicito le relazioni tra elementi che non sono annidati utilizzando l'annotazione **msdata:Relationship.You can, however,** explicitly specify relations between elements that are not nested by using the msdata:Relationship annotation.</span><span class="sxs-lookup"><span data-stu-id="41215-104">You can, however, explicitly specify relations between elements that are not nested by using the **msdata:Relationship** annotation.</span></span>  
  
 <span data-ttu-id="41215-105">Nell'esempio seguente viene illustrato uno schema XML in cui l'annotazione **msdata:Relationship** viene specificata tra gli elementi **Order** e **OrderDetail,** che non sono annidati.</span><span class="sxs-lookup"><span data-stu-id="41215-105">The following example shows an XML Schema in which the **msdata:Relationship** annotation is specified between the **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="41215-106">L'annotazione **msdata:Relationship** viene specificata come elemento figlio dell'elemento **Schema.**</span><span class="sxs-lookup"><span data-stu-id="41215-106">The **msdata:Relationship** annotation is specified as the child element of the **Schema** element.</span></span>  
  
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
  
 <span data-ttu-id="41215-107">Il processo di mapping dello schema XSD <xref:System.Data.DataSet> (XML Schema Definition Language) crea un oggetto con le tabelle **Order** e **OrderDetail** e una relazione specificata tra queste due tabelle, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="41215-107">The XML Schema definition language (XSD) schema mapping process creates a <xref:System.Data.DataSet> with **Order** and **OrderDetail** tables and a relationship specified between these two tables, as shown below.</span></span>  
  
```text  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber
ChildTable: OrderDetail  
ChildColumns: OrderNo
Nested: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="41215-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41215-108">See also</span></span>

- [<span data-ttu-id="41215-109">Generazione di relazioni tra dataset da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="41215-109">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="41215-110">Mapping tra vincoli XML Schema (XSD) e vincoli di dataset</span><span class="sxs-lookup"><span data-stu-id="41215-110">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="41215-111">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="41215-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
