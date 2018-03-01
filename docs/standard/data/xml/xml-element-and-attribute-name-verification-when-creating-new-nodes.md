---
title: Verifica dei nomi di elementi e di attributi XML durante la creazione di nuovi nodi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 36b9761cefb1dba47c88d053773c89e4312dee9d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a>Verifica dei nomi di elementi e di attributi XML durante la creazione di nuovi nodi
La validità dei nomi viene controllata dal modello DOM XML durante la creazione di nuovi nodi di elementi o di attributi. Se i nomi contengono caratteri non validi, verrà generata un'eccezione. Per garantire che i nomi siano validi e codificati correttamente, è necessario usare la classe **XmlConvert** per codificare il nome e decodificarlo nuovamente al livello dell'applicazione. **XmlWriter** dispone di metodi con cui vengono eseguite operazioni aggiuntive per garantire che venga generato un XML in formato corretto.  
  
## <a name="see-also"></a>Vedere anche  
 [Modello DOM (Document Object Mode) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
