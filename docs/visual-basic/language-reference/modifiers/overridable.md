---
title: Overridable (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Overridable
- vb.Overridable
helpviewer_keywords:
- elements [Visual Basic], concrete
- properties [Visual Basic], redefining
- overriding, Overridable keyword
- elements [Visual Basic], virtual
- virtual [elements VB]
- procedures [Visual Basic], overriding
- concrete [elements VB]
- procedures [Visual Basic], redefining
- Overridable keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
ms.openlocfilehash: 91a1cedc66fd66e336b6e7976ad87ad638cb43c3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816881"
---
# <a name="overridable-visual-basic"></a>Overridable (Visual Basic)
Specifica che una proprietà o routine può essere sostituita da una proprietà con nome identico o routine in una classe derivata.  
  
## <a name="remarks"></a>Note  
 Il `Overridable` modificatore consente a una proprietà o metodo in una classe per eseguire l'override in una classe derivata. Il [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modificatore impedisce una proprietà o metodo da sottoporre a override in una classe derivata.  Per altre informazioni, vedere [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Se il `Overridable` o `NotOverridable` modificatore non è specificato, l'impostazione predefinita dipende dal fatto che la proprietà o il metodo esegue l'override di una proprietà della classe base o un metodo. Se la proprietà o il metodo esegue l'override di una proprietà della classe base o un metodo, l'impostazione predefinita è `Overridable`; in caso contrario, è `NotOverridable`.  
  
 È possibile nascondere o sottoporre a override per ridefinire un elemento ereditato, ma esistono differenze significative tra i due approcci. Per altre informazioni, vedere [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
 Un elemento che può essere sottoposto a override è talvolta detta un *virtuale* elemento. Se è possibile eseguire l'override, ma non deve essere, detto a volte anche un *concreta* elemento.  
  
 È possibile usare `Overridable` solo in un'istruzione per la dichiarazione di proprietà o routine.  
  
## <a name="combined-modifiers"></a>Modificatori combinati  
 Non è possibile specificare `Overridable` oppure `NotOverridable` per un `Private` (metodo).  
  
 Non è possibile specificare `Overridable` assieme `MustOverride`, `NotOverridable`, o `Shared` nella stessa dichiarazione.  
  
 Poiché un elemento che esegue l'override può essere implicitamente sottoposto a override, non è possibile combinare `Overridable` e `Overrides`.  
  
## <a name="usage"></a>Utilizzo  
 Il modificatore `Overridable` può essere usato nei contesti seguenti:  
  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Modificatori](../../../visual-basic/language-reference/modifiers/index.md)
- [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
- [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
