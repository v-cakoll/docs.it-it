---
title: L'oggetto o la classe non supporta il set di eventi
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: be4b9140222ef969bfb836fd74f45b8f662360b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>L'oggetto o la classe non supporta il set di eventi
Si è tentato di utilizzare un `WithEvents` variabile con un componente che non può fungere da un'origine evento per il set specificato di eventi. Ad esempio, si desidera elaborare gli eventi di un oggetto, quindi creare un altro oggetto che `Implements` il primo oggetto. Sebbene si pensi che è stato possibile sink degli eventi dall'oggetto implementato, questo non è sempre il caso. `Implements`implementa solo un'interfaccia per i metodi e proprietà. `WithEvents`non è supportata per privato `UserControls`, perché le informazioni sul tipo necessarie generare il `ObjectEvent` non è disponibile in fase di esecuzione.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  È Impossibile sink di eventi per un componente che non sia l'origine eventi.  
  
## <a name="see-also"></a>Vedere anche  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)  
 [Istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
