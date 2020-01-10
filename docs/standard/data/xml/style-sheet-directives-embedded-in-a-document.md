---
title: Fogli di stile incorporati in un documento
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
ms.openlocfilehash: 19e25ab7262bb006144eea71e74bd7454066b3f6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710154"
---
# <a name="style-sheet-directives-embedded-in-a-document"></a><span data-ttu-id="d0a19-102">Fogli di stile incorporati in un documento</span><span class="sxs-lookup"><span data-stu-id="d0a19-102">Style Sheet Directives Embedded in a Document</span></span>

<span data-ttu-id="d0a19-103">Può accadere che il codice XML esistente contenga la direttiva dei fogli di stile di `<?xml:stylesheet?>`</span><span class="sxs-lookup"><span data-stu-id="d0a19-103">Occasionally, existing XML contains the style sheet directive of `<?xml:stylesheet?>`.</span></span> <span data-ttu-id="d0a19-104">che viene accettata da Microsoft Internet Explorer come alternativa alla sintassi `<?xml-stylesheet?>`.</span><span class="sxs-lookup"><span data-stu-id="d0a19-104">Microsoft Internet Explorer accepts this as an alternative to the `<?xml-stylesheet?>` syntax.</span></span> <span data-ttu-id="d0a19-105">Quando i dati XML contengono una direttiva `<?xml:stylesheet?>`, come nei dati seguenti, se si tenta di caricare questi dati nel DOM XML, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d0a19-105">When the XML data contains an `<?xml:stylesheet?>` directive, as shown in the following data, attempting to load this data into the XML Document Object Model (DOM) throws an exception.</span></span>

```xml
<?xml version="1.0" ?>
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>
<root>
    <test>Node 1</test>
    <test>Node 2</test>
</root>
```

<span data-ttu-id="d0a19-106">Questo si verifica perché `<?xml:stylesheet?>` viene considerata una **ProcessingInstruction** non valida per il DOM.</span><span class="sxs-lookup"><span data-stu-id="d0a19-106">This occurs because the `<?xml:stylesheet?>` is considered an invalid **ProcessingInstruction** to the DOM.</span></span> <span data-ttu-id="d0a19-107">In base alla specifica XML degli spazi dei nomi, una **ProcessingInstruction** può essere solo un NCName (No Column Name, nome senza due punti).</span><span class="sxs-lookup"><span data-stu-id="d0a19-107">Any **ProcessingInstruction**, according to the Namespaces in XML specification, can only be no-colon names (NCNames), as opposed to qualified names (QNames).</span></span>

<span data-ttu-id="d0a19-108">In base alla sezione 6 della specifica sugli spazi dei nomi in XML, la conformità dei metodi **Load** e **LoadXml** alla specifica significa che in un documento:</span><span class="sxs-lookup"><span data-stu-id="d0a19-108">From Section 6 of the Namespaces in XML specification, the effect of having the **Load** and **LoadXml** methods conform to the specification is that in a document:</span></span>

- <span data-ttu-id="d0a19-109">Tutti i tipi di elementi e i nomi di attributi contengono uno zero o un segno di due punti.</span><span class="sxs-lookup"><span data-stu-id="d0a19-109">All element types and attribute names contain either zero or one colon.</span></span>

- <span data-ttu-id="d0a19-110">Nessun nome di entità, destinazione di ProcessingInstruction o nome di notazione contiene alcun segno di due punti.</span><span class="sxs-lookup"><span data-stu-id="d0a19-110">No entity names, ProcessingInstruction targets, or notation names contain any colons.</span></span>

<span data-ttu-id="d0a19-111">Poiché `<?xml:stylesheet?>` contiene un segno di due punti, viene violata la regola del secondo punto.</span><span class="sxs-lookup"><span data-stu-id="d0a19-111">With the `<?xml:stylesheet?>` containing a colon, you now violate the rule in the second bullet.</span></span>

<span data-ttu-id="d0a19-112">Secondo la raccomandazione W3C (World Wide Web Consortium) [Associating Style Sheets with XML documents Version 1.0](https://www.w3.org/TR/xml-stylesheet/), l'istruzione di elaborazione per associare un foglio di stile XSL a un documento XML è `<?xml-stylesheet?>`, con un trattino al posto del segno di due punti.</span><span class="sxs-lookup"><span data-stu-id="d0a19-112">According to the World Wide Web Consortium (W3C) [Associating Style Sheets with XML documents Version 1.0 Recommendation](https://www.w3.org/TR/xml-stylesheet/),  the processing instruction to associate an XSLT style sheet with an XML document is `<?xml-stylesheet?>`, with a dash replacing the colon.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0a19-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0a19-113">See also</span></span>

- [<span data-ttu-id="d0a19-114">Modello DOM (Document Object Mode) XML</span><span class="sxs-lookup"><span data-stu-id="d0a19-114">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
