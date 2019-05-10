---
title: Accesso di membro condiviso tramite un'istanza; l'espressione di qualificazione non verrà valutata
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 311f4c025072162e0cfb6b87587f8602d33fcd19
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64646874"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Accesso di membro condiviso tramite un'istanza; l'espressione di qualificazione non verrà valutata
Una variabile di istanza di una classe o struttura viene usata per accedere a un `Shared` variabile, proprietà, routine o evento definito in quella classe o struttura. Questo avviso può verificarsi anche se una variabile di istanza viene utilizzata per accedere a un membro condiviso in modo implicito di una classe o struttura, ad esempio una costante o enumerazione, o una classe annidata o una struttura.  
  
 Lo scopo della condivisione di un membro consiste nel creare una sola copia di tale membro e rendere disponibili per ogni istanza della classe o struttura in cui è dichiarata unica copia. È coerenza con lo scopo per accedere a un `Shared` membro tramite il nome della relativa classe o struttura, anziché tramite una variabile che contiene una singola istanza di quella classe o struttura.  
  
 L'accesso a un `Shared` membro tramite una variabile di istanza può rendere più difficile da comprendere nascondendo il fatto che il membro è il codice `Shared`. Inoltre, se tale accesso fa parte di un'espressione che esegue altre azioni, ad esempio un `Function` procedure che restituisce un'istanza del membro condiviso, Visual Basic consente di ignorare l'espressione e tutte le altre azioni che altrimenti verrebbero eseguite.  
  
 Per altre informazioni e un esempio, vedere [condiviso](../../../visual-basic/language-reference/modifiers/shared.md).  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42025  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Usare il nome della classe o struttura che definisca il `Shared` membro per accedervi, come illustrato nell'esempio seguente.  
  
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
>  Prestare particolare attenzione agli effetti dell'ambito quando due elementi di programmazione hanno lo stesso nome. Nell'esempio precedente, se si dichiara un'istanza usando `Dim testClass as testClass = Nothing`, il compilatore considera una chiamata a `testClass.sayHello()` non appena si verifica un accesso al metodo tramite il nome della classe e alcun messaggio di avviso.  
  
## <a name="see-also"></a>Vedere anche

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Scope in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
