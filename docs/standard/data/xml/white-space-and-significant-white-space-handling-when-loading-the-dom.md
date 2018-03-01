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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8a16f90b6d48bc2ffabfd678722fa9b6e61328cd
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a>Gestione degli spazi vuoti e degli spazi vuoti significativi durante il caricamento del DOM
Quando si carica il documento, è possibile impostare l'opzione che consente di conservare gli spazi e creare nodi **XmlWhitespace** nell'albero del documento. Per creare nodi con spazi, impostare la proprietà **PreserveWhitespace** su true. Se la proprietà è impostata su **false**, che rappresenta il valore predefinito, i nodi con spazi non vengono creati. I nodi con spazi significativi vengono sempre mantenuti e i nodi **XmlSignificantWhitespace** vengono sempre creati in memoria per rappresentare tali dati, indipendentemente dall'impostazione del flag **PreserveWhitespace**.  
  
 Se il documento viene caricato da un lettore, l'impostazione della proprietà del flag **PreserveWhitespace** nella classe **XmlDocument** incide sulla creazione dei nodi **XmlWhitespace** solo se la proprietà **WhitespaceHandling** di **XmlTextReader** non è impostata su **WhitespaceHandling.None**. Il valore della proprietà **WhitespaceHandling** nel lettore che ha la precedenza sull'impostazione del flag nella classe **XmlDocument**. Per altre informazioni su **XmlSignificantWhitespace**, vedere <xref:System.Xml.XmlSignificantWhitespace>.  
  
## <a name="see-also"></a>Vedere anche  
 [Modello DOM (Document Object Mode) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
