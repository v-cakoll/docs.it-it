---
title: Derivazione della struttura relazionale di dataset da XML Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: d32b5cb86bc5a138f9a5f438629d8e231be4ba94
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151169"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="88c3b-102">Derivazione della struttura relazionale di dataset da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="88c3b-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="88c3b-103">Questa sezione fornisce una panoramica della compilazione dello schema relazionale di un tipo `DataSet` da un documento basato sullo schema XSD (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="88c3b-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="88c3b-104">In generale, `complexType` per ogni elemento figlio di un elemento `DataSet`dello schema, viene generata una tabella nell'oggetto .</span><span class="sxs-lookup"><span data-stu-id="88c3b-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="88c3b-105">La struttura della tabella è determinata dalla definizione del tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="88c3b-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="88c3b-106">Le tabelle vengono `DataSet` create negli elementi di primo livello per lo schema.</span><span class="sxs-lookup"><span data-stu-id="88c3b-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="88c3b-107">Tuttavia, una tabella viene creata `complexType` solo per `complexType` un elemento `complexType` di primo livello quando `complexType` l'elemento è `DataTable` annidato all'interno di un altro elemento, nel qual caso l'elemento nidificato viene mappato a un all'interno di `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="88c3b-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="88c3b-108">Per ulteriori informazioni su XSD, vedere la parte 0 della sezione Schema XML del World Wide Web Consortium (W3C) [, Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/)e XML Schema Part [2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span><span class="sxs-lookup"><span data-stu-id="88c3b-108">For more information about the XSD, see the World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), the [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), and the [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span></span>  
  
 <span data-ttu-id="88c3b-109">Nell'esempio seguente viene `customers` illustrato uno schema `MyDataSet` XML in cui è l'elemento figlio dell'elemento, che è un **DataSet** elemento.</span><span class="sxs-lookup"><span data-stu-id="88c3b-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
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
  
 <span data-ttu-id="88c3b-110">L'elemento `customers` nell'esempio precedente è un elemento di tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="88c3b-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="88c3b-111">La definizione di tipo complesso viene quindi analizzata e la tabella seguente viene creata dal processo di mapping.</span><span class="sxs-lookup"><span data-stu-id="88c3b-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="88c3b-112">Il tipo di dati relativo a ogni colonna della tabella viene derivato dal tipo di XML Schema relativo al corrispondente elemento o attributo specificato.</span><span class="sxs-lookup"><span data-stu-id="88c3b-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="88c3b-113">Se l'elemento `customers` è di un tipo di dati Schema XML semplice, ad esempio **integer**, non viene generata alcuna tabella.</span><span class="sxs-lookup"><span data-stu-id="88c3b-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="88c3b-114">Le tabelle vengono create solo per gli elementi di livello principale di tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="88c3b-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="88c3b-115">Nello schema XML seguente l'elemento **Schema** `InStateCustomers` ha `OutOfStateCustomers`due elementi figlio e .</span><span class="sxs-lookup"><span data-stu-id="88c3b-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
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
  
 <span data-ttu-id="88c3b-116">Entrambi gli elementi figlio `InStateCustomers` e `OutOfStateCustomers` sono elementi di tipo complesso (`customerType`).</span><span class="sxs-lookup"><span data-stu-id="88c3b-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="88c3b-117">Di conseguenza, il processo di mapping `DataSet`genera le due tabelle identiche seguenti nel file .</span><span class="sxs-lookup"><span data-stu-id="88c3b-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="88c3b-118">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="88c3b-118">In This Section</span></span>  
 [<span data-ttu-id="88c3b-119">Mapping tra vincoli XML Schema (XSD) e vincoli di dataset</span><span class="sxs-lookup"><span data-stu-id="88c3b-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="88c3b-120">Vengono descritti gli elementi dello schema XML utilizzati `DataSet`per creare vincoli di chiave univoca ed esterna in un oggetto .</span><span class="sxs-lookup"><span data-stu-id="88c3b-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="88c3b-121">Generazione di relazioni tra dataset da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="88c3b-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="88c3b-122">Vengono descritti gli elementi dello schema XML utilizzati per creare relazioni tra le colonne della tabella in un `DataSet`oggetto .</span><span class="sxs-lookup"><span data-stu-id="88c3b-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="88c3b-123">Vincoli e relazioni di XML Schema</span><span class="sxs-lookup"><span data-stu-id="88c3b-123">XML Schema Constraints and Relationships</span></span>](xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="88c3b-124">Viene descritto come le relazioni vengono create in modo `DataSet`implicito quando si utilizzano gli elementi xml Schema per creare vincoli in un oggetto .</span><span class="sxs-lookup"><span data-stu-id="88c3b-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="88c3b-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="88c3b-125">Related Sections</span></span>  
 [<span data-ttu-id="88c3b-126">Utilizzo di XML in un dataset</span><span class="sxs-lookup"><span data-stu-id="88c3b-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="88c3b-127">Viene descritto come caricare e rendere persistente `DataSet` la struttura relazionale e i dati in un database XML.</span><span class="sxs-lookup"><span data-stu-id="88c3b-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88c3b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88c3b-128">See also</span></span>

- [<span data-ttu-id="88c3b-129">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="88c3b-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
