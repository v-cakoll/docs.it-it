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
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8c5cfcc9f35e4a07e9426a4dd24c1e2f04985f16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="style-sheet-directives-embedded-in-a-document"></a><span data-ttu-id="e4694-102">Fogli di stile incorporati in un documento</span><span class="sxs-lookup"><span data-stu-id="e4694-102">Style Sheet Directives Embedded in a Document</span></span>
<span data-ttu-id="e4694-103">Può accadere che il codice XML esistente contenga la direttiva dei fogli di stile di `<?xml:stylesheet?>`</span><span class="sxs-lookup"><span data-stu-id="e4694-103">Occasionally, existing XML contains the style sheet directive of `<?xml:stylesheet?>`.</span></span> <span data-ttu-id="e4694-104">Microsoft Internet Explorer viene accettata come alternativa per il `<?xml-stylesheet?>` sintassi.</span><span class="sxs-lookup"><span data-stu-id="e4694-104">Microsoft Internet Explorer accepts this as an alternative to the `<?xml-stylesheet?>` syntax.</span></span> <span data-ttu-id="e4694-105">Quando i dati XML contengono una direttiva `<?xml:stylesheet?>`, come nei dati seguenti, se si tenta di caricare questi dati nel DOM XML, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e4694-105">When the XML data contains an `<?xml:stylesheet?>` directive, as shown in the following data, attempting to load this data into the XML Document Object Model (DOM) throws an exception.</span></span>  
  
```xml  
<?xml version="1.0" ?>  
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>  
<root>  
    <test>Node 1</test>  
    <test>Node 2</test>  
</root>  
```  
  
 <span data-ttu-id="e4694-106">Questo errore si verifica perché il `<?xml:stylesheet?>` viene considerata non valida **ProcessingInstruction** al DOM.</span><span class="sxs-lookup"><span data-stu-id="e4694-106">This occurs because the `<?xml:stylesheet?>` is considered an invalid **ProcessingInstruction** to the DOM.</span></span> <span data-ttu-id="e4694-107">Qualsiasi **ProcessingInstruction**, in base agli spazi dei nomi specifica XML, è possibile solo senza due punti (NCName), nomi (QName).</span><span class="sxs-lookup"><span data-stu-id="e4694-107">Any **ProcessingInstruction**, according to the Namespaces in XML specification, can only be no-colon names (NCNames), as opposed to qualified names (QNames).</span></span>  
  
 <span data-ttu-id="e4694-108">Dalla sezione 6 della specifica XML, l'effetto della presenza degli spazi del **carico** e **LoadXml** metodi sono conformi alla specifica significa che in un documento:</span><span class="sxs-lookup"><span data-stu-id="e4694-108">From Section 6 of the Namespaces in XML specification, the effect of having the **Load** and **LoadXml** methods conform to the specification is that in a document:</span></span>  
  
-   <span data-ttu-id="e4694-109">Tutti i tipi di elementi e i nomi di attributi contengono uno zero o un segno di due punti.</span><span class="sxs-lookup"><span data-stu-id="e4694-109">All element types and attribute names contain either zero or one colon.</span></span>  
  
-   <span data-ttu-id="e4694-110">Nessun nome di entità, destinazione di ProcessingInstruction o nome di notazione contiene alcun segno di due punti.</span><span class="sxs-lookup"><span data-stu-id="e4694-110">No entity names, ProcessingInstruction targets, or notation names contain any colons.</span></span>  
  
 <span data-ttu-id="e4694-111">Poiché `<?xml:stylesheet?>` contiene un segno di due punti, viene violata la regola del secondo punto.</span><span class="sxs-lookup"><span data-stu-id="e4694-111">With the `<?xml:stylesheet?>` containing a colon, you now violate the rule in the second bullet.</span></span>  
  
 <span data-ttu-id="e4694-112">Secondo la raccomandazione W3C (World Wide Web Consortium) Associating Style Sheets with XML documents Version 1.0 (informazioni in lingua inglese), disponibile all'indirizzo www.w3.org/TR/xml-stylesheet, l'istruzione di elaborazione per associare un foglio di stile XSL a un documento XML è `<?xml-stylesheet?>`, con un trattino al posto del segno di due punti.</span><span class="sxs-lookup"><span data-stu-id="e4694-112">According to the World Wide Web Consortium (W3C) Associating Style Sheets with XML documents Version 1.0 Recommendation, located at www.w3.org/TR/xml-stylesheet, the processing instruction to associate an XSLT style sheet with an XML document is `<?xml-stylesheet?>`, with a dash replacing the colon.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4694-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4694-113">See Also</span></span>  
 [<span data-ttu-id="e4694-114">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="e4694-114">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
