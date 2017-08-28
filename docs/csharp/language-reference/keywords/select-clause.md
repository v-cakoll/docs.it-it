---
title: Clausola select (Riferimento C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- select_CSharpKeyword
- select
dev_langs:
- CSharp
helpviewer_keywords:
- select keyword [C#]
- select clause [C#]
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a505399eb79cbecbefcc53953329279a4abd92f6
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="select-clause-c-reference"></a>Clausola select (Riferimento C#)
In un'espressione di query, la clausola `select` specifica il tipo di valori che verranno prodotti quando viene eseguita la query. Il risultato è basato sulla valutazione di tutte le clausole precedenti e su qualsiasi espressione nella clausola `select` stessa. Un'espressione di query deve terminare con una clausola `select` o una clausola [group](../../../csharp/language-reference/keywords/group-clause.md).  
  
 Nell'esempio seguente viene illustrata una semplice clausola `select` in un'espressione di query.  
  
 [!code-cs[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_1.cs)]  
  
 Il tipo della sequenza prodotto dalla clausola `select` determina il tipo della variabile di query `queryHighScores`. Nel caso più semplice, la clausola `select` specifica solo la variabile di intervallo. In tal modo, la sequenza restituita contiene elementi dello stesso tipo dell'origine dati. Per altre informazioni, vedere [Relazioni tra i tipi nelle operazioni di query LINQ (C#)](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md). Tuttavia, la clausola `select` fornisce anche un potente meccanismo per la trasformazione (o la *proiezione*) dell'origine dati in nuovi tipi. Per altre informazioni, vedere [Trasformazioni dati con LINQ (C#)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente sono illustrate tutte le diverse forme che una clausola `select` può avere. In ogni query, si noti la relazione tra la clausola `select` e il tipo di *variabile di query* (`studentQuery1`, `studentQuery2` e così via).  
  
 [!code-cs[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_2.cs)]  
  
 Come illustrato in `studentQuery8` nell'esempio precedente, in alcuni casi è preferibile che gli elementi della sequenza restituita contengano solo un subset delle proprietà degli elementi di origine. Riducendo al minimo le dimensioni della sequenza restituita, è possibile ridurre i requisiti di memoria e aumentare la velocità di esecuzione della query. A tale scopo, è possibile creare un tipo anonimo nella clausola `select` e usare un inizializzatore di oggetto per inizializzarlo con le proprietà appropriate dall'elemento di origine. Per un esempio di come eseguire questa operazione, vedere [Inizializzatori di oggetto e di raccolta](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## <a name="remarks"></a>Note  
 In fase di compilazione, la clausola `select` viene convertita in una chiamata al metodo per l'operatore query standard <xref:System.Linq.Enumerable.Select%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)   
 [Parole chiave di query (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Clausola From](../../../csharp/language-reference/keywords/from-clause.md)   
 [parziale (Metodo) (Riferimenti per C#)](../../../csharp/language-reference/keywords/partial-method.md)   
 [Tipi anonimi](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Espressioni di query LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Nozioni di base su LINQ in C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

