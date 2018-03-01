---
title: "Influenza dello spazio dei nomi sull'espansione dei riferimenti alle entità per i nuovi nodi contenenti elementi e attributi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64359aee-aab0-4042-9a32-d19789af6ca7
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9b59f85eb0ef6646345eaef2a409f622c6fe4651
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="namespace-affect-on-entity-reference-expansion-for-new-nodes-containing-elements-and-attributes"></a>Influenza dello spazio dei nomi sull'espansione dei riferimenti alle entità per i nuovi nodi contenenti elementi e attributi
Poiché il contenuto di una dichiarazione di entità può contenere praticamente qualsiasi elemento, è possibile che contenga un elemento quale `<!ENTITY aname "<elem>test</elem>">`.  
  
 Quando il codice XML viene analizzato dal parser, `&aname;` non viene espanso con il contenuto di sostituzione durante l'analisi. L'espansione del codice XML non viene eseguita in quanto la risoluzione dello spazio dei nomi dell'elemento non può verificarsi fino a quando il nodo non viene posizionato nel documento. Fino a quel momento, non è possibile sapere quale spazio dei nomi è incluso nell'ambito. Quando il nodo viene inserito nel documento, si verifica la risoluzione dello spazio dei nomi e il contenuto dell'entità risultante viene analizzato dal parser nei nodi appropriati.  
  
> [!NOTE]
>  Una volta verificatasi l'espansione su un nodo di riferimento all'entità appena creato, l'espansione non si ripete. Pertanto gli spazi dei nomi usati nel testo di sostituzione per l'elemento vengono associati nel momento in cui viene impostato il nodo padre. È tuttavia possibile modificare lo spazio dei nomi nel caso in cui i nodi di riferimento all'entità esistenti vengano rimossi e quindi inseriti in un punto diverso o nel caso di nodi di riferimento all'entità clonati con il metodo **CloneNode**.  
  
## <a name="see-also"></a>Vedere anche  
 [Modello DOM (Document Object Mode) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
