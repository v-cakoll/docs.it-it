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
ms.openlocfilehash: 463dd2454aafebf11554fb7bacdb73724c3130d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392158"
---
# <a name="notoverridable-visual-basic"></a>NotOverridable (Visual Basic)
Specifica che una proprietà o una routine non può essere sottoposta a override in una classe derivata.  
  
## <a name="remarks"></a>Commenti  
 Il `NotOverridable` modificatore impedisce che una proprietà o un metodo venga sottoposto a override in una classe derivata.  Il modificatore [Overridable](overridable.md) consente di eseguire l'override di una proprietà o di un metodo in una classe in una classe derivata. Per altre informazioni, vedere [Nozioni fondamentali sull'ereditarietà](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Se il `Overridable` `NotOverridable` modificatore o non è specificato, l'impostazione predefinita dipende dalla proprietà o dal metodo che esegue l'override di una proprietà o di un metodo della classe base. Se la proprietà o il metodo esegue l'override di una proprietà o di un metodo della classe base, l'impostazione predefinita è `Overridable` ; in caso contrario, è `NotOverridable` .  
  
 Un elemento che non può essere sottoposto a override è talvolta denominato elemento *sealed* .  
  
 È possibile utilizzare `NotOverridable` solo in un'istruzione di dichiarazione di proprietà o di routine. È possibile specificare `NotOverridable` solo su una proprietà o una routine che esegue l'override di un'altra proprietà o routine, ovvero solo in combinazione con `Overrides` .  
  
## <a name="combined-modifiers"></a>Modificatori combinati  
 Non è possibile specificare `Overridable` o `NotOverridable` per un `Private` metodo.  
  
 Non è possibile specificare `NotOverridable` insieme a `MustOverride` , `Overridable` o `Shared` nella stessa dichiarazione.  
  
## <a name="usage"></a>Uso  
 Il modificatore `NotOverridable` può essere usato nei contesti seguenti:  
  
 [Istruzione Function](../statements/function-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Istruzione Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Modificatori](index.md)
- [Nozioni fondamentali sull'ereditarietà](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](mustoverride.md)
- [Overridable](overridable.md)
- [Override](overrides.md)
- [Parole chiave](../keywords/index.md)
- [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
