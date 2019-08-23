---
title: Derivazione della struttura relazionale di dataset da XML Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: 98c43b6af2913b9737085d2d983b37c6da4c1724
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934471"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="cbf85-102">Derivazione della struttura relazionale di dataset da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="cbf85-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="cbf85-103">Questa sezione fornisce una panoramica della compilazione dello schema relazionale di un tipo `DataSet` da un documento basato sullo schema XSD (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="cbf85-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="cbf85-104">In generale, per ogni `complexType` elemento figlio di un elemento dello schema, viene generata una tabella `DataSet`in.</span><span class="sxs-lookup"><span data-stu-id="cbf85-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="cbf85-105">La struttura della tabella è determinata dalla definizione del tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="cbf85-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="cbf85-106">Le `DataSet` tabelle vengono create in per gli elementi di primo livello nello schema.</span><span class="sxs-lookup"><span data-stu-id="cbf85-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="cbf85-107">Tuttavia, una tabella viene creata solo per un elemento di livello `complexType` principale quando l' `complexType` elemento è annidato all' `complexType` interno di un altro elemento, nel `complexType` qual caso l'elemento `DataSet`annidato viene mappato a un oggetto `DataTable` all'interno di.</span><span class="sxs-lookup"><span data-stu-id="cbf85-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="cbf85-108">Per ulteriori informazioni su XSD, vedere la World Wide Web Consortium (W3C) [XML Schema Part 0: Raccomandazione](https://www.w3.org/TR/xmlschema-0/) principale[, XML Schema Part 1: Indicazioni](https://www.w3.org/TR/xmlschema-1/) sulle[strutture e XML Schema Part 2: Indicazione](https://www.w3.org/TR/xmlschema-2/)DataTypes.</span><span class="sxs-lookup"><span data-stu-id="cbf85-108">For more information about the XSD, see the World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), the [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), and the [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span></span>  
  
 <span data-ttu-id="cbf85-109">Nell'esempio seguente viene illustrato un XML schema `customers` in cui è l'elemento figlio `MyDataSet` dell'elemento, che è un elemento del **set di dati** .</span><span class="sxs-lookup"><span data-stu-id="cbf85-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
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
  
 <span data-ttu-id="cbf85-110">L'elemento `customers` nell'esempio precedente è un elemento di tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="cbf85-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="cbf85-111">La definizione di tipo complesso viene quindi analizzata e la tabella seguente viene creata dal processo di mapping.</span><span class="sxs-lookup"><span data-stu-id="cbf85-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 <span data-ttu-id="cbf85-112">Il tipo di dati relativo a ogni colonna della tabella viene derivato dal tipo di XML Schema relativo al corrispondente elemento o attributo specificato.</span><span class="sxs-lookup"><span data-stu-id="cbf85-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cbf85-113">Se l'elemento `customers` è di un tipo di dati XML Schema semplice, ad esempio **Integer**, non viene generata alcuna tabella.</span><span class="sxs-lookup"><span data-stu-id="cbf85-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="cbf85-114">Le tabelle vengono create solo per gli elementi di livello principale di tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="cbf85-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="cbf85-115">Nel seguente schema XML, l'elemento **schema** ha due elementi figlio, `InStateCustomers` e. `OutOfStateCustomers`</span><span class="sxs-lookup"><span data-stu-id="cbf85-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
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
  
 <span data-ttu-id="cbf85-116">Entrambi gli elementi figlio `InStateCustomers` e `OutOfStateCustomers` sono elementi di tipo complesso (`customerType`).</span><span class="sxs-lookup"><span data-stu-id="cbf85-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="cbf85-117">Pertanto, il processo di mapping genera le due tabelle identiche seguenti `DataSet`in.</span><span class="sxs-lookup"><span data-stu-id="cbf85-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="cbf85-118">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="cbf85-118">In This Section</span></span>  
 [<span data-ttu-id="cbf85-119">Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet</span><span class="sxs-lookup"><span data-stu-id="cbf85-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="cbf85-120">Vengono descritti gli elementi di XML Schema usati per creare vincoli UNIQUE ed Foreign Key `DataSet`in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="cbf85-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="cbf85-121">Generazione di relazioni tra DataSet da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="cbf85-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="cbf85-122">Vengono descritti gli elementi di XML Schema utilizzati per creare relazioni tra le colonne `DataSet`della tabella in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="cbf85-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="cbf85-123">Vincoli e relazioni di XML Schema</span><span class="sxs-lookup"><span data-stu-id="cbf85-123">XML Schema Constraints and Relationships</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="cbf85-124">Viene descritto come vengono create le relazioni in modo implicito quando si utilizzano gli elementi dello `DataSet`schema XML per creare vincoli in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="cbf85-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cbf85-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="cbf85-125">Related Sections</span></span>  
 [<span data-ttu-id="cbf85-126">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="cbf85-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="cbf85-127">Viene descritto come caricare e salvare in modo permanente la struttura relazionale e `DataSet` i dati in un oggetto come dati XML.</span><span class="sxs-lookup"><span data-stu-id="cbf85-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbf85-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbf85-128">See also</span></span>

- [<span data-ttu-id="cbf85-129">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="cbf85-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
