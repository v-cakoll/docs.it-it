---
title: "&#39; Per ogni &#39; nel tipo &#39; &lt;typename&gt;&#39; è ambiguo perché il tipo implementa più creazioni di istanza di &#39; IEnumerable (Of T) &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords: BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a74178f3f0b2e7589b87046973473582993f3ed9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a><span data-ttu-id="f3ab5-102">&#39; Per ogni &#39; nel tipo &#39; &lt;typename&gt;&#39; è ambiguo perché il tipo implementa più creazioni di istanza di &#39; IEnumerable (Of T) &#39;</span><span class="sxs-lookup"><span data-stu-id="f3ab5-102">&#39;For Each&#39; on type &#39;&lt;typename&gt;&#39; is ambiguous because the type implements multiple instantiations of &#39;System.Collections.Generic.IEnumerable(Of T)&#39;</span></span>
<span data-ttu-id="f3ab5-103">Oggetto `For Each` istruzione specifica una variabile di iteratore che è presenti più <xref:System.Collections.IEnumerable.GetEnumerator%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="f3ab5-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>  
  
 <span data-ttu-id="f3ab5-104">La variabile iteratore deve essere di un tipo che implementa il <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interfaccia in uno del `Collections` spazi dei nomi di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3ab5-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface in one of the `Collections` namespaces of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="f3ab5-105">È possibile che una classe implementare più interfacce generiche costruite con un argomento di tipo diverso per ogni tipo di costruzione.</span><span class="sxs-lookup"><span data-stu-id="f3ab5-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="f3ab5-106">Se una classe che esegue questa operazione viene utilizzata per la variabile iteratore, tale variabile è presenti più <xref:System.Collections.IEnumerable.GetEnumerator%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="f3ab5-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="f3ab5-107">In tal caso, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] non è possibile scegliere il metodo da chiamare.</span><span class="sxs-lookup"><span data-stu-id="f3ab5-107">In such a case, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cannot choose which method to call.</span></span>  
  
 <span data-ttu-id="f3ab5-108">**ID errore:** BC32096</span><span class="sxs-lookup"><span data-stu-id="f3ab5-108">**Error ID:** BC32096</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f3ab5-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f3ab5-109">To correct this error</span></span>  
  
-   <span data-ttu-id="f3ab5-110">Utilizzare [operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) o [operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) per eseguire il cast del tipo di variabile di iteratore per l'interfaccia che definisce il <xref:System.Collections.IEnumerable.GetEnumerator%2A> metodo che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="f3ab5-110">Use [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3ab5-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3ab5-111">See Also</span></span>  
 [<span data-ttu-id="f3ab5-112">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="f3ab5-112">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="f3ab5-113">Interfacce</span><span class="sxs-lookup"><span data-stu-id="f3ab5-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
