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
ms.openlocfilehash: 1b20108a2d42e82c0af7598fde8d60a08fea28ec
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396194"
---
# <a name="mustoverride-visual-basic"></a>MustOverride (Visual Basic)
Specifica che una proprietà o una routine non è implementata in questa classe e deve essere sottoposta a override in una classe derivata prima di poter essere utilizzata.  
  
## <a name="remarks"></a>Commenti  
 È possibile utilizzare `MustOverride` solo in un'istruzione di dichiarazione di proprietà o di routine. La proprietà o la routine che specifica `MustOverride` deve essere un membro di una classe e la classe deve essere contrassegnata come [MustInherit](mustinherit.md).  
  
## <a name="rules"></a>Regole  
  
- **Dichiarazione incompleta.** Quando si specifica `MustOverride` , non vengono fornite righe di codice aggiuntive per la proprietà o la routine, non anche per l' `End Function` `End Property` istruzione, o `End Sub` .  
  
- **Modificatori combinati.** Non è possibile specificare `MustOverride` insieme a `NotOverridable` , `Overridable` o `Shared` nella stessa dichiarazione.  
  
- **Shadowing e override.** Sebbene lo shadowing e l'override ridefiniscano entrambi un elemento ereditato, tra i due metodi esistono differenze sostanziali. Per ulteriori informazioni, vedere [shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).  
  
- **Termini alternativi.** Un elemento che non può essere utilizzato ad eccezione di un override viene talvolta denominato elemento *virtuale puro* .  
  
 Il modificatore `MustOverride` può essere usato nei contesti seguenti:  
  
 [Istruzione Function](../statements/function-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Istruzione Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [NotOverridable](notoverridable.md)
- [Overridable](overridable.md)
- [Override](overrides.md)
- [MustInherit](mustinherit.md)
- [Parole chiave](../keywords/index.md)
- [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
