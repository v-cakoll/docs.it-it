---
title: Accesso di membro condiviso tramite un'istanza; l'espressione di qualificazione non verrà valutata
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 773a97c301e7cb5bec0234ae466d487ec9716437
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250344"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Accesso di membro condiviso tramite un'istanza; l'espressione di qualificazione non verrà valutata

Una variabile di istanza di una classe o struttura viene utilizzata per accedere a una variabile @no__t 0, una proprietà, una routine o un evento definito nella classe o nella struttura. Questo avviso può verificarsi anche se viene usata una variabile di istanza per accedere a un membro implicitamente condiviso di una classe o di una struttura, ad esempio una costante o un'enumerazione, oppure una classe o una struttura annidata.

Lo scopo della condivisione di un membro consiste nel creare una sola copia di tale membro e renderla disponibile per ogni istanza della classe o della struttura in cui è dichiarata. È coerente con questo scopo per accedere a un membro `Shared` tramite il nome della relativa classe o struttura, anziché tramite una variabile che include una singola istanza della classe o della struttura.

L'accesso a un membro `Shared` tramite una variabile di istanza può rendere il codice più difficile da comprendere nascondendo il fatto che il membro è `Shared`. Inoltre, se tale accesso è parte di un'espressione che esegue altre azioni, ad esempio una routine `Function` che restituisce un'istanza del membro condiviso, Visual Basic ignora l'espressione e qualsiasi altra azione che altrimenti verrebbe eseguita.  
  
Per ulteriori informazioni e un esempio, vedere [Shared](../modifiers/shared.md).  
  
Per impostazione predefinita, si tratta di un messaggio di avviso. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
**ID errore:** BC42025  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
Usare il nome della classe o della struttura che definisce il membro `Shared` per accedervi, come illustrato nell'esempio seguente:
  
```vb
Public Class TestClass
    Public Shared Sub SayHello()
        MsgBox("Hello")
    End Sub
End Class
  
Module Program
    Public Sub Main()  
        ' Access a shared method through an instance variable.  
        ' This generates a warning.  
        Dim tc As New TestClass()
        tc.SayHello()
  
        ' Access a shared method by using the class name.  
        ' This does not generate a warning.  
        TestClass.SayHello()
    End Sub  
End Module  
```  
  
> [!NOTE]
> Ricevere un avviso per gli effetti dell'ambito quando due elementi di programmazione hanno lo stesso nome. Nell'esempio precedente, se si dichiara un'istanza di usando `Dim testClass as testClass = Nothing`, il compilatore considera una chiamata a `testClass.sayHello()` come accesso del metodo tramite il nome della classe e non viene generato alcun avviso.
  
## <a name="see-also"></a>Vedere anche

- [Shared](../modifiers/shared.md)
- [Ambito in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md)
