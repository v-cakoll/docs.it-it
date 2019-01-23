---
title: "&#39;&lt;TypeName&gt; &#39; non può ereditare da &lt;tipo&gt; &#39; &lt;nomeTipoBase&gt; &#39; perché espande l'accesso della base &lt;tipo&gt; all'esterno dell'assembly"
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 108025132bdd0fa86df5ed142aaa39c7b7e18062
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556483"
---
# <a name="39lttypenamegt39-cannot-inherit-from-lttypegt-39ltbasetypenamegt39-because-it-expands-the-access-of-the-base-lttypegt-outside-the-assembly"></a>&#39;&lt;TypeName&gt; &#39; non può ereditare da &lt;tipo&gt; &#39; &lt;nomeTipoBase&gt; &#39; perché espande l'accesso della base &lt;tipo&gt; all'esterno dell'assembly
Una classe o interfaccia eredita da una classe di base o interfaccia ma ha un livello di accesso meno restrittivo.  
  
 Ad esempio, un `Public` interfaccia eredita da un `Friend` interfaccia o una `Protected` classe eredita da un `Private` classe. Ciò espone la classe di base o l'interfaccia per accedere a oltre il livello desiderato.  
  
 **ID errore:** BC30910  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Modificare il livello di accesso della classe derivata o dell'interfaccia sia restrittiva almeno quanto quella della classe di base o dell'interfaccia.  
  
     -oppure-  
  
-   Se è necessario il livello di accesso meno restrittivo, rimuovere il `Inherits` istruzione. È possibile ereditare da una classe di base con maggiori restrizioni o un'interfaccia.  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
