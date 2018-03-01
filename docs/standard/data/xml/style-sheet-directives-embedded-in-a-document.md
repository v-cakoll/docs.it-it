---
title: Fogli di stile incorporati in un documento
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b0d4589dc73b4effeff553e5b7bf5562a7602c2d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="style-sheet-directives-embedded-in-a-document"></a><span data-ttu-id="6be88-102">Fogli di stile incorporati in un documento</span><span class="sxs-lookup"><span data-stu-id="6be88-102">Style Sheet Directives Embedded in a Document</span></span>
<span data-ttu-id="6be88-103">Può accadere che il codice XML esistente contenga la direttiva dei fogli di stile di `<?xml:stylesheet?>`</span><span class="sxs-lookup"><span data-stu-id="6be88-103">Occasionally, existing XML contains the style sheet directive of `<?xml:stylesheet?>`.</span></span> <span data-ttu-id="6be88-104">che viene accettata da Microsoft Internet Explorer come alternativa alla sintassi `<?xml-stylesheet?>`.</span><span class="sxs-lookup"><span data-stu-id="6be88-104">Microsoft Internet Explorer accepts this as an alternative to the `<?xml-stylesheet?>` syntax.</span></span> <span data-ttu-id="6be88-105">Quando i dati XML contengono una direttiva `<?xml:stylesheet?>`, come nei dati seguenti, se si tenta di caricare questi dati nel DOM XML, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="6be88-105">When the XML data contains an `<?xml:stylesheet?>` directive, as shown in the following data, attempting to load this data into the XML Document Object Model (DOM) throws an exception.</span></span>  
  
```xml  
<?xml version="1.0" ?>  
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>  
<root>  
    <test>Node 1</test>  
    <test>Node 2</test>  
</root>  
```  
  
 <span data-ttu-id="6be88-106">Questo si verifica perché `<?xml:stylesheet?>` viene considerata una **ProcessingInstruction** non valida per il DOM.</span><span class="sxs-lookup"><span data-stu-id="6be88-106">This occurs because the `<?xml:stylesheet?>` is considered an invalid **ProcessingInstruction** to the DOM.</span></span> <span data-ttu-id="6be88-107">In base alla specifica XML degli spazi dei nomi, una **ProcessingInstruction** può essere solo un NCName (No Column Name, nome senza due punti).</span><span class="sxs-lookup"><span data-stu-id="6be88-107">Any **ProcessingInstruction**, according to the Namespaces in XML specification, can only be no-colon names (NCNames), as opposed to qualified names (QNames).</span></span>  
  
 <span data-ttu-id="6be88-108">In base alla sezione 6 della specifica sugli spazi dei nomi in XML, la conformità dei metodi **Load** e **LoadXml** alla specifica significa che in un documento:</span><span class="sxs-lookup"><span data-stu-id="6be88-108">From Section 6 of the Namespaces in XML specification, the effect of having the **Load** and **LoadXml** methods conform to the specification is that in a document:</span></span>  
  
-   <span data-ttu-id="6be88-109">Tutti i tipi di elementi e i nomi di attributi contengono uno zero o un segno di due punti.</span><span class="sxs-lookup"><span data-stu-id="6be88-109">All element types and attribute names contain either zero or one colon.</span></span>  
  
-   <span data-ttu-id="6be88-110">Nessun nome di entità, destinazione di ProcessingInstruction o nome di notazione contiene alcun segno di due punti.</span><span class="sxs-lookup"><span data-stu-id="6be88-110">No entity names, ProcessingInstruction targets, or notation names contain any colons.</span></span>  
  
 <span data-ttu-id="6be88-111">Poiché `<?xml:stylesheet?>` contiene un segno di due punti, viene violata la regola del secondo punto.</span><span class="sxs-lookup"><span data-stu-id="6be88-111">With the `<?xml:stylesheet?>` containing a colon, you now violate the rule in the second bullet.</span></span>  
  
 <span data-ttu-id="6be88-112">Secondo la raccomandazione W3C (World Wide Web Consortium) Associating Style Sheets with XML documents Version 1.0 (informazioni in lingua inglese), disponibile all'indirizzo www.w3.org/TR/xml-stylesheet, l'istruzione di elaborazione per associare un foglio di stile XSL a un documento XML è `<?xml-stylesheet?>`, con un trattino al posto del segno di due punti.</span><span class="sxs-lookup"><span data-stu-id="6be88-112">According to the World Wide Web Consortium (W3C) Associating Style Sheets with XML documents Version 1.0 Recommendation, located at www.w3.org/TR/xml-stylesheet, the processing instruction to associate an XSLT style sheet with an XML document is `<?xml-stylesheet?>`, with a dash replacing the colon.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6be88-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6be88-113">See Also</span></span>  
 [<span data-ttu-id="6be88-114">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="6be88-114">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
