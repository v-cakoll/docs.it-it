---
title: Risoluzione dell'overload con associazione tardiva non è possibile applicare a &#39; &lt;nomeroutine&gt; &#39; perché l'istanza di accesso è un tipo di interfaccia
ms.date: 07/20/2015
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
ms.openlocfilehash: e41cbf30f06547ef39553e31542e4e8b6df49a3b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589880"
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-39ltprocedurenamegt39-because-the-accessing-instance-is-an-interface-type"></a>Risoluzione dell'overload con associazione tardiva non è possibile applicare a &#39; &lt;nomeroutine&gt; &#39; perché l'istanza di accesso è un tipo di interfaccia
Il compilatore sta provando a risolvere un riferimento a una proprietà di overload o una routine, ma il riferimento non riesce perché è un argomento di tipo `Object` e l'oggetto che fa riferimento il tipo di dati di un'interfaccia. Il `Object` argomento induce il compilatore per risolvere il riferimento come ad associazione tardiva.  
  
 In questi casi, il compilatore risolve l'overload tramite la classe di implementazione anziché tramite l'interfaccia sottostante. Se la classe rinomina una delle versioni di overload, il compilatore non considera tale versione di overload perché il nome è diverso. Questo causa a sua volta al compilatore di ignorare la versione rinominata quando sarebbe stato la scelta corretta per risolvere il riferimento.  
  
 **ID errore:** BC30933  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Utilizzare `CType` per eseguire il cast dell'argomento da `Object` al tipo specificato per la firma di overload da chiamare.  
  
     Si noti che non consentono il cast dell'oggetto che fa riferimento all'interfaccia sottostante. È necessario eseguire il cast dell'argomento per evitare questo errore.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una chiamata a un overload `Sub` procedure che genera questo errore in fase di compilazione.  
  
```  
Module m1  
    Interface i1  
        Sub s1(ByVal p1 As Integer)  
        Sub s1(ByVal p1 As Double)  
    End Interface  
    Class c1  
        Implements i1  
        Public Overloads Sub s1(ByVal p1 As Integer) Implements i1.s1  
        End Sub  
        Public Overloads Sub s2(ByVal p1 As Double) Implements i1.s1  
        End Sub  
    End Class  
    Sub Main()  
        Dim refer As i1 = New c1  
        Dim o1 As Object = 3.1415  
        ' The following reference is INVALID and causes a compiler error.  
        refer.s1(o1)   
    End Sub  
End Module  
```  
  
 Nell'esempio precedente, se il compilatore ha consentito la chiamata a `s1` quanto scritto, la risoluzione verrà eseguita tramite la classe `c1` anziché l'interfaccia `i1`. Ciò significa che il compilatore non considerare `s2` perché il nome è diverso in `c1`, anche se è la scelta corretta, come definito da `i1`.  
  
 È possibile correggere l'errore modificando la chiamata a una delle righe di codice seguente:  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 Ognuna delle righe di codice precedenti esegue il cast in modo esplicito il `Object` variabile `o1` a uno dei tipi di parametro definiti per gli overload.  
  
## <a name="see-also"></a>Vedere anche  
 [Overload della routine](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [Risoluzione dell'overload](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)  
 [Funzione CType](../../../visual-basic/language-reference/functions/ctype-function.md)
