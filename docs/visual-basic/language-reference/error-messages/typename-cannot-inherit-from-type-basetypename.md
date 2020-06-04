---
title: "'<typename>' non può ereditare da <type> '<basetypename>' perché espande l'accesso del <type> base all'esterno dell'assembly"
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: aa04c558abbcc4259c2821cdcbdc1669b91ffee0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402772"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a>'\<typename>' non può ereditare da \<type> '\<basetypename>' perché espande l'accesso del \<type> base all'esterno dell'assembly
Una classe o interfaccia eredita da una classe o interfaccia di base ma ha un livello di accesso meno restrittivo.  
  
 Ad esempio, un' `Public` interfaccia eredita da un' `Friend` interfaccia o una `Protected` classe eredita da una `Private` classe. Questa operazione espone la classe o l'interfaccia di base per accedere oltre il livello previsto.  
  
 **ID errore:** BC30910  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Modificare il livello di accesso della classe o dell'interfaccia derivata in modo che sia almeno quanto restrittivo della classe base o dell'interfaccia.  
  
     -oppure-  
  
- Se è necessario il livello di accesso meno restrittivo, rimuovere l' `Inherits` istruzione. Non è possibile ereditare da una classe o un'interfaccia di base più limitata.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Class](../statements/class-statement.md)
- [Istruzione Interface](../statements/interface-statement.md)
- [Inherits Statement](../statements/inherits-statement.md)
- [Livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
