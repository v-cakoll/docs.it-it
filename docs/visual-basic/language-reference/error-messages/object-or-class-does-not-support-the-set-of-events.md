---
title: L'oggetto o la classe non supporta il set di eventi
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: bc75e031c2d05bea3aa64774a9d3817756e51e8b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409361"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>L'oggetto o la classe non supporta il set di eventi
Si è provato a usare una `WithEvents` variabile con un componente che non può funzionare come origine evento per il set di eventi specificato. Si desidera, ad esempio, affondare gli eventi di un oggetto, quindi creare un altro oggetto che `Implements` il primo oggetto. Sebbene si possa pensare che è possibile affondare gli eventi dall'oggetto implementato, questo non è sempre il caso. `Implements`implementa solo un'interfaccia per metodi e proprietà. `WithEvents`non è supportato per private `UserControls` , perché le informazioni sul tipo necessarie per generare l'oggetto `ObjectEvent` non sono disponibili in fase di esecuzione.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Non è possibile eseguire il sink di eventi per un componente che non è un evento di origine.  
  
## <a name="see-also"></a>Vedere anche

- [WithEvents](../modifiers/withevents.md)
- [Istruzione Implements](../statements/implements-statement.md)
