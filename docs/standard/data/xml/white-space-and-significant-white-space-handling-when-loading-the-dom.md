---
title: Gestione degli spazi vuoti e degli spazi vuoti significativi durante il caricamento del DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
ms.openlocfilehash: 520d965737b82fda082aa44029f2a4042d948deb
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281773"
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a>Gestione degli spazi vuoti e degli spazi vuoti significativi durante il caricamento del DOM
Quando si carica il documento, è possibile impostare l'opzione che consente di conservare gli spazi e creare nodi **XmlWhitespace** nell'albero del documento. Per creare nodi con spazi, impostare la proprietà **PreserveWhitespace** su true. Se la proprietà è impostata su **false**, che rappresenta il valore predefinito, i nodi con spazi non vengono creati. I nodi con spazi significativi vengono sempre mantenuti e i nodi **XmlSignificantWhitespace** vengono sempre creati in memoria per rappresentare tali dati, indipendentemente dall'impostazione del flag **PreserveWhitespace**.  
  
 Se il documento viene caricato da un lettore, l'impostazione della proprietà del flag **PreserveWhitespace** nella classe **XmlDocument** incide sulla creazione dei nodi **XmlWhitespace** solo se la proprietà **WhitespaceHandling** di **XmlTextReader** non è impostata su **WhitespaceHandling.None**. Il valore della proprietà **WhitespaceHandling** nel lettore che ha la precedenza sull'impostazione del flag nella classe **XmlDocument**. Per altre informazioni su **XmlSignificantWhitespace**, vedere <xref:System.Xml.XmlSignificantWhitespace>.  
  
## <a name="see-also"></a>Vedere anche

- [XML DOM (Document Object Model)](xml-document-object-model-dom.md)
