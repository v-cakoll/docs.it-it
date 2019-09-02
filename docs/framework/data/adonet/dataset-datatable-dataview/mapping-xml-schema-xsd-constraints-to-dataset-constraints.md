---
title: Mapping tra vincoli XML Schema (XSD) e vincoli di dataset
ms.date: 03/30/2017
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
ms.openlocfilehash: b0082b534b8df10ac5277cf2f5aa5b2d2e40c11b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204629"
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="2bf0f-102">Mapping tra vincoli XML Schema (XSD) e vincoli di dataset</span><span class="sxs-lookup"><span data-stu-id="2bf0f-102">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="2bf0f-103">Lo schema XSD (XML Schema Definition Language) consente di specificare vincoli sugli elementi e sugli attributi in esso definiti.</span><span class="sxs-lookup"><span data-stu-id="2bf0f-103">The XML Schema definition language (XSD) allows constraints to be specified on the elements and attributes it defines.</span></span> <span data-ttu-id="2bf0f-104">Quando si esegue il mapping di un XML Schema a uno <xref:System.Data.DataSet>schema relazionale in un, i vincoli XML schema vengono mappati ai vincoli relazionali appropriati sulle tabelle e sulle colonne all'interno del **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="2bf0f-104">When mapping an XML Schema to relational schema in a <xref:System.Data.DataSet>, XML Schema constraints are mapped to appropriate relational constraints on the tables and columns within the **DataSet**.</span></span>  
  
 <span data-ttu-id="2bf0f-105">Contenuto della sezione viene illustrato il mapping dei seguenti vincoli di XML Schema:</span><span class="sxs-lookup"><span data-stu-id="2bf0f-105">This section discusses the mapping of the following XML Schema constraints:</span></span>  
  
- <span data-ttu-id="2bf0f-106">Vincolo di univocità specificato utilizzando l'elemento **Unique** .</span><span class="sxs-lookup"><span data-stu-id="2bf0f-106">The uniqueness constraint specified using the **unique** element.</span></span>  
  
- <span data-ttu-id="2bf0f-107">Vincolo di chiave specificato mediante l'elemento **Key** .</span><span class="sxs-lookup"><span data-stu-id="2bf0f-107">The key constraint specified using the **key** element.</span></span>  
  
- <span data-ttu-id="2bf0f-108">Vincolo keyref specificato utilizzando l'elemento **keyref** .</span><span class="sxs-lookup"><span data-stu-id="2bf0f-108">The keyref constraint specified using the **keyref** element.</span></span>  
  
 <span data-ttu-id="2bf0f-109">Usando un vincolo su un elemento o su un attributo, si specificano determinate restrizioni relative ai valori dell'elemento in qualsiasi istanza del documento.</span><span class="sxs-lookup"><span data-stu-id="2bf0f-109">By using a constraint on an element or attribute, you specify certain restrictions on the values of the element in any instance of the document.</span></span> <span data-ttu-id="2bf0f-110">Un vincolo di chiave per un elemento figlio **CustomerID** di un elemento **Customer** nello schema, ad esempio, indica che i valori dell'elemento figlio **CustomerID** devono essere univoci in qualsiasi istanza del documento e che i valori null non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="2bf0f-110">For example, a key constraint on a **CustomerID** child element of a **Customer** element in the schema indicates that the values of the **CustomerID** child element must be unique in any document instance, and that null values are not allowed.</span></span>  
  
 <span data-ttu-id="2bf0f-111">È anche possibile specificare vincoli tra elementi e attributi in un documento, in modo da stabilire una relazione all'interno del documento.</span><span class="sxs-lookup"><span data-stu-id="2bf0f-111">Constraints can also be specified between elements and attributes in a document, in order to establish a relationship within the document.</span></span> <span data-ttu-id="2bf0f-112">I vincoli key e keyref vengono usati nello schema per specificare i vincoli all'interno del documento, creando quindi una relazione tra gli elementi e gli attributi del documento.</span><span class="sxs-lookup"><span data-stu-id="2bf0f-112">The key and keyref constraints are used in the schema to specify the constraints within the document, resulting in a relationship between document elements and attributes.</span></span>  
  
 <span data-ttu-id="2bf0f-113">Il processo di mapping converte questi vincoli dello schema in vincoli appropriati per le tabelle create all'interno del **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="2bf0f-113">The mapping process converts these schema constraints into appropriate constraints on the tables created within the **DataSet**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2bf0f-114">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="2bf0f-114">In This Section</span></span>  
 [<span data-ttu-id="2bf0f-115">Mapping tra vincoli XML Schema (XSD) univoci e vincoli di DataSet</span><span class="sxs-lookup"><span data-stu-id="2bf0f-115">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>](map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="2bf0f-116">Vengono descritti gli elementi di XML Schema usati per creare vincoli univoci in un **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="2bf0f-116">Describes the XML Schema elements used to create unique constraints in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="2bf0f-117">Mapping tra vincoli di chiave XML Schema (XSD) e vincoli di DataSet</span><span class="sxs-lookup"><span data-stu-id="2bf0f-117">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>](map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="2bf0f-118">Vengono descritti gli elementi di XML Schema usati per creare vincoli di chiave (vincoli UNIQUE in cui i valori null non sono consentiti) in un **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="2bf0f-118">Describes the XML Schema elements used to create key constraints (unique constraints where null values are not allowed) in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="2bf0f-119">Mapping tra vincoli keyref XML Schema (XSD) e vincoli di DataSet</span><span class="sxs-lookup"><span data-stu-id="2bf0f-119">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>](map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="2bf0f-120">Vengono descritti gli elementi di XML Schema utilizzati per creare vincoli keyref (Foreign Key) in un **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="2bf0f-120">Describes the XML Schema elements used to create keyref (foreign key) constraints in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2bf0f-121">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="2bf0f-121">Related Sections</span></span>  
 [<span data-ttu-id="2bf0f-122">Derivazione della struttura relazionale di DataSet da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="2bf0f-122">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="2bf0f-123">Viene descritta la struttura relazionale, o schema, di un **set di dati** creato da uno schema XSD.</span><span class="sxs-lookup"><span data-stu-id="2bf0f-123">Describes the relational structure, or schema, of a **DataSet** that is created from XSD schema.</span></span>  
  
 [<span data-ttu-id="2bf0f-124">Generazione di relazioni tra DataSet da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="2bf0f-124">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="2bf0f-125">Vengono descritti gli elementi di XML Schema utilizzati per creare relazioni tra le colonne della tabella in un **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="2bf0f-125">Describes the XML Schema elements used to create relations between table columns in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bf0f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2bf0f-126">See also</span></span>

- [<span data-ttu-id="2bf0f-127">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="2bf0f-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
