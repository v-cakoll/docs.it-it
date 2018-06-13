---
title: Mapping di relazioni specificate per elementi annidati
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: e1fde0ef585621a6821838613a7e77dedf7042b1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756696"
---
# <a name="map-relations-specified-for-nested-elements"></a><span data-ttu-id="0d902-102">Mapping di relazioni specificate per elementi annidati</span><span class="sxs-lookup"><span data-stu-id="0d902-102">Map Relations Specified for Nested Elements</span></span>
<span data-ttu-id="0d902-103">Uno schema può includere un **msdata: Relationship** annotazione per specificare in modo esplicito il mapping tra qualsiasi due elementi nello schema.</span><span class="sxs-lookup"><span data-stu-id="0d902-103">A schema can include an **msdata:Relationship** annotation to explicitly specify the mapping between any two elements in the schema.</span></span> <span data-ttu-id="0d902-104">I due elementi specificati **msdata: Relationship** possono essere annidati nello schema, ma non è necessario essere.</span><span class="sxs-lookup"><span data-stu-id="0d902-104">The two elements specified in **msdata:Relationship** can be nested in the schema, but do not have to be.</span></span> <span data-ttu-id="0d902-105">Il processo di mapping utilizza **msdata: Relationship** nello schema per generare la relazione chiave primaria/esterna chiave tra le due colonne.</span><span class="sxs-lookup"><span data-stu-id="0d902-105">The mapping process uses **msdata:Relationship** in the schema to generate the primary key/foreign key relationship between the two columns.</span></span>  
  
 <span data-ttu-id="0d902-106">Nell'esempio seguente viene illustrato un XML Schema in cui il **OrderDetail** elemento è un elemento figlio di **ordine**.</span><span class="sxs-lookup"><span data-stu-id="0d902-106">The following example shows an XML Schema in which the **OrderDetail** element is a child element of **Order**.</span></span> <span data-ttu-id="0d902-107">Il **msdata: Relationship** identifica la relazione padre-figlio e specifica che il **OrderNumber** colonna dell'oggetto risultante **ordine** tabella è correlata al **OrderNo** colonna dell'oggetto risultante **OrderDetail** tabella.</span><span class="sxs-lookup"><span data-stu-id="0d902-107">The **msdata:Relationship** identifies this parent-child relationship and specifies that the **OrderNumber** column of the resulting **Order** table is related to the **OrderNo** column of the resulting **OrderDetail** table.</span></span>  
  
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
  
 <span data-ttu-id="0d902-108">Il processo di mapping di XML Schema consente di creare nell'oggetto <xref:System.Data.DataSet> i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="0d902-108">The XML Schema mapping process creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
-   <span data-ttu-id="0d902-109">Un **ordine** e **OrderDetail** tabella.</span><span class="sxs-lookup"><span data-stu-id="0d902-109">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
-   <span data-ttu-id="0d902-110">Una relazione tra il **ordine** e **OrderDetail** tabelle.</span><span class="sxs-lookup"><span data-stu-id="0d902-110">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="0d902-111">Il **Nested** per questa relazione è impostata su **True** perché il **ordine** e **OrderDetail** elementi sono annidati nello schema .</span><span class="sxs-lookup"><span data-stu-id="0d902-111">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 <span data-ttu-id="0d902-112">Il processo di mapping non consente di creare alcun vincolo.</span><span class="sxs-lookup"><span data-stu-id="0d902-112">The mapping process does not create any constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d902-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d902-113">See Also</span></span>  
 [<span data-ttu-id="0d902-114">Generazione di relazioni tra DataSet da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="0d902-114">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="0d902-115">Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet</span><span class="sxs-lookup"><span data-stu-id="0d902-115">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="0d902-116">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="0d902-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
