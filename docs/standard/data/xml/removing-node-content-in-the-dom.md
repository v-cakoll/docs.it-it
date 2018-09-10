---
title: Rimozione del contenuto di un nodo nel DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 737766586ee920a87c25dd42896bdfb14ae69d98
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44205218"
---
# <a name="removing-node-content-in-the-dom"></a>Rimozione del contenuto di un nodo nel DOM
Per i tipi di nodo che ereditano da <xref:System.Xml.XmlCharacterData>, ossia <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace> e <xref:System.Xml.XmlSignificantWhitespace>, è possibile rimuovere i caratteri usando il metodo <xref:System.Xml.XmlCharacterData.DeleteData%2A>, che consente di rimuovere una serie di caratteri dal nodo. Per rimuovere l'intero contenuto di un nodo, è necessario rimuovere il nodo stesso. Per mantenere il nodo, anche se il contenuto non è corretto, è necessario modificare il contenuto. Per informazioni sulla modifica del contenuto di un nodo, vedere [Modifica di nodi, contenuto e valori in un documento XML](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).  
  
## <a name="see-also"></a>Vedere anche

- [Modello DOM (Document Object Mode) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
