---
title: Lettura delle dichiarazioni di entità e dei riferimenti a entità nel DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 86dba977-5cc4-4567-964f-027ffabc47b2
ms.openlocfilehash: fa650e75d7661eeafea74146f5cbb61878978575
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710401"
---
# <a name="reading-entity-declarations-and-entity-references-into-the-dom"></a><span data-ttu-id="5853b-102">Lettura delle dichiarazioni di entità e dei riferimenti a entità nel DOM</span><span class="sxs-lookup"><span data-stu-id="5853b-102">Reading Entity Declarations and Entity References into the DOM</span></span>
<span data-ttu-id="5853b-103">Un'entità è una dichiarazione che stabilisce il nome da usare in XML al posto del contenuto o del markup.</span><span class="sxs-lookup"><span data-stu-id="5853b-103">An entity is a declaration that states a name to be used in the XML in place of content or markup.</span></span> <span data-ttu-id="5853b-104">Le entità sono composte da due parti.</span><span class="sxs-lookup"><span data-stu-id="5853b-104">There are two parts to entities.</span></span> <span data-ttu-id="5853b-105">Innanzitutto, è necessario associare un nome al contenuto di sostituzione tramite una dichiarazione di entità.</span><span class="sxs-lookup"><span data-stu-id="5853b-105">First, you must tie a name to the replacement content using an entity declaration.</span></span> <span data-ttu-id="5853b-106">La dichiarazione di entità viene creata mediante la sintassi `<!ENTITY name "value">` in una DTD (Document Type Definition) o in uno schema XML.</span><span class="sxs-lookup"><span data-stu-id="5853b-106">An entity declaration is created by using the `<!ENTITY name "value">` syntax in a document type definition (DTD) or XML schema.</span></span> <span data-ttu-id="5853b-107">Successivamente, il nome definito nella dichiarazione di entità viene usato in XML</span><span class="sxs-lookup"><span data-stu-id="5853b-107">Secondly, the name defined in the entity declaration is subsequently used in the XML.</span></span> <span data-ttu-id="5853b-108">e, in questo caso, viene denominato riferimento all'entità.</span><span class="sxs-lookup"><span data-stu-id="5853b-108">When used in the XML, it is called an entity reference.</span></span> <span data-ttu-id="5853b-109">Ad esempio, la dichiarazione di entità seguente dichiara un'entità il cui nome `publisher` viene associato al contenuto di "Microsoft Press".</span><span class="sxs-lookup"><span data-stu-id="5853b-109">For example, the following entity declaration declares an entity of the name `publisher` being associated with the content of "Microsoft Press".</span></span>  
  
```xml  
<!ENTITY publisher "Microsoft Press">  
```  
  
 <span data-ttu-id="5853b-110">Nel seguente esempio è illustrato l'uso di questa dichiarazione di entità in XML come riferimento all'entità.</span><span class="sxs-lookup"><span data-stu-id="5853b-110">The following example shows the use of this entity declaration in XML as an entity reference.</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="5853b-111">Alcuni parser consentono di espandere automaticamente le entità quando viene caricato un documento in memoria.</span><span class="sxs-lookup"><span data-stu-id="5853b-111">Some parsers automatically expand entities when a document is loaded into memory.</span></span> <span data-ttu-id="5853b-112">Quindi, quando l'XML viene letto in memoria, le dichiarazioni di entità vengono memorizzate e salvate.</span><span class="sxs-lookup"><span data-stu-id="5853b-112">Therefore, when the XML is being read into memory, entity declarations are remembered and saved.</span></span> <span data-ttu-id="5853b-113">Durante il successivo rilevamento dei caratteri `&;`, che identificano un riferimento a un'entità generale, il parser ricercherà quel determinato nome in una tabella delle dichiarazioni di entità.</span><span class="sxs-lookup"><span data-stu-id="5853b-113">When the parser subsequently encounters `&;` characters, which identify a general entity reference, the parser looks up that name in an entity declaration table.</span></span> <span data-ttu-id="5853b-114">Il riferimento `&publisher;` verrà sostituito dal contenuto che rappresenta.</span><span class="sxs-lookup"><span data-stu-id="5853b-114">The reference, `&publisher;` is replaced by the content that it represents.</span></span> <span data-ttu-id="5853b-115">Usando il seguente codice XML,</span><span class="sxs-lookup"><span data-stu-id="5853b-115">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="5853b-116">espandendo il riferimento all'entità e sostituendo `&publisher;` con il contenuto di Microsoft Press viene fornito il seguente codice XML espanso.</span><span class="sxs-lookup"><span data-stu-id="5853b-116">expanding the entity reference and replacing the `&publisher;` with the Microsoft Press content gives the following expanded XML.</span></span>  
  
 <span data-ttu-id="5853b-117">**Output**</span><span class="sxs-lookup"><span data-stu-id="5853b-117">**Output**</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by Microsoft Press</pubinfo>  
```  
  
 <span data-ttu-id="5853b-118">Esistono molti tipi di entità.</span><span class="sxs-lookup"><span data-stu-id="5853b-118">There are many kinds of entities.</span></span> <span data-ttu-id="5853b-119">Nel diagramma seguente è riportata la suddivisione dei tipi di entità e della terminologia.</span><span class="sxs-lookup"><span data-stu-id="5853b-119">The following diagram shows the breakdown of entity types and terminology.</span></span>  
  
 <span data-ttu-id="5853b-120">![Diagramma di flusso della gerarchia del tipo di entità](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="5853b-120">![flow chart of entity type hierarchy](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")</span></span>  
  
 <span data-ttu-id="5853b-121">Per impostazione predefinita, nell'implementazione Microsoft .NET Framework del DOM XML, i riferimenti alle entità vengono conservati e le entità non vengono espanse quando si carica l'XML.</span><span class="sxs-lookup"><span data-stu-id="5853b-121">The default for the Microsoft .NET Framework implementation of the XML Document Object Model (DOM) is to preserve the entities references and not expand the entities when the XML is loaded.</span></span> <span data-ttu-id="5853b-122">Di conseguenza quando un documento viene caricato nel DOM, viene creato un nodo **XmlEntityReference** contenente la variabile di riferimento `&publisher;` con tutti i nodi figlio che rappresentano il contenuto dell'entità dichiarata nella DTD.</span><span class="sxs-lookup"><span data-stu-id="5853b-122">The implication of this is that as a document is loaded in the DOM, an **XmlEntityReference** node containing the reference variable `&publisher;` is created, with child nodes representing the content in the entity declared in the DTD.</span></span>  
  
 <span data-ttu-id="5853b-123">Usando la dichiarazione di entità `<!ENTITY publisher "Microsoft Press">`, nel diagramma seguente vengono mostrati i nodi **XmlEntity** e **XmlText** creati da questa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="5853b-123">Using the `<!ENTITY publisher "Microsoft Press">` entity declaration, the following diagram shows the **XmlEntity** and **XmlText** nodes created from this declaration.</span></span>  
  
 <span data-ttu-id="5853b-124">![nodi creati da dichiarazioni di entità](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")</span><span class="sxs-lookup"><span data-stu-id="5853b-124">![nodes created from entity declaration](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")</span></span>  
  
 <span data-ttu-id="5853b-125">Il fatto che i riferimenti alle entità vengano espansi o meno determina quali nodi vengono generati nell'albero DOM, in memoria.</span><span class="sxs-lookup"><span data-stu-id="5853b-125">The differences when entity references are expanded and when they are not makes a difference in what nodes are generated in the DOM tree, in memory.</span></span> <span data-ttu-id="5853b-126">La differenza tra i nodi generati è descritta negli argomenti [Riferimenti alle entità conservati](../../../../docs/standard/data/xml/entity-references-are-preserved.md) e [Riferimenti alle entità espansi e non conservati](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md).</span><span class="sxs-lookup"><span data-stu-id="5853b-126">The difference in the nodes that are generated is explained in the topics [Entity References are Preserved](../../../../docs/standard/data/xml/entity-references-are-preserved.md) and [Entity References are Expanded and Not Preserved](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5853b-127">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="5853b-127">See also</span></span>

- [<span data-ttu-id="5853b-128">XML DOM (Document Object Model)</span><span class="sxs-lookup"><span data-stu-id="5853b-128">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
