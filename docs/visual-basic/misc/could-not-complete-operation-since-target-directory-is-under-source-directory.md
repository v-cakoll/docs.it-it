---
title: Impossibile completare l'operazione. La directory di destinazione è una sottodirectory della directory di origine
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 68217023a980891200c18b5536ef902574d36257
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>Impossibile completare l'operazione. La directory di destinazione è una sottodirectory della directory di origine
Un'operazione ciclica non è riuscita. Queste operazioni sono cicliche e quindi non possono essere completate. Ad esempio, un oggetto A potrebbe provare a ereditare dall'oggetto B, che a sua volta eredita dall'oggetto A.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Quando si eredita, assicurarsi che non siano presenti riferimenti ciclici.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di errore](../../visual-basic/programming-guide/language-features/error-types.md)  
 [Nozioni fondamentali di debug: i punti di interruzione](http://msdn.microsoft.com/library/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)
