---
title: Accesso a XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 282b7d91ec7cfe2f587c67bc9a982f0da22ad925
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410309"
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="dfc07-102">Accesso a XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dfc07-102">Accessing XML in Visual Basic</span></span>
<span data-ttu-id="dfc07-103">Visual Basic fornisce proprietà Axis XML per l'accesso e l'esplorazione delle [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] strutture.</span><span class="sxs-lookup"><span data-stu-id="dfc07-103">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="dfc07-104">Queste proprietà utilizzano una sintassi speciale per consentire l'accesso agli elementi e agli attributi specificando i nomi XML.</span><span class="sxs-lookup"><span data-stu-id="dfc07-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="dfc07-105">Nella tabella seguente sono elencate le funzionalità del linguaggio che consentono di accedere agli elementi e agli attributi XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="dfc07-105">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="dfc07-106">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="dfc07-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="dfc07-107">Descrizione proprietà</span><span class="sxs-lookup"><span data-stu-id="dfc07-107">Property description</span></span>|<span data-ttu-id="dfc07-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="dfc07-108">Example</span></span>|<span data-ttu-id="dfc07-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dfc07-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="dfc07-110">*child - asse*</span><span class="sxs-lookup"><span data-stu-id="dfc07-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="dfc07-111">Ottiene tutti `phone` gli elementi che sono elementi figlio dell' `contact` elemento.</span><span class="sxs-lookup"><span data-stu-id="dfc07-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="dfc07-112">*attributo, asse*</span><span class="sxs-lookup"><span data-stu-id="dfc07-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="dfc07-113">Ottiene tutti `type` gli attributi dell' `phone` elemento.</span><span class="sxs-lookup"><span data-stu-id="dfc07-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="dfc07-114">*descendant - asse*</span><span class="sxs-lookup"><span data-stu-id="dfc07-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="dfc07-115">Ottiene tutti `name` gli elementi dell' `contacts` elemento, indipendentemente dalla profondità della gerarchia in cui si verificano.</span><span class="sxs-lookup"><span data-stu-id="dfc07-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="dfc07-116">*indicizzatore di estensione*</span><span class="sxs-lookup"><span data-stu-id="dfc07-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="dfc07-117">Ottiene il primo `name` elemento dalla sequenza.</span><span class="sxs-lookup"><span data-stu-id="dfc07-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="dfc07-118">*value*</span><span class="sxs-lookup"><span data-stu-id="dfc07-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="dfc07-119">Ottiene la rappresentazione di stringa del primo oggetto nella sequenza o `Nothing` se la sequenza è vuota.</span><span class="sxs-lookup"><span data-stu-id="dfc07-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="dfc07-120">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="dfc07-120">In This Section</span></span>  
 [<span data-ttu-id="dfc07-121">Procedura: Accedere agli elementi discendenti XML</span><span class="sxs-lookup"><span data-stu-id="dfc07-121">How to: Access XML Descendant Elements</span></span>](how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="dfc07-122">Viene illustrato come utilizzare una proprietà asse discendente per accedere a tutti gli elementi XML con un nome specificato e che sono contenuti in un elemento XML specificato.</span><span class="sxs-lookup"><span data-stu-id="dfc07-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="dfc07-123">Procedura: Accedere agli elementi figlio XML</span><span class="sxs-lookup"><span data-stu-id="dfc07-123">How to: Access XML Child Elements</span></span>](how-to-access-xml-child-elements.md)  
 <span data-ttu-id="dfc07-124">Viene illustrato come utilizzare una proprietà Axis figlio per accedere a tutti gli elementi figlio XML con un nome specificato in un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="dfc07-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="dfc07-125">Procedura: accedere agli attributi XML</span><span class="sxs-lookup"><span data-stu-id="dfc07-125">How to: Access XML Attributes</span></span>](how-to-access-xml-attributes.md)  
 <span data-ttu-id="dfc07-126">Viene illustrato come utilizzare una proprietà axis dell'attributo per accedere a tutti gli attributi XML con un nome specificato in un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="dfc07-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="dfc07-127">Procedura: Dichiarare e usare prefissi dello spazio dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="dfc07-127">How to: Declare and Use XML Namespace Prefixes</span></span>](how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="dfc07-128">Viene illustrato come dichiarare un prefisso dello spazio dei nomi XML e utilizzarlo per creare e accedere a elementi XML.</span><span class="sxs-lookup"><span data-stu-id="dfc07-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="dfc07-129">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="dfc07-129">Related Sections</span></span>  
 [<span data-ttu-id="dfc07-130">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="dfc07-130">XML Axis Properties</span></span>](../../../language-reference/xml-axis/index.md)  
 <span data-ttu-id="dfc07-131">Vengono forniti collegamenti a sezioni che descrivono le varie proprietà di accesso XML.</span><span class="sxs-lookup"><span data-stu-id="dfc07-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="dfc07-132">Cenni preliminari su LINQ to XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dfc07-132">Overview of LINQ to XML in Visual Basic</span></span>](overview-of-linq-to-xml.md)  
 <span data-ttu-id="dfc07-133">Viene fornita un'introduzione all'utilizzo di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="dfc07-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="dfc07-134">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dfc07-134">Creating XML in Visual Basic</span></span>](creating-xml.md)  
 <span data-ttu-id="dfc07-135">Viene fornita un'introduzione all'utilizzo di valori letterali XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="dfc07-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="dfc07-136">Modifica di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dfc07-136">Manipulating XML in Visual Basic</span></span>](manipulating-xml.md)  
 <span data-ttu-id="dfc07-137">Vengono forniti collegamenti alle sezioni relative al caricamento e alla modifica di XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="dfc07-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="dfc07-138">XML</span><span class="sxs-lookup"><span data-stu-id="dfc07-138">XML</span></span>](index.md)  
 <span data-ttu-id="dfc07-139">Vengono forniti collegamenti a sezioni che descrivono come utilizzare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="dfc07-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
