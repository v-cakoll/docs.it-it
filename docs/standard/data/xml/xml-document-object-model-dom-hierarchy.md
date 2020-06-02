---
title: Gerarchia del modello a oggetti di documenti XML (Document Object Model, DOM)
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
ms.openlocfilehash: a6099b6c5e30fbf2e4d5d4ed046369bc8f884845
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291435"
---
# <a name="xml-document-object-model-dom-hierarchy"></a>Gerarchia del modello a oggetti di documenti XML (Document Object Model, DOM)
Nell'illustrazione seguente è rappresentata la gerarchia delle classi per il DOM XML, con il nome W3C (World Wide Web Consortium) tra parentesi insieme a quello della classe ove pertinente.  
  
 ![Document Object Model XML &#40;gerarchia&#41; DOM](media/dom-class-hierarchy.gif "Dom_class_hierarchy")  
Gerarchia del modello a oggetti di documenti XML (DOM, Document Object Model)  
  
 Le classi seguenti non ereditano da **XmlNode**:  
  
- **XmlImplementation**  
  
- **XmlNamedNodeMap**  
  
- **XmlNodeList**  
  
- **XmlNodeChangedEventArgs**  
  
 La classe **XmlImplementation** viene usata per creare un documento XML. Per altre informazioni, vedere [Creazione di documenti XML](xml-document-creation.md).  
  
 Dalla classe **XmlNamedNodeMap** viene gestito un set di nodi non ordinato. Per altre informazioni, vedere [Recupero di nodi non ordinati in base al nome o all'indice](unordered-node-retrieval-by-name-or-index.md).  
  
 Dalla classe **XmlNodeList** viene gestito un elenco di nodi ordinato. Per altre informazioni, vedere [Recupero di nodi ordinati in base all'indice](ordered-node-retrieval-by-index.md).  
  
 Dalla classe **XmlNodeChangedEventArgs** vengono gestiti i gestori eventi registrati in **XmlDocument**. Per altre informazioni, vedere [Gestione degli eventi in un documento XML con XmlNodeChangedEventArgs](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).  
  
 La classe **XmlLinkedNode** eredita da **XmlNode**. Lo scopo di questa classe è di eseguire l'override di due metodi di **XmlNode**: i metodi **PreviousSibling** e **NextSibling**. Questi metodi di cui è stato eseguito l'override vengono quindi ereditati e usati dalle classi **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** e **XmlProcessingInstruction**, che presentano elementi di pari livello precedenti e successivi.  
  
## <a name="see-also"></a>Vedere anche

- [XML DOM (Document Object Model)](xml-document-object-model-dom.md)
