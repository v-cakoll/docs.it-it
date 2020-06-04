---
title: For Each' sul tipo '<typename>' è ambiguo perché il tipo implementa più creazioni di istanza di 'System.Collections.Generic.IEnumerable(Of T)'
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: 153a2640d66f48660f21339aaf0ecc8eaa10f51f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402966"
---
# <a name="for-each-on-type-typename-is-ambiguous-because-the-type-implements-multiple-instantiations-of-systemcollectionsgenericienumerableof-t"></a><span data-ttu-id="8c936-102">For Each' sul tipo '\<typename>' è ambiguo perché il tipo implementa più creazioni di istanza di 'System.Collections.Generic.IEnumerable(Of T)'</span><span class="sxs-lookup"><span data-stu-id="8c936-102">'For Each' on type '\<typename>' is ambiguous because the type implements multiple instantiations of 'System.Collections.Generic.IEnumerable(Of T)'</span></span>
<span data-ttu-id="8c936-103">Un' `For Each` istruzione specifica una variabile iteratore con più di un <xref:System.Collections.IEnumerable.GetEnumerator%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="8c936-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>  
  
 <span data-ttu-id="8c936-104">La variabile iteratore deve essere di un tipo che implementa <xref:System.Collections.IEnumerable?displayProperty=nameWithType> l' <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interfaccia o in uno degli `Collections` spazi dei nomi del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8c936-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface in one of the `Collections` namespaces of the .NET Framework.</span></span> <span data-ttu-id="8c936-105">È possibile che una classe implementi più di un'interfaccia generica costruita, usando un argomento di tipo diverso per ogni costruzione.</span><span class="sxs-lookup"><span data-stu-id="8c936-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="8c936-106">Se una classe che esegue questa operazione viene usata per la variabile iteratore, tale variabile ha più di un <xref:System.Collections.IEnumerable.GetEnumerator%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="8c936-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="8c936-107">In tal caso, Visual Basic non è in grado di scegliere il metodo da chiamare.</span><span class="sxs-lookup"><span data-stu-id="8c936-107">In such a case, Visual Basic cannot choose which method to call.</span></span>  
  
 <span data-ttu-id="8c936-108">**ID errore:** BC32096</span><span class="sxs-lookup"><span data-stu-id="8c936-108">**Error ID:** BC32096</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8c936-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="8c936-109">To correct this error</span></span>  
  
- <span data-ttu-id="8c936-110">Usare l'operatore [DirectCast](../operators/directcast-operator.md) o [TryCast](../operators/trycast-operator.md) per eseguire il cast del tipo di variabile iteratore all'interfaccia che definisce il <xref:System.Collections.IEnumerable.GetEnumerator%2A> metodo che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="8c936-110">Use [DirectCast Operator](../operators/directcast-operator.md) or [TryCast Operator](../operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c936-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c936-111">See also</span></span>

- [<span data-ttu-id="8c936-112">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="8c936-112">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
- [<span data-ttu-id="8c936-113">Interfacce</span><span class="sxs-lookup"><span data-stu-id="8c936-113">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
