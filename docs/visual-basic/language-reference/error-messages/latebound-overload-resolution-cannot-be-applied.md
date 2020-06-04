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
# <a name="latebound-overload-resolution-cannot-be-applied-to-procedurename-because-the-accessing-instance-is-an-interface-type"></a><span data-ttu-id="7eee4-102">Impossibile applicare la risoluzione dell'overload con associazione tardiva a '\<procedurename>' perché l'istanza di accesso è un tipo interfaccia</span><span class="sxs-lookup"><span data-stu-id="7eee4-102">Latebound overload resolution cannot be applied to '\<procedurename>' because the accessing instance is an interface type</span></span>

<span data-ttu-id="7eee4-103">Il compilatore sta provando a risolvere un riferimento a una proprietà o una routine di overload, ma il riferimento non riesce perché un argomento è di tipo `Object` e l'oggetto di riferimento ha il tipo di dati di un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7eee4-103">The compiler is attempting to resolve a reference to an overloaded property or procedure, but the reference fails because an argument is of type `Object` and the referring object has the data type of an interface.</span></span> <span data-ttu-id="7eee4-104">L' `Object` argomento impone al compilatore di risolvere il riferimento come ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="7eee4-104">The `Object` argument forces the compiler to resolve the reference as late-bound.</span></span>

<span data-ttu-id="7eee4-105">In queste circostanze, il compilatore risolve l'overload tramite la classe di implementazione invece che tramite l'interfaccia sottostante.</span><span class="sxs-lookup"><span data-stu-id="7eee4-105">In these circumstances, the compiler resolves the overload through the implementing class instead of through the underlying interface.</span></span> <span data-ttu-id="7eee4-106">Se la classe Rinomina una delle versioni di overload, il compilatore non considera tale versione come un overload perché il nome è diverso.</span><span class="sxs-lookup"><span data-stu-id="7eee4-106">If the class renames one of the overloaded versions, the compiler does not consider that version to be an overload because its name is different.</span></span> <span data-ttu-id="7eee4-107">Ciò comporta a sua volta che il compilatore ignori la versione rinominata quando potrebbe essere stata la scelta corretta per risolvere il riferimento.</span><span class="sxs-lookup"><span data-stu-id="7eee4-107">This in turn causes the compiler to ignore the renamed version when it might have been the correct choice to resolve the reference.</span></span>

<span data-ttu-id="7eee4-108">**ID errore:** BC30933</span><span class="sxs-lookup"><span data-stu-id="7eee4-108">**Error ID:** BC30933</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="7eee4-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="7eee4-109">To correct this error</span></span>

- <span data-ttu-id="7eee4-110">Utilizzare `CType` per eseguire il cast dell'argomento da `Object` al tipo specificato dalla firma dell'overload che si desidera chiamare.</span><span class="sxs-lookup"><span data-stu-id="7eee4-110">Use `CType` to cast the argument from `Object` to the type specified by the signature of the overload you want to call.</span></span>

  <span data-ttu-id="7eee4-111">Si noti che non consente di eseguire il cast dell'oggetto di riferimento all'interfaccia sottostante.</span><span class="sxs-lookup"><span data-stu-id="7eee4-111">Note that it does not help to cast the referring object to the underlying interface.</span></span> <span data-ttu-id="7eee4-112">Per evitare questo errore, è necessario eseguire il cast dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="7eee4-112">You must cast the argument to avoid this error.</span></span>

## <a name="example"></a><span data-ttu-id="7eee4-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="7eee4-113">Example</span></span>

<span data-ttu-id="7eee4-114">Nell'esempio seguente viene illustrata una chiamata a una routine di overload `Sub` che causa questo errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7eee4-114">The following example shows a call to an overloaded `Sub` procedure that causes this error at compile time.</span></span>

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

<span data-ttu-id="7eee4-115">Nell'esempio precedente, se il compilatore consentiva la chiamata a `s1` come scritto, la risoluzione verrebbe eseguita tramite la classe `c1` anziché l'interfaccia `i1` .</span><span class="sxs-lookup"><span data-stu-id="7eee4-115">In the preceding example, if the compiler allowed the call to `s1` as written, the resolution would take place through the class `c1` instead of the interface `i1`.</span></span> <span data-ttu-id="7eee4-116">Ciò significa che il compilatore non prende in considerazione `s2` perché il nome è diverso in `c1` , anche se è la scelta corretta in base a quanto definito da `i1` .</span><span class="sxs-lookup"><span data-stu-id="7eee4-116">This would mean that the compiler would not consider `s2` because its name is different in `c1`, even though it is the correct choice as defined by `i1`.</span></span>

<span data-ttu-id="7eee4-117">È possibile correggere l'errore modificando la chiamata a una delle righe di codice seguenti:</span><span class="sxs-lookup"><span data-stu-id="7eee4-117">You can correct the error by changing the call to either of the following lines of code:</span></span>

```vb
refer.s1(CType(o1, Integer))
refer.s1(CType(o1, Double))
```

<span data-ttu-id="7eee4-118">Ognuna delle righe precedenti di codice esegue esplicitamente il cast della `Object` variabile `o1` a uno dei tipi di parametro definiti per gli overload.</span><span class="sxs-lookup"><span data-stu-id="7eee4-118">Each of the preceding lines of code explicitly casts the `Object` variable `o1` to one of the parameter types defined for the overloads.</span></span>

## <a name="see-also"></a><span data-ttu-id="7eee4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7eee4-119">See also</span></span>

- [<span data-ttu-id="7eee4-120">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="7eee4-120">Procedure Overloading</span></span>](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="7eee4-121">Risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="7eee4-121">Overload Resolution</span></span>](../../programming-guide/language-features/procedures/overload-resolution.md)
- [<span data-ttu-id="7eee4-122">CType Function</span><span class="sxs-lookup"><span data-stu-id="7eee4-122">CType Function</span></span>](../functions/ctype-function.md)
