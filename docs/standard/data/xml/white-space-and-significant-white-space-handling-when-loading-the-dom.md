---
title: Gestione degli spazi vuoti e degli spazi vuoti significativi durante il caricamento del DOM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 82401a18132801f9aa5368832b96be3cb67a8642
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a>Gestione degli spazi vuoti e degli spazi vuoti significativi durante il caricamento del DOM
Quando si carica il documento, è possibile impostare l'opzione per mantenere gli spazi vuoti e creare **XmlWhitespace** nodi nell'albero del documento. Per creare nodi con spazi vuoti, impostare il **PreserveWhitespace** proprietà su true. Se la proprietà è impostata su **false**, ovvero l'impostazione predefinita, i nodi spazi vuoti non vengono creati. I nodi spazi vuoti significativi vengono sempre conservati e **XmlSignificantWhitespace** nodi vengono sempre creati in memoria per rappresentare i dati, indipendentemente dall'impostazione del **PreserveWhitespace** flag.  
  
 Se il documento viene caricato da un lettore, l'impostazione del **PreserveWhitespace** flag di proprietà di **XmlDocument** classe influisce sulla creazione di **XmlWhitespace** nodi solo quando il **WhitespaceHandling** proprietà il **XmlTextReader** non è impostata su **WhitespaceHandling**. È il valore della **WhitespaceHandling** il lettore ha la precedenza sull'impostazione del flag nella proprietà di **XmlDocument**. Per ulteriori informazioni su **XmlSignificantWhitespace**, vedere <xref:System.Xml.XmlSignificantWhitespace>.  
  
## <a name="see-also"></a>Vedere anche  
 [XML Document Object Model (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
