---
title: NotOverridable
ms.date: 07/20/2015
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
ms.openlocfilehash: c55d57bb3008b2825fe5382844908ea32f0d500c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351454"
---
# <a name="notoverridable-visual-basic"></a>NotOverridable (Visual Basic)
Specifica che una proprietà o una routine non può essere sottoposta a override in una classe derivata.  
  
## <a name="remarks"></a>Note  
 Il modificatore `NotOverridable` impedisce l'override di una proprietà o di un metodo in una classe derivata.  Il modificatore [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) consente di eseguire l'override di una proprietà o di un metodo in una classe in una classe derivata. Per altre informazioni, vedere [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Se il modificatore `Overridable` o `NotOverridable` non è specificato, l'impostazione predefinita dipende dalla proprietà o dal metodo che esegue l'override di una proprietà o di un metodo della classe base. Se la proprietà o il metodo esegue l'override di una proprietà o di un metodo della classe base, l'impostazione predefinita è `Overridable`; in caso contrario, viene `NotOverridable`.  
  
 Un elemento che non può essere sottoposto a override è talvolta denominato elemento *sealed* .  
  
 È possibile utilizzare `NotOverridable` solo in un'istruzione di dichiarazione di proprietà o di routine. È possibile specificare `NotOverridable` solo in una proprietà o una routine che esegue l'override di un'altra proprietà o routine, ovvero solo in combinazione con `Overrides`.  
  
## <a name="combined-modifiers"></a>Modificatori combinati  
 Non è possibile specificare `Overridable` o `NotOverridable` per un metodo di `Private`.  
  
 Non è possibile specificare `NotOverridable` insieme `MustOverride`, `Overridable`o `Shared` nella stessa dichiarazione.  
  
## <a name="usage"></a>Utilizzo  
 Il modificatore `NotOverridable` può essere usato nei contesti seguenti:  
  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Modificatori](../../../visual-basic/language-reference/modifiers/index.md)
- [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
- [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
