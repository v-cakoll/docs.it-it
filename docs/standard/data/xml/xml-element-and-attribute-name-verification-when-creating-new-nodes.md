---
title: Verifica dei nomi di elementi e di attributi XML durante la creazione di nuovi nodi
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de11c190310dec90bd23d044f77d0c38e3a34fcf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568849"
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a>Verifica dei nomi di elementi e di attributi XML durante la creazione di nuovi nodi
La validità dei nomi viene controllata dal modello DOM XML durante la creazione di nuovi nodi di elementi o di attributi. Se i nomi contengono caratteri non validi, verrà generata un'eccezione. Per garantire che i nomi siano validi e codificati correttamente, è necessario usare la classe **XmlConvert** per codificare il nome e decodificarlo nuovamente al livello dell'applicazione. **XmlWriter** dispone di metodi con cui vengono eseguite operazioni aggiuntive per garantire che venga generato un XML in formato corretto.  
  
## <a name="see-also"></a>Vedere anche  
 [Modello DOM (Document Object Mode) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
