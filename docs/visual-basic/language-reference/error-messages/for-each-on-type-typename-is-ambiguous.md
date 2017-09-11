---
title: "&quot;For Each&quot; sul tipo &quot;&lt;typename&gt;&quot; è ambiguo perché il tipo implementa più creazioni di istanze di &quot;IEnumerable (Of T)&quot; | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32096
- bc32096
dev_langs:
- VB
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 783c741a8acb0d27ef6ff5c52939bd12a026ba74
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a><span data-ttu-id="f6406-102">'For Each' sul tipo '&lt;typename&gt;' è ambiguo perché il tipo implementa più creazioni di istanze di 'IEnumerable (Of T)'</span><span class="sxs-lookup"><span data-stu-id="f6406-102">&#39;For Each&#39; on type &#39;&lt;typename&gt;&#39; is ambiguous because the type implements multiple instantiations of &#39;System.Collections.Generic.IEnumerable(Of T)&#39;</span></span>
<span data-ttu-id="f6406-103">Oggetto `For Each` istruzione specifica una variabile di iteratore che è presenti più <xref:System.Collections.IEnumerable.GetEnumerator%2A>metodo.</xref:System.Collections.IEnumerable.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="f6406-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>  
  
 <span data-ttu-id="f6406-104">La variabile di iteratore deve essere di un tipo che implementa il <xref:System.Collections.IEnumerable?displayProperty=fullName>o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>interfaccia in uno del `Collections` gli spazi dei nomi di [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> </xref:System.Collections.IEnumerable?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f6406-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=fullName> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> interface in one of the `Collections` namespaces of the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="f6406-105">È possibile che una classe implementare più interfacce generiche costruite utilizzando un argomento di tipo diverso per ogni tipo di costruzione.</span><span class="sxs-lookup"><span data-stu-id="f6406-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="f6406-106">Se una classe che esegue questa operazione viene utilizzata per la variabile di iteratore, tale variabile è presenti più <xref:System.Collections.IEnumerable.GetEnumerator%2A>metodo.</xref:System.Collections.IEnumerable.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="f6406-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="f6406-107">In tal caso, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] non può scegliere il metodo da chiamare.</span><span class="sxs-lookup"><span data-stu-id="f6406-107">In such a case, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot choose which method to call.</span></span>  
  
 <span data-ttu-id="f6406-108">**ID errore:** BC32096</span><span class="sxs-lookup"><span data-stu-id="f6406-108">**Error ID:** BC32096</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f6406-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f6406-109">To correct this error</span></span>  
  
-   <span data-ttu-id="f6406-110">Utilizzare [operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) o [operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) per eseguire il cast del tipo di variabile di iteratore per l'interfaccia che definisce il <xref:System.Collections.IEnumerable.GetEnumerator%2A>metodo che si desidera utilizzare.</xref:System.Collections.IEnumerable.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="f6406-110">Use [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6406-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6406-111">See Also</span></span>  
 <span data-ttu-id="f6406-112">[Per ogni corso... Next (istruzione)](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f6406-112">[For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span></span>  
<span data-ttu-id="f6406-113"> [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)</span><span class="sxs-lookup"><span data-stu-id="f6406-113"> [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)</span></span>
