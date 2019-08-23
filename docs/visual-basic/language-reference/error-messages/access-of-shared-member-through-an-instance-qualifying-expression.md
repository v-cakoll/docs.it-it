---
title: Accesso di membro condiviso tramite un'istanza; l'espressione di qualificazione non verrà valutata
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 3174d463744303e8c90ed0b2e1a4d86ed08fbcfb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947704"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Accesso di membro condiviso tramite un'istanza; l'espressione di qualificazione non verrà valutata
Una variabile di istanza di una classe o struttura viene utilizzata per accedere `Shared` a una variabile, una proprietà, una routine o un evento definito in tale classe o struttura. Questo avviso può verificarsi anche se viene usata una variabile di istanza per accedere a un membro implicitamente condiviso di una classe o di una struttura, ad esempio una costante o un'enumerazione, oppure una classe o una struttura annidata.  
  
 Lo scopo della condivisione di un membro consiste nel creare una sola copia di tale membro e renderla disponibile per ogni istanza della classe o della struttura in cui è dichiarata. È coerente con questo scopo per accedere a un `Shared` membro tramite il nome della relativa classe o struttura, anziché tramite una variabile che include una singola istanza della classe o della struttura.  
  
 L'accesso a `Shared` un membro tramite una variabile di istanza può rendere il codice più difficile da comprendere nascondendo il fatto che il membro `Shared`è. Inoltre, se tale accesso è parte di un'espressione che esegue altre azioni, ad esempio una `Function` routine che restituisce un'istanza del membro condiviso, Visual Basic ignora l'espressione e qualsiasi altra azione che altrimenti verrebbe eseguita.  
  
 Per ulteriori informazioni e un esempio, vedere [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42025  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Usare il nome della classe o della struttura che definisce il `Shared` membro per accedervi, come illustrato nell'esempio seguente.  
  
```vb  
Public Class testClass  
    Public Shared Sub sayHello()  
        MsgBox("Hello")  
    End Sub  
End Class  
  
Module testModule  
    Public Sub Main()  
        ' Access a shared method through an instance variable.  
        ' This generates a warning.  
        Dim tc As New testClass  
        tc.sayHello()  
  
        ' Access a shared method by using the class name.  
        ' This does not generate a warning.  
        testClass.sayHello()  
    End Sub  
End Module  
```  
  
> [!NOTE]
> Ricevere un avviso per gli effetti dell'ambito quando due elementi di programmazione hanno lo stesso nome. Nell'esempio precedente, se si dichiara un'istanza usando `Dim testClass as testClass = Nothing`, il compilatore considera una chiamata a `testClass.sayHello()` come accesso del metodo tramite il nome della classe e non viene generato alcun avviso.  
  
## <a name="see-also"></a>Vedere anche

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Ambito in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
