---
title: Impossibile applicare la risoluzione dell'overload con associazione tardiva a '<procedurename>' perché l'istanza di accesso è un tipo interfaccia
ms.date: 07/20/2015
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
ms.openlocfilehash: 4500a177c7a4729fe5131af1b007fd38e77afe07
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397337"
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-procedurename-because-the-accessing-instance-is-an-interface-type"></a>Impossibile applicare la risoluzione dell'overload con associazione tardiva a '\<procedurename>' perché l'istanza di accesso è un tipo interfaccia

Il compilatore sta provando a risolvere un riferimento a una proprietà o una routine di overload, ma il riferimento non riesce perché un argomento è di tipo `Object` e l'oggetto di riferimento ha il tipo di dati di un'interfaccia. L' `Object` argomento impone al compilatore di risolvere il riferimento come ad associazione tardiva.

In queste circostanze, il compilatore risolve l'overload tramite la classe di implementazione invece che tramite l'interfaccia sottostante. Se la classe Rinomina una delle versioni di overload, il compilatore non considera tale versione come un overload perché il nome è diverso. Ciò comporta a sua volta che il compilatore ignori la versione rinominata quando potrebbe essere stata la scelta corretta per risolvere il riferimento.

**ID errore:** BC30933

## <a name="to-correct-this-error"></a>Per correggere l'errore

- Utilizzare `CType` per eseguire il cast dell'argomento da `Object` al tipo specificato dalla firma dell'overload che si desidera chiamare.

  Si noti che non consente di eseguire il cast dell'oggetto di riferimento all'interfaccia sottostante. Per evitare questo errore, è necessario eseguire il cast dell'argomento.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata una chiamata a una routine di overload `Sub` che causa questo errore in fase di compilazione.

```vb
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

Nell'esempio precedente, se il compilatore consentiva la chiamata a `s1` come scritto, la risoluzione verrebbe eseguita tramite la classe `c1` anziché l'interfaccia `i1` . Ciò significa che il compilatore non prende in considerazione `s2` perché il nome è diverso in `c1` , anche se è la scelta corretta in base a quanto definito da `i1` .

È possibile correggere l'errore modificando la chiamata a una delle righe di codice seguenti:

```vb
refer.s1(CType(o1, Integer))
refer.s1(CType(o1, Double))
```

Ognuna delle righe precedenti di codice esegue esplicitamente il cast della `Object` variabile `o1` a uno dei tipi di parametro definiti per gli overload.

## <a name="see-also"></a>Vedere anche

- [Overload della routine](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [Risoluzione dell'overload](../../programming-guide/language-features/procedures/overload-resolution.md)
- [CType Function](../functions/ctype-function.md)
