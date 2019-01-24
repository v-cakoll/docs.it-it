---
title: MustOverride (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.MustOverride
- MustOverride
helpviewer_keywords:
- virtual elements [Visual Basic], pure
- elements [Visual Basic], pure virtual
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- overriding, MustOverride keyword
- procedures [Visual Basic], redefining
- pure virtual elements [Visual Basic]
- MustOverride keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
ms.openlocfilehash: fedebf3ee791fbab02ace2ba2dc121590a241c53
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627330"
---
# <a name="mustoverride-visual-basic"></a>MustOverride (Visual Basic)
Specifica che una proprietà o routine non è implementato in questa classe e deve essere sottoposto a override in una classe derivata prima che possa essere utilizzato.  
  
## <a name="remarks"></a>Note  
 È possibile usare `MustOverride` solo in un'istruzione per la dichiarazione di proprietà o routine. La proprietà o una routine che specifica `MustOverride` deve essere un membro di una classe, mentre la classe deve essere contrassegnata [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).  
  
## <a name="rules"></a>Regole  
  
-   **Dichiarazione di non completata.** Quando si specifica `MustOverride`, non si specifica una riga di codice per la proprietà o routine, non ancora il `End Function`, `End Property`, o `End Sub` istruzione.  
  
-   **Modificatori combinati.** Non è possibile specificare `MustOverride` assieme `NotOverridable`, `Overridable`, o `Shared` nella stessa dichiarazione.  
  
-   **Shadowing e override.** Sebbene lo shadowing e l'override ridefiniscano entrambi un elemento ereditato, tra i due metodi esistono differenze sostanziali. Per altre informazioni, vedere [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
-   **Condizioni di alternative.** Un elemento che può essere utilizzato solo in un override viene chiamato talvolta un *pure virtuale* elemento.  
  
 Il modificatore `MustOverride` può essere usato nei contesti seguenti:  
  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
- [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
