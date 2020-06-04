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
# <a name="for-each-on-type-typename-is-ambiguous-because-the-type-implements-multiple-instantiations-of-systemcollectionsgenericienumerableof-t"></a>For Each' sul tipo '\<typename>' è ambiguo perché il tipo implementa più creazioni di istanza di 'System.Collections.Generic.IEnumerable(Of T)'
Un' `For Each` istruzione specifica una variabile iteratore con più di un <xref:System.Collections.IEnumerable.GetEnumerator%2A> metodo.  
  
 La variabile iteratore deve essere di un tipo che implementa <xref:System.Collections.IEnumerable?displayProperty=nameWithType> l' <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interfaccia o in uno degli `Collections` spazi dei nomi del .NET Framework. È possibile che una classe implementi più di un'interfaccia generica costruita, usando un argomento di tipo diverso per ogni costruzione. Se una classe che esegue questa operazione viene usata per la variabile iteratore, tale variabile ha più di un <xref:System.Collections.IEnumerable.GetEnumerator%2A> metodo. In tal caso, Visual Basic non è in grado di scegliere il metodo da chiamare.  
  
 **ID errore:** BC32096  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Usare l'operatore [DirectCast](../operators/directcast-operator.md) o [TryCast](../operators/trycast-operator.md) per eseguire il cast del tipo di variabile iteratore all'interfaccia che definisce il <xref:System.Collections.IEnumerable.GetEnumerator%2A> metodo che si vuole usare.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione For Each...Next](../statements/for-each-next-statement.md)
- [Interfacce](../../programming-guide/language-features/interfaces/index.md)
