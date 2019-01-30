---
title: "'<keyword>' è valido solo all'interno di un metodo di istanza"
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: af3bc95e2db88577c7c53e4b58fb60aed8a83453
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267644"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a>'\<parola chiave >' è valido solo all'interno di un metodo di istanza
Il `Me`, `MyClass`, e `MyBase` parole chiave fanno riferimento alle istanze di classe specifica. È possibile utilizzarle all'interno di un oggetto condiviso `Function` o `Sub` procedure.  
  
 **ID errore:** BC30043  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Rimuovere la parola chiave dalla routine oppure rimuovere il `Shared` parola chiave dalla dichiarazione di routine.  
  
## <a name="see-also"></a>Vedere anche
- [Assegnazione di variabili oggetto](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase e MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
