---
title: Overridable
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
ms.openlocfilehash: dcbabde8464dd8a0ce5fad24d7d72b1e780270d3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392119"
---
# <a name="overridable-visual-basic"></a>Overridable (Visual Basic)
Specifica che una proprietà o una routine può essere sottoposta a override da una proprietà o una routine con nome identico in una classe derivata.  
  
## <a name="remarks"></a>Commenti  
 Il `Overridable` modificatore consente di eseguire l'override di una proprietà o di un metodo in una classe in una classe derivata. Il modificatore [NotOverridable](notoverridable.md) impedisce l'override di una proprietà o di un metodo in una classe derivata.  Per altre informazioni, vedere [Nozioni fondamentali sull'ereditarietà](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Se il `Overridable` `NotOverridable` modificatore o non è specificato, l'impostazione predefinita dipende dalla proprietà o dal metodo che esegue l'override di una proprietà o di un metodo della classe base. Se la proprietà o il metodo esegue l'override di una proprietà o di un metodo della classe base, l'impostazione predefinita è `Overridable` ; in caso contrario, è `NotOverridable` .  
  
 È possibile eseguire l'ombreggiatura o l'override per ridefinire un elemento ereditato, ma esistono differenze significative tra i due approcci. Per ulteriori informazioni, vedere [shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).  
  
 Un elemento di cui è possibile eseguire l'override viene talvolta definito come elemento *virtuale* . Se è possibile eseguirne l'override, ma non è necessario, viene talvolta chiamato anche elemento *concreto* .  
  
 È possibile utilizzare `Overridable` solo in un'istruzione di dichiarazione di proprietà o di routine.  
  
## <a name="combined-modifiers"></a>Modificatori combinati  
 Non è possibile specificare `Overridable` o `NotOverridable` per un `Private` metodo.  
  
 Non è possibile specificare `Overridable` insieme a `MustOverride` , `NotOverridable` o `Shared` nella stessa dichiarazione.  
  
 Poiché un elemento che esegue l'override può essere implicitamente sottoposto a override, non è possibile combinare `Overridable` e `Overrides`.  
  
## <a name="usage"></a>Uso  
 Il modificatore `Overridable` può essere usato nei contesti seguenti:  
  
 [Istruzione Function](../statements/function-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Istruzione Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Modificatori](index.md)
- [Nozioni fondamentali sull'ereditarietà](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](mustoverride.md)
- [NotOverridable](notoverridable.md)
- [Override](overrides.md)
- [Parole chiave](../keywords/index.md)
- [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
