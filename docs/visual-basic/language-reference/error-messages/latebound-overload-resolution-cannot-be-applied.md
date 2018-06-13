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
# <a name="latebound-overload-resolution-cannot-be-applied-to-39ltprocedurenamegt39-because-the-accessing-instance-is-an-interface-type"></a><span data-ttu-id="eed29-102">Risoluzione dell'overload con associazione tardiva non è possibile applicare a &#39; &lt;nomeroutine&gt; &#39; perché l'istanza di accesso è un tipo di interfaccia</span><span class="sxs-lookup"><span data-stu-id="eed29-102">Latebound overload resolution cannot be applied to &#39;&lt;procedurename&gt;&#39; because the accessing instance is an interface type</span></span>
<span data-ttu-id="eed29-103">Il compilatore sta provando a risolvere un riferimento a una proprietà di overload o una routine, ma il riferimento non riesce perché è un argomento di tipo `Object` e l'oggetto che fa riferimento il tipo di dati di un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="eed29-103">The compiler is attempting to resolve a reference to an overloaded property or procedure, but the reference fails because an argument is of type `Object` and the referring object has the data type of an interface.</span></span> <span data-ttu-id="eed29-104">Il `Object` argomento induce il compilatore per risolvere il riferimento come ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="eed29-104">The `Object` argument forces the compiler to resolve the reference as late-bound.</span></span>  
  
 <span data-ttu-id="eed29-105">In questi casi, il compilatore risolve l'overload tramite la classe di implementazione anziché tramite l'interfaccia sottostante.</span><span class="sxs-lookup"><span data-stu-id="eed29-105">In these circumstances, the compiler resolves the overload through the implementing class instead of through the underlying interface.</span></span> <span data-ttu-id="eed29-106">Se la classe rinomina una delle versioni di overload, il compilatore non considera tale versione di overload perché il nome è diverso.</span><span class="sxs-lookup"><span data-stu-id="eed29-106">If the class renames one of the overloaded versions, the compiler does not consider that version to be an overload because its name is different.</span></span> <span data-ttu-id="eed29-107">Questo causa a sua volta al compilatore di ignorare la versione rinominata quando sarebbe stato la scelta corretta per risolvere il riferimento.</span><span class="sxs-lookup"><span data-stu-id="eed29-107">This in turn causes the compiler to ignore the renamed version when it might have been the correct choice to resolve the reference.</span></span>  
  
 <span data-ttu-id="eed29-108">**ID errore:** BC30933</span><span class="sxs-lookup"><span data-stu-id="eed29-108">**Error ID:** BC30933</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="eed29-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="eed29-109">To correct this error</span></span>  
  
-   <span data-ttu-id="eed29-110">Utilizzare `CType` per eseguire il cast dell'argomento da `Object` al tipo specificato per la firma di overload da chiamare.</span><span class="sxs-lookup"><span data-stu-id="eed29-110">Use `CType` to cast the argument from `Object` to the type specified by the signature of the overload you want to call.</span></span>  
  
     <span data-ttu-id="eed29-111">Si noti che non consentono il cast dell'oggetto che fa riferimento all'interfaccia sottostante.</span><span class="sxs-lookup"><span data-stu-id="eed29-111">Note that it does not help to cast the referring object to the underlying interface.</span></span> <span data-ttu-id="eed29-112">È necessario eseguire il cast dell'argomento per evitare questo errore.</span><span class="sxs-lookup"><span data-stu-id="eed29-112">You must cast the argument to avoid this error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eed29-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="eed29-113">Example</span></span>  
 <span data-ttu-id="eed29-114">Nell'esempio seguente viene illustrata una chiamata a un overload `Sub` procedure che genera questo errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="eed29-114">The following example shows a call to an overloaded `Sub` procedure that causes this error at compile time.</span></span>  
  
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
  
 <span data-ttu-id="eed29-115">Nell'esempio precedente, se il compilatore ha consentito la chiamata a `s1` quanto scritto, la risoluzione verrà eseguita tramite la classe `c1` anziché l'interfaccia `i1`.</span><span class="sxs-lookup"><span data-stu-id="eed29-115">In the preceding example, if the compiler allowed the call to `s1` as written, the resolution would take place through the class `c1` instead of the interface `i1`.</span></span> <span data-ttu-id="eed29-116">Ciò significa che il compilatore non considerare `s2` perché il nome è diverso in `c1`, anche se è la scelta corretta, come definito da `i1`.</span><span class="sxs-lookup"><span data-stu-id="eed29-116">This would mean that the compiler would not consider `s2` because its name is different in `c1`, even though it is the correct choice as defined by `i1`.</span></span>  
  
 <span data-ttu-id="eed29-117">È possibile correggere l'errore modificando la chiamata a una delle righe di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="eed29-117">You can correct the error by changing the call to either of the following lines of code:</span></span>  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 <span data-ttu-id="eed29-118">Ognuna delle righe di codice precedenti esegue il cast in modo esplicito il `Object` variabile `o1` a uno dei tipi di parametro definiti per gli overload.</span><span class="sxs-lookup"><span data-stu-id="eed29-118">Each of the preceding lines of code explicitly casts the `Object` variable `o1` to one of the parameter types defined for the overloads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eed29-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eed29-119">See Also</span></span>  
 [<span data-ttu-id="eed29-120">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="eed29-120">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [<span data-ttu-id="eed29-121">Risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="eed29-121">Overload Resolution</span></span>](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)  
 [<span data-ttu-id="eed29-122">Funzione CType</span><span class="sxs-lookup"><span data-stu-id="eed29-122">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
