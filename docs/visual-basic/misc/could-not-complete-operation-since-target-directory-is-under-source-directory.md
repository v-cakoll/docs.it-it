---
title: Impossibile completare l'operazione. La directory di destinazione è una sottodirectory della directory di origine
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 46ec7ae452d4f8259d0f8ca3a896d1b29151ed61
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84376742"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>Impossibile completare l'operazione. La directory di destinazione è una sottodirectory della directory di origine
Un'operazione ciclica non è riuscita. Queste operazioni sono cicliche e quindi non possono essere completate. Ad esempio, un oggetto A potrebbe provare a ereditare dall'oggetto B, che a sua volta eredita dall'oggetto A.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Quando si eredita, assicurarsi che non siano presenti riferimenti ciclici.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di errore](../programming-guide/language-features/error-types.md)
- [Usare i punti di interruzione nel debugger di Visual Studio](/visualstudio/debugger/using-breakpoints)
