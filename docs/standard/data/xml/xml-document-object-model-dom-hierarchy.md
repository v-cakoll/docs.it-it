---
title: Gerarchia del modello a oggetti di documenti XML (Document Object Model, DOM)
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ef2b5b200f95cdfac9b08a33c328c1dfb797e59e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44179164"
---
# <a name="xml-document-object-model-dom-hierarchy"></a>Gerarchia del modello a oggetti di documenti XML (Document Object Model, DOM)
Nell'illustrazione seguente è rappresentata la gerarchia delle classi per il DOM XML, con il nome W3C (World Wide Web Consortium) tra parentesi insieme a quello della classe ove pertinente.  
  
 ![Gerarchia del modello a oggetti di documenti XML &#40;DOM&#41;](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")  
Gerarchia del modello a oggetti di documenti XML (DOM, Document Object Model)  
  
 Le classi seguenti non ereditano da **XmlNode**:  
  
-   **XmlImplementation**  
  
-   **XmlNamedNodeMap**  
  
-   **XmlNodeList**  
  
-   **XmlNodeChangedEventArgs**  
  
 La classe **XmlImplementation** viene usata per creare un documento XML. Per altre informazioni, vedere [Creazione di documenti XML](../../../../docs/standard/data/xml/xml-document-creation.md).  
  
 Dalla classe **XmlNamedNodeMap** viene gestito un set di nodi non ordinato. Per altre informazioni, vedere [Recupero di nodi non ordinati in base al nome o all'indice](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).  
  
 Dalla classe **XmlNodeList** viene gestito un elenco di nodi ordinato. Per altre informazioni, vedere [Recupero di nodi ordinati in base all'indice](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).  
  
 Dalla classe **XmlNodeChangedEventArgs** vengono gestiti i gestori eventi registrati in **XmlDocument**. Per altre informazioni, vedere [Gestione degli eventi in un documento XML con XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).  
  
 La classe **XmlLinkedNode** eredita da **XmlNode**. Lo scopo di questa classe è di eseguire l'override di due metodi di **XmlNode**: i metodi **PreviousSibling** e **NextSibling**. Questi metodi di cui è stato eseguito l'override vengono quindi ereditati e usati dalle classi **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** e **XmlProcessingInstruction**, che presentano elementi di pari livello precedenti e successivi.  
  
## <a name="see-also"></a>Vedere anche

- [Modello DOM (Document Object Mode) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
