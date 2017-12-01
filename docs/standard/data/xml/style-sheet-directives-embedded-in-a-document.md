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
# <a name="style-sheet-directives-embedded-in-a-document"></a>Fogli di stile incorporati in un documento
Può accadere che il codice XML esistente contenga la direttiva dei fogli di stile di `<?xml:stylesheet?>` Microsoft Internet Explorer viene accettata come alternativa per il `<?xml-stylesheet?>` sintassi. Quando i dati XML contengono una direttiva `<?xml:stylesheet?>`, come nei dati seguenti, se si tenta di caricare questi dati nel DOM XML, viene generata un'eccezione.  
  
```xml  
<?xml version="1.0" ?>  
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>  
<root>  
    <test>Node 1</test>  
    <test>Node 2</test>  
</root>  
```  
  
 Questo errore si verifica perché il `<?xml:stylesheet?>` viene considerata non valida **ProcessingInstruction** al DOM. Qualsiasi **ProcessingInstruction**, in base agli spazi dei nomi specifica XML, è possibile solo senza due punti (NCName), nomi (QName).  
  
 Dalla sezione 6 della specifica XML, l'effetto della presenza degli spazi del **carico** e **LoadXml** metodi sono conformi alla specifica significa che in un documento:  
  
-   Tutti i tipi di elementi e i nomi di attributi contengono uno zero o un segno di due punti.  
  
-   Nessun nome di entità, destinazione di ProcessingInstruction o nome di notazione contiene alcun segno di due punti.  
  
 Poiché `<?xml:stylesheet?>` contiene un segno di due punti, viene violata la regola del secondo punto.  
  
 Secondo la raccomandazione W3C (World Wide Web Consortium) Associating Style Sheets with XML documents Version 1.0 (informazioni in lingua inglese), disponibile all'indirizzo www.w3.org/TR/xml-stylesheet, l'istruzione di elaborazione per associare un foglio di stile XSL a un documento XML è `<?xml-stylesheet?>`, con un trattino al posto del segno di due punti.  
  
## <a name="see-also"></a>Vedere anche  
 [XML Document Object Model (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
