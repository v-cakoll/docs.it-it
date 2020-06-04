---
title: "'<keyword>' è valido solo all'interno di un metodo di istanza"
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: 537689405ea30bdd7c075320eba58a8723a93cdb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397402"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a>'\<keyword>' è valido solo all'interno di un metodo di istanza
Le `Me` `MyClass` `MyBase` parole chiave, e si riferiscono a specifiche istanze di classe. Non è possibile usarli all'interno di una `Function` routine o condivisa `Sub` .  
  
 **ID errore:** BC30043  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Rimuovere la parola chiave dalla routine oppure rimuovere la `Shared` parola chiave dalla dichiarazione di routine.  
  
## <a name="see-also"></a>Vedere anche

- [Assegnazione di variabili oggetto](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase e MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Nozioni fondamentali sull'ereditarietà](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
