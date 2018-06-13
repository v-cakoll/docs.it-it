---
title: L'oggetto o la classe non supporta il set di eventi
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: 4a6f1f59f43cdb351d49fbcbfd18362db888586e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593204"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>L'oggetto o la classe non supporta il set di eventi
Si è tentato di utilizzare un `WithEvents` variabile con un componente che non può fungere da un'origine evento per il set specificato di eventi. Ad esempio, si desidera elaborare gli eventi di un oggetto, quindi creare un altro oggetto che `Implements` il primo oggetto. Sebbene si pensi che è stato possibile sink degli eventi dall'oggetto implementato, questo non è sempre il caso. `Implements` implementa solo un'interfaccia per i metodi e proprietà. `WithEvents` non è supportata per private `UserControls`, perché le informazioni sul tipo necessarie generare il `ObjectEvent` non è disponibile in fase di esecuzione.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  È Impossibile sink di eventi per un componente che non sia l'origine eventi.  
  
## <a name="see-also"></a>Vedere anche  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)  
 [Istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
