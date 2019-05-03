---
title: "'<keyword>' è valido solo all'interno di un metodo di istanza"
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: 5ff82b932f9bea4c7fd087651e34277ef94bc27c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946640"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a>'\<parola chiave >' è valido solo all'interno di un metodo di istanza
Il `Me`, `MyClass`, e `MyBase` parole chiave fanno riferimento alle istanze di classe specifica. È possibile utilizzarle all'interno di un oggetto condiviso `Function` o `Sub` procedure.  
  
 **ID errore:** BC30043  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Rimuovere la parola chiave dalla routine oppure rimuovere il `Shared` parola chiave dalla dichiarazione di routine.  
  
## <a name="see-also"></a>Vedere anche

- [Assegnazione di variabili oggetto](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase e MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
