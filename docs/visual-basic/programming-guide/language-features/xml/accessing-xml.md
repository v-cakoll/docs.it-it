---
title: Accesso a XML in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: b000b3f6846f800b2a96ce10cdd408a355f78a81
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649594"
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="eec2f-102">Accesso a XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eec2f-102">Accessing XML in Visual Basic</span></span>
<span data-ttu-id="eec2f-103">Visual Basic fornisce le proprietà axis XML per l'accesso e la navigazione [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] strutture.</span><span class="sxs-lookup"><span data-stu-id="eec2f-103">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="eec2f-104">Queste proprietà utilizzano una sintassi speciale che consente di accedere a elementi e attributi specificando i nomi XML.</span><span class="sxs-lookup"><span data-stu-id="eec2f-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="eec2f-105">Nella tabella seguente sono elencate le funzionalità del linguaggio che consentono di accedere agli elementi XML e attributi in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="eec2f-105">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="eec2f-106">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="eec2f-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="eec2f-107">Descrizione della proprietà</span><span class="sxs-lookup"><span data-stu-id="eec2f-107">Property description</span></span>|<span data-ttu-id="eec2f-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="eec2f-108">Example</span></span>|<span data-ttu-id="eec2f-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eec2f-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="eec2f-110">*asse child*</span><span class="sxs-lookup"><span data-stu-id="eec2f-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="eec2f-111">Ottiene tutti `phone` gli elementi figlio del `contact` elemento.</span><span class="sxs-lookup"><span data-stu-id="eec2f-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="eec2f-112">*asse attribute*</span><span class="sxs-lookup"><span data-stu-id="eec2f-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="eec2f-113">Ottiene tutti `type` gli attributi del `phone` elemento.</span><span class="sxs-lookup"><span data-stu-id="eec2f-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="eec2f-114">*asse descendant*</span><span class="sxs-lookup"><span data-stu-id="eec2f-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="eec2f-115">Ottiene tutti `name` elementi di `contacts` elemento, indipendentemente dal livello di profondità della gerarchia che si verifichino.</span><span class="sxs-lookup"><span data-stu-id="eec2f-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="eec2f-116">*indicizzatore di estensione*</span><span class="sxs-lookup"><span data-stu-id="eec2f-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="eec2f-117">Ottiene il primo `name` elemento dalla sequenza.</span><span class="sxs-lookup"><span data-stu-id="eec2f-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="eec2f-118">*valore*</span><span class="sxs-lookup"><span data-stu-id="eec2f-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="eec2f-119">Ottiene la rappresentazione di stringa del primo oggetto nella sequenza, o `Nothing` se la sequenza è vuota.</span><span class="sxs-lookup"><span data-stu-id="eec2f-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="eec2f-120">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="eec2f-120">In This Section</span></span>  
 [<span data-ttu-id="eec2f-121">Procedura: Accedere agli elementi discendenti XML</span><span class="sxs-lookup"><span data-stu-id="eec2f-121">How to: Access XML Descendant Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="eec2f-122">Di seguito viene illustrato come utilizzare una proprietà axis descendant per accedere a tutti gli elementi XML che hanno un nome specificato e che sono contenuti in un elemento XML specificato.</span><span class="sxs-lookup"><span data-stu-id="eec2f-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="eec2f-123">Procedura: Accedere agli elementi figlio XML</span><span class="sxs-lookup"><span data-stu-id="eec2f-123">How to: Access XML Child Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 <span data-ttu-id="eec2f-124">Viene illustrato come utilizzare un elemento figlio di proprietà dell'asse di accesso a tutti gli elementi figlio XML che hanno un nome specificato in un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="eec2f-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="eec2f-125">Procedura: Accedere agli attributi XML</span><span class="sxs-lookup"><span data-stu-id="eec2f-125">How to: Access XML Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 <span data-ttu-id="eec2f-126">Di seguito viene illustrato come utilizzare una proprietà axis dell'attributo per accedere a tutti gli attributi XML che hanno un nome specificato in un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="eec2f-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="eec2f-127">Procedura: Dichiarare e usare prefissi dello spazio dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="eec2f-127">How to: Declare and Use XML Namespace Prefixes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="eec2f-128">Viene illustrato come dichiarare un prefisso dello spazio dei nomi XML e utilizzarlo per creare e accedere agli elementi XML.</span><span class="sxs-lookup"><span data-stu-id="eec2f-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="eec2f-129">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="eec2f-129">Related Sections</span></span>  
 [<span data-ttu-id="eec2f-130">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="eec2f-130">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 <span data-ttu-id="eec2f-131">Vengono forniti collegamenti alle sezioni che descrive le varie proprietà di accesso XML.</span><span class="sxs-lookup"><span data-stu-id="eec2f-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="eec2f-132">Cenni preliminari su LINQ to XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eec2f-132">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="eec2f-133">Fornisce un'introduzione all'uso [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="eec2f-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="eec2f-134">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eec2f-134">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="eec2f-135">Fornisce un'introduzione all'utilizzo di valori letterali XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="eec2f-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="eec2f-136">Modifica di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="eec2f-136">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 <span data-ttu-id="eec2f-137">Vengono forniti collegamenti alle sezioni sul caricamento e modifica di XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="eec2f-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="eec2f-138">XML</span><span class="sxs-lookup"><span data-stu-id="eec2f-138">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="eec2f-139">Vengono forniti collegamenti a sezioni in cui viene illustrato come utilizzare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="eec2f-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
