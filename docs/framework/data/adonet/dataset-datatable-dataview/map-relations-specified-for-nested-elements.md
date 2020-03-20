---
title: Mapping di relazioni specificate per elementi annidati
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: cd652f51f01dcfa16a8b707f35c658043c20670d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150896"
---
# <a name="map-relations-specified-for-nested-elements"></a><span data-ttu-id="a750e-102">Mapping di relazioni specificate per elementi annidati</span><span class="sxs-lookup"><span data-stu-id="a750e-102">Map Relations Specified for Nested Elements</span></span>
<span data-ttu-id="a750e-103">Uno schema può includere un'annotazione **msdata:Relationship** per specificare in modo esplicito il mapping tra due elementi qualsiasi nello schema.</span><span class="sxs-lookup"><span data-stu-id="a750e-103">A schema can include an **msdata:Relationship** annotation to explicitly specify the mapping between any two elements in the schema.</span></span> <span data-ttu-id="a750e-104">I due elementi specificati in **msdata:Relationship** possono essere annidati nello schema, ma non è necessario.</span><span class="sxs-lookup"><span data-stu-id="a750e-104">The two elements specified in **msdata:Relationship** can be nested in the schema, but do not have to be.</span></span> <span data-ttu-id="a750e-105">Il processo di mapping utilizza **msdata:Relationship** nello schema per generare la relazione chiave primaria/chiave esterna tra le due colonne.</span><span class="sxs-lookup"><span data-stu-id="a750e-105">The mapping process uses **msdata:Relationship** in the schema to generate the primary key/foreign key relationship between the two columns.</span></span>  
  
 <span data-ttu-id="a750e-106">Nell'esempio seguente viene illustrato uno schema XML in cui l'elemento **OrderDetail** è un elemento figlio **Order**.</span><span class="sxs-lookup"><span data-stu-id="a750e-106">The following example shows an XML Schema in which the **OrderDetail** element is a child element of **Order**.</span></span> <span data-ttu-id="a750e-107">**Msdata:Relationship** identifica questa relazione padre-figlio e specifica che la colonna **OrderNumber** della tabella **Order** risultante è correlata alla colonna **OrderNo** della tabella **OrderDetail** risultante.</span><span class="sxs-lookup"><span data-stu-id="a750e-107">The **msdata:Relationship** identifies this parent-child relationship and specifies that the **OrderNumber** column of the resulting **Order** table is related to the **OrderNo** column of the resulting **OrderDetail** table.</span></span>  
  
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
  
 <span data-ttu-id="a750e-108">Il processo di mapping di XML Schema consente di creare nell'oggetto <xref:System.Data.DataSet> i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="a750e-108">The XML Schema mapping process creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="a750e-109">Una tabella **Order** e **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="a750e-109">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```text  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- <span data-ttu-id="a750e-110">Relazione tra le tabelle **Order** e **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="a750e-110">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="a750e-111">Il **Nested** proprietà per questa relazione è impostata su **True** perché il **Order** e **OrderDetail** elementi sono annidati nello schema.</span><span class="sxs-lookup"><span data-stu-id="a750e-111">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```text  
    ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 <span data-ttu-id="a750e-112">Il processo di mapping non consente di creare alcun vincolo.</span><span class="sxs-lookup"><span data-stu-id="a750e-112">The mapping process does not create any constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a750e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a750e-113">See also</span></span>

- [<span data-ttu-id="a750e-114">Generazione di relazioni tra dataset da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="a750e-114">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="a750e-115">Mapping tra vincoli XML Schema (XSD) e vincoli di dataset</span><span class="sxs-lookup"><span data-stu-id="a750e-115">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="a750e-116">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a750e-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
