---
title: MustOverride
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
ms.openlocfilehash: dc6a153a604fd0e5cee9d7d46ebcd63294f33628
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351488"
---
# <a name="mustoverride-visual-basic"></a>MustOverride (Visual Basic)
Specifica che una proprietà o una routine non è implementata in questa classe e deve essere sottoposta a override in una classe derivata prima di poter essere utilizzata.  
  
## <a name="remarks"></a>Osservazioni  
 È possibile utilizzare `MustOverride` solo in un'istruzione di dichiarazione di proprietà o di routine. La proprietà o la routine che specifica `MustOverride` deve essere un membro di una classe e la classe deve essere contrassegnata come [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).  
  
## <a name="rules"></a>Regole  
  
- **Dichiarazione incompleta.** Quando si specifica `MustOverride`, non vengono fornite righe di codice aggiuntive per la proprietà o la routine, non anche per l'istruzione `End Function`, `End Property`o `End Sub`.  
  
- **Modificatori combinati.** Non è possibile specificare `MustOverride` insieme `NotOverridable`, `Overridable`o `Shared` nella stessa dichiarazione.  
  
- **Shadowing e override.** Sebbene lo shadowing e l'override ridefiniscano entrambi un elemento ereditato, tra i due metodi esistono differenze sostanziali. Per ulteriori informazioni, vedere [shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
- **Termini alternativi.** Un elemento che non può essere utilizzato ad eccezione di un override viene talvolta denominato elemento *virtuale puro* .  
  
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
