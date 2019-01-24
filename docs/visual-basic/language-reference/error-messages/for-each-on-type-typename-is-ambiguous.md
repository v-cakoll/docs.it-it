---
title: '&#39;Per ogni&#39; nel tipo &#39; &lt;typename&gt; &#39; è ambiguo perché il tipo implementa più creazioni di istanza di &#39;IEnumerable (Of T)&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: 7fd779ba34afa2a59fa6c42971597df8ce01495a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597346"
---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a>&#39;Per ogni&#39; nel tipo &#39; &lt;typename&gt; &#39; è ambiguo perché il tipo implementa più creazioni di istanza di &#39;IEnumerable (Of T)&#39;
Oggetto `For Each` istruzione specifica una variabile di iteratore che è presenti più <xref:System.Collections.IEnumerable.GetEnumerator%2A> (metodo).  
  
 La variabile iteratore deve essere di un tipo che implementa il <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interfaccia in uno del `Collections` spazi dei nomi il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. È possibile che una classe implementare più interfacce di generico costruito, usando un argomento di tipo diverso per ogni tipo di costruzione. Se una classe che esegue questa operazione viene usata per la variabile iteratore, tale variabile è presenti più <xref:System.Collections.IEnumerable.GetEnumerator%2A> (metodo). In tal caso, Visual Basic non è possibile scegliere il metodo da chiamare.  
  
 **ID errore:** BC32096  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Usare [operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) oppure [operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) per eseguire il cast del tipo di variabile di iteratore per l'interfaccia che definisce il <xref:System.Collections.IEnumerable.GetEnumerator%2A> metodo da usare.  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
