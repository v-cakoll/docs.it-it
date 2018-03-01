---
title: "&#39; Per ogni &#39; nel tipo &#39; &lt;typename&gt;&#39; è ambiguo perché il tipo implementa più creazioni di istanza di &#39; IEnumerable (Of T) &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a74178f3f0b2e7589b87046973473582993f3ed9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a>&#39; Per ogni &#39; nel tipo &#39; &lt;typename&gt;&#39; è ambiguo perché il tipo implementa più creazioni di istanza di &#39; IEnumerable (Of T) &#39;
Oggetto `For Each` istruzione specifica una variabile di iteratore che è presenti più <xref:System.Collections.IEnumerable.GetEnumerator%2A> metodo.  
  
 La variabile iteratore deve essere di un tipo che implementa il <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interfaccia in uno del `Collections` spazi dei nomi di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. È possibile che una classe implementare più interfacce generiche costruite con un argomento di tipo diverso per ogni tipo di costruzione. Se una classe che esegue questa operazione viene utilizzata per la variabile iteratore, tale variabile è presenti più <xref:System.Collections.IEnumerable.GetEnumerator%2A> metodo. In tal caso, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] non è possibile scegliere il metodo da chiamare.  
  
 **ID errore:** BC32096  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Utilizzare [operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) o [operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) per eseguire il cast del tipo di variabile di iteratore per l'interfaccia che definisce il <xref:System.Collections.IEnumerable.GetEnumerator%2A> metodo che si desidera utilizzare.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
