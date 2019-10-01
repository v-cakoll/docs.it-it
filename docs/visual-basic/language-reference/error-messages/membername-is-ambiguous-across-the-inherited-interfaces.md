---
title: "'<membername>' è ambiguo nelle interfacce ereditate '<interfacename1>' e '<interfacename2>'"
ms.date: 07/20/2015
f1_keywords:
- vbc30685
- bc30685
helpviewer_keywords:
- BC30685
ms.assetid: 756add7a-23d5-4b4f-a48d-8297d6459c73
ms.openlocfilehash: 06e0d8863c74041f81977b3187fe99a1d05bcd53
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700890"
---
# <a name="membername-is-ambiguous-across-the-inherited-interfaces-interfacename1-and-interfacename2"></a>' \<membername >' è ambiguo tra le interfacce ereditate ' \<interfacename1 >' è \<interfacename2 >'
L'interfaccia eredita due o più membri con lo stesso nome da più interfacce.  
  
 **ID errore:** BC30685  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Eseguire il cast del valore all'interfaccia di base che si desidera utilizzare. Per esempio:  
  
    ```vb  
    Interface Left  
        Sub MySub()  
    End Interface  
  
    Interface Right  
        Sub MySub()  
    End Interface  
  
    Interface LeftRight  
        Inherits Left, Right  
    End Interface  
  
    Module test  
        Sub Main()  
            Dim x As LeftRight  
            ' x.MySub()  'x is ambiguous.  
            CType(x, Left).MySub() ' Cast to base type.  
            CType(x, Right).MySub() ' Call the other base type.  
        End Sub  
    End Module  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
