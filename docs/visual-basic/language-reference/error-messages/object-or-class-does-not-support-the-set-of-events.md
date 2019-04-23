---
title: L'oggetto o la classe non supporta il set di eventi
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: ad9176b5332a75f03968e742501c3fce541055de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342882"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>L'oggetto o la classe non supporta il set di eventi
Si è provato a usare un `WithEvents` variabile con un componente che non può fungere da un'origine evento per il set specificato di eventi. Ad esempio, si voleva il sink degli eventi di un oggetto, quindi creare un altro oggetto che `Implements` il primo oggetto. Anche se si potrebbe pensare che è possibile effettuare il sink gli eventi dall'oggetto implementato, questo non è sempre il caso. `Implements` implementa solo un'interfaccia per i metodi e proprietà. `WithEvents` non è supportata per privati `UserControls`, perché le informazioni sul tipo necessarie generare il `ObjectEvent` non è disponibile in fase di esecuzione.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. È possibile effettuare il sink degli eventi per un componente che non sia l'origine eventi.  
  
## <a name="see-also"></a>Vedere anche

- [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
- [Istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
