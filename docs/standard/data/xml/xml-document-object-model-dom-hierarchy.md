---
title: Gerarchia del modello a oggetti di documenti XML (Document Object Model, DOM)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6dec61860fba5815b1dae802d280e8df6628ab91
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-object-model-dom-hierarchy"></a>Gerarchia del modello a oggetti di documenti XML (Document Object Model, DOM)
Nell'illustrazione seguente è rappresentata la gerarchia delle classi per il DOM XML, con il nome W3C (World Wide Web Consortium) tra parentesi insieme a quello della classe ove pertinente.  
  
 ![DOM XML Document Object Model &#40; &#41; gerarchia](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")  
Gerarchia del modello a oggetti di documenti XML (DOM, Document Object Model)  
  
 Le classi seguenti non ereditano il **XmlNode**:  
  
-   **XmlImplementation**  
  
-   **XmlNamedNodeMap**  
  
-   **XmlNodeList**  
  
-   **XmlNodeChangedEventArgs**  
  
 Il **XmlImplementation** classe viene utilizzata per creare un documento XML. Per ulteriori informazioni, vedere [creazione di documenti XML](../../../../docs/standard/data/xml/xml-document-creation.md).  
  
 Il **XmlNamedNodeMap** classe gestisce un set di nodi non ordinato. Per ulteriori informazioni, vedere [il recupero di nodi non ordinati per nome o indice](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).  
  
 Il **XmlNodeList** classe gestisce un elenco ordinato di nodi. Per ulteriori informazioni, vedere [recupero di nodi ordinati in base all'indice](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).  
  
 Il **XmlNodeChangedEventArgs** classe gestisce i gestori eventi registrati il **XmlDocument**. Per ulteriori informazioni, vedere [gestione degli eventi in un documento XML con XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).  
  
 Il **XmlLinkedNode** classe eredita da **XmlNode**. Lo scopo consiste nell'eseguire l'override di due metodi di **XmlNode**: il **PreviousSibling** e **NextSibling** metodi. Questi metodi sottoposti a override vengono quindi ereditati e utilizzati da **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, e **XmlProcessingInstruction**, che sono classi di elementi di pari livello precedenti e successivi.  
  
## <a name="see-also"></a>Vedere anche  
 [XML Document Object Model (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
