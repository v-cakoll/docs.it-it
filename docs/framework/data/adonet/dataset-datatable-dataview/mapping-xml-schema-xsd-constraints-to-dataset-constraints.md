---
title: Mapping tra vincoli XML Schema (XSD) e vincoli di dataset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f403dc974e4fe67d239688f587061cd23a8deff6
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="23da2-102">Mapping tra vincoli XML Schema (XSD) e vincoli di dataset</span><span class="sxs-lookup"><span data-stu-id="23da2-102">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="23da2-103">Lo schema XSD (XML Schema Definition Language) consente di specificare vincoli sugli elementi e sugli attributi in esso definiti.</span><span class="sxs-lookup"><span data-stu-id="23da2-103">The XML Schema definition language (XSD) allows constraints to be specified on the elements and attributes it defines.</span></span> <span data-ttu-id="23da2-104">Durante il mapping di uno Schema XML a uno schema relazionale in un <xref:System.Data.DataSet>, vincoli di XML Schema vengono mappati ai vincoli relazionali appropriati nelle tabelle e colonne all'interno di **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="23da2-104">When mapping an XML Schema to relational schema in a <xref:System.Data.DataSet>, XML Schema constraints are mapped to appropriate relational constraints on the tables and columns within the **DataSet**.</span></span>  
  
 <span data-ttu-id="23da2-105">Contenuto della sezione viene illustrato il mapping dei seguenti vincoli di XML Schema:</span><span class="sxs-lookup"><span data-stu-id="23da2-105">This section discusses the mapping of the following XML Schema constraints:</span></span>  
  
-   <span data-ttu-id="23da2-106">Il vincolo di univocità specificato mediante il **univoco** elemento.</span><span class="sxs-lookup"><span data-stu-id="23da2-106">The uniqueness constraint specified using the **unique** element.</span></span>  
  
-   <span data-ttu-id="23da2-107">Il vincolo di chiave specificato utilizzando il **chiave** elemento.</span><span class="sxs-lookup"><span data-stu-id="23da2-107">The key constraint specified using the **key** element.</span></span>  
  
-   <span data-ttu-id="23da2-108">Il vincolo keyref specificato mediante il **keyref** elemento.</span><span class="sxs-lookup"><span data-stu-id="23da2-108">The keyref constraint specified using the **keyref** element.</span></span>  
  
 <span data-ttu-id="23da2-109">Usando un vincolo su un elemento o su un attributo, si specificano determinate restrizioni relative ai valori dell'elemento in qualsiasi istanza del documento.</span><span class="sxs-lookup"><span data-stu-id="23da2-109">By using a constraint on an element or attribute, you specify certain restrictions on the values of the element in any instance of the document.</span></span> <span data-ttu-id="23da2-110">Ad esempio, un vincolo di chiave in un **CustomerID** elemento figlio di un **cliente** elemento nello schema indica che i valori del **CustomerID** deve essere l'elemento figlio univoco in qualsiasi istanza di documento, e che non sono consentiti valori null.</span><span class="sxs-lookup"><span data-stu-id="23da2-110">For example, a key constraint on a **CustomerID** child element of a **Customer** element in the schema indicates that the values of the **CustomerID** child element must be unique in any document instance, and that null values are not allowed.</span></span>  
  
 <span data-ttu-id="23da2-111">È anche possibile specificare vincoli tra elementi e attributi in un documento, in modo da stabilire una relazione all'interno del documento.</span><span class="sxs-lookup"><span data-stu-id="23da2-111">Constraints can also be specified between elements and attributes in a document, in order to establish a relationship within the document.</span></span> <span data-ttu-id="23da2-112">I vincoli key e keyref vengono usati nello schema per specificare i vincoli all'interno del documento, creando quindi una relazione tra gli elementi e gli attributi del documento.</span><span class="sxs-lookup"><span data-stu-id="23da2-112">The key and keyref constraints are used in the schema to specify the constraints within the document, resulting in a relationship between document elements and attributes.</span></span>  
  
 <span data-ttu-id="23da2-113">Il processo di mapping consente di convertire tali vincoli dello schema in vincoli appropriati per le tabelle create all'interno di **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="23da2-113">The mapping process converts these schema constraints into appropriate constraints on the tables created within the **DataSet**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="23da2-114">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="23da2-114">In This Section</span></span>  
 [<span data-ttu-id="23da2-115">Mapping tra vincoli XML Schema (XSD) univoci e vincoli di DataSet</span><span class="sxs-lookup"><span data-stu-id="23da2-115">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="23da2-116">Vengono descritti gli elementi di XML Schema utilizzati per creare vincoli univoci in un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="23da2-116">Describes the XML Schema elements used to create unique constraints in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="23da2-117">Mapping tra vincoli di chiave XML Schema (XSD) e vincoli di DataSet</span><span class="sxs-lookup"><span data-stu-id="23da2-117">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="23da2-118">Vengono descritti gli elementi di XML Schema utilizzati per creare vincoli key (vincoli univoci in cui non sono consentiti valori null) in un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="23da2-118">Describes the XML Schema elements used to create key constraints (unique constraints where null values are not allowed) in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="23da2-119">Mapping tra vincoli keyref XML Schema (XSD) e vincoli di DataSet</span><span class="sxs-lookup"><span data-stu-id="23da2-119">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="23da2-120">Vengono descritti gli elementi di XML Schema utilizzati per creare keyref vincoli (chiave esterna) in un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="23da2-120">Describes the XML Schema elements used to create keyref (foreign key) constraints in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="23da2-121">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="23da2-121">Related Sections</span></span>  
 [<span data-ttu-id="23da2-122">Derivazione della struttura relazionale di DataSet da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="23da2-122">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="23da2-123">Viene descritta la struttura relazionale, o schema, di un **DataSet** creato dallo schema XSD.</span><span class="sxs-lookup"><span data-stu-id="23da2-123">Describes the relational structure, or schema, of a **DataSet** that is created from XSD schema.</span></span>  
  
 [<span data-ttu-id="23da2-124">Generazione di relazioni tra DataSet da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="23da2-124">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="23da2-125">Vengono descritti gli elementi di XML Schema utilizzati per creare relazioni tra le colonne della tabella in un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="23da2-125">Describes the XML Schema elements used to create relations between table columns in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23da2-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23da2-126">See Also</span></span>  
 [<span data-ttu-id="23da2-127">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="23da2-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
