---
title: Derivazione della struttura relazionale di dataset da XML Schema (XSD)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: eb4f6e3a63c901ec69ca5572a6f79d2f0ac4adfc
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="c0301-102">Derivazione della struttura relazionale di dataset da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="c0301-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="c0301-103">Questa sezione fornisce una panoramica della compilazione dello schema relazionale di un tipo `DataSet` da un documento basato sullo schema XSD (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="c0301-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="c0301-104">In generale, per ogni `complexType` elemento figlio di un elemento dello schema, in cui viene generata una tabella di `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="c0301-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="c0301-105">La struttura della tabella è determinata dalla definizione del tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="c0301-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="c0301-106">Le tabelle vengono create nel `DataSet` per gli elementi di primo livello nello schema.</span><span class="sxs-lookup"><span data-stu-id="c0301-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="c0301-107">Tuttavia, una tabella viene creata solo per un livello superiore `complexType` elemento quando il `complexType` è annidato l'elemento all'interno di un altro `complexType` elemento, in cui caso nidificata `complexType` elemento viene mappato a un `DataTable` all'interno del `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="c0301-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="c0301-108">Per ulteriori informazioni su XSD, vedere il World Wide Web Consortium (W3C) XML Schema Part 0: Primer raccomandazione, XML Schema Part 1: Structures Recommendation e XML Schema Part 2: Datatypes Recommendation, disponibile all'indirizzo [http:// www.w3.org/](http://www.w3.org/TR/).</span><span class="sxs-lookup"><span data-stu-id="c0301-108">For more information about the XSD, see the World Wide Web Consortium (W3C) XML Schema Part 0: Primer Recommendation, the XML Schema Part 1: Structures Recommendation, and the XML Schema Part 2: Datatypes Recommendation, located at [http://www.w3.org/](http://www.w3.org/TR/).</span></span>  
  
 <span data-ttu-id="c0301-109">Nell'esempio seguente viene illustrato un XML Schema in cui `customers` è l'elemento figlio del `MyDataSet` elemento, ovvero un **DataSet** elemento.</span><span class="sxs-lookup"><span data-stu-id="c0301-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >   
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"   
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"   
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="c0301-110">L'elemento `customers` nell'esempio precedente è un elemento di tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="c0301-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="c0301-111">La definizione di tipo complesso viene quindi analizzata e la tabella seguente viene creata dal processo di mapping.</span><span class="sxs-lookup"><span data-stu-id="c0301-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 <span data-ttu-id="c0301-112">Il tipo di dati relativo a ogni colonna della tabella viene derivato dal tipo di XML Schema relativo al corrispondente elemento o attributo specificato.</span><span class="sxs-lookup"><span data-stu-id="c0301-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0301-113">Se l'elemento `customers` è di un tipo di dati XML Schema semplice, ad esempio **intero**, verrà generata alcuna tabella.</span><span class="sxs-lookup"><span data-stu-id="c0301-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="c0301-114">Le tabelle vengono create solo per gli elementi di livello principale di tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="c0301-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="c0301-115">Nello Schema XML seguente, il **Schema** elemento dispone di due elementi figlio, `InStateCustomers` e `OutOfStateCustomers`.</span><span class="sxs-lookup"><span data-stu-id="c0301-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="c0301-116">Entrambi gli elementi figlio `InStateCustomers` e `OutOfStateCustomers` sono elementi di tipo complesso (`customerType`).</span><span class="sxs-lookup"><span data-stu-id="c0301-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="c0301-117">Pertanto, il processo di mapping genera le due tabelle identiche seguenti nel `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="c0301-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="c0301-118">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="c0301-118">In This Section</span></span>  
 [<span data-ttu-id="c0301-119">Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet</span><span class="sxs-lookup"><span data-stu-id="c0301-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="c0301-120">Vengono descritti gli elementi di XML Schema utilizzati per creare vincoli di chiave esterni e univoci in un `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="c0301-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="c0301-121">Generazione di relazioni tra DataSet da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="c0301-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="c0301-122">Vengono descritti gli elementi di XML Schema utilizzati per creare relazioni tra le colonne della tabella in un `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="c0301-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="c0301-123">Vincoli e relazioni di XML Schema</span><span class="sxs-lookup"><span data-stu-id="c0301-123">XML Schema Constraints and Relationships</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="c0301-124">Viene descritto come le relazioni vengono create in modo implicito quando si usano elementi di XML Schema per creare vincoli in un `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="c0301-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c0301-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c0301-125">Related Sections</span></span>  
 [<span data-ttu-id="c0301-126">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="c0301-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="c0301-127">Viene descritto come caricare e mantenere la struttura relazionale e i dati in un `DataSet` come dati XML.</span><span class="sxs-lookup"><span data-stu-id="c0301-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0301-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0301-128">See Also</span></span>  
 [<span data-ttu-id="c0301-129">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="c0301-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
