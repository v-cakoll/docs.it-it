---
title: "'<typename>' non può ereditare da <type> '<basetypename>' perché espande l'accesso del <type> base all'esterno dell'assembly"
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: dc979a66c73fdf15a4349a003680156e0ce27ed3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61764361"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a>'\<nomeTipo >' non può ereditare \<tipo > '\<nomeTipoBase >' perché espande l'accesso della base \<tipo > all'esterno dell'assembly
Una classe o interfaccia eredita da una classe di base o interfaccia ma ha un livello di accesso meno restrittivo.  
  
 Ad esempio, un `Public` interfaccia eredita da un `Friend` interfaccia o una `Protected` classe eredita da un `Private` classe. Ciò espone la classe di base o l'interfaccia per accedere a oltre il livello desiderato.  
  
 **ID errore:** BC30910  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Modificare il livello di accesso della classe derivata o dell'interfaccia sia restrittiva almeno quanto quella della classe di base o dell'interfaccia.  
  
     -oppure-  
  
- Se è necessario il livello di accesso meno restrittivo, rimuovere il `Inherits` istruzione. È possibile ereditare da una classe di base con maggiori restrizioni o un'interfaccia.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
