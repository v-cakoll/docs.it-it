---
title: 'Procedura: utilizzare espressioni lambda in una query (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: lambda expressions [C#], in LINQ
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 279d76aa29f27d35bc907d6779a146a23c7e162a
ms.sourcegitcommit: bf8a3ba647252010bdce86dd914ac6c61b5ba89d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2018
---
# <a name="how-to-use-lambda-expressions-in-a-query-c-programming-guide"></a>Procedura: utilizzare espressioni lambda in una query (Guida per programmatori C#)
Le espressioni lambda non vengono usate direttamente nella sintassi delle query, ma nelle chiamate al metodo e le espressioni di query possono contenere chiamate al metodo. Di fatto, alcune operazioni di query possono essere espresse solo nella sintassi del metodo. Per altre informazioni sulle differenze tra la sintassi delle query e la sintassi dei metodi, vedere [Sintassi di query e sintassi di metodi in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come usare un'espressione lambda in una query basata sul metodo tramite l'operatore query standard <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType>. Si noti che il metodo <xref:System.Linq.Enumerable.Where%2A> in questo esempio dispone di un parametro di input del tipo delegato <xref:System.Func%601> e che il delegato accetta come input un numero intero e restituisce un valore booleano. L'espressione lambda può essere convertita al delegato. Se si trattasse di una query [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] che usa il metodo <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>, il tipo di parametro sarebbe un `Expression<Func<int,bool>>` ma l'espressione lambda avrebbe esattamente lo stesso aspetto. Per altre informazioni sul tipo di espressione, vedere <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType>.  
  
 [!code-csharp[csProgGuideLINQ#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_1.cs)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come usare un'espressione lambda in una chiamata al metodo di un'espressione di query. L'espressione lambda è necessaria perché l'operatore query standard <xref:System.Linq.Enumerable.Sum%2A> non può essere richiamato tramite la sintassi della query.  
  
 La query raggruppa innanzitutto gli studenti in base alla classe, come definito nel valore enum `GradeLevel`. Quindi per ogni gruppo aggiunge il punteggio totale per ogni studente. Ciò richiede due operazioni `Sum`. La `Sum` interna calcola il punteggio totale per ogni studente, mentre la `Sum` esterna mantiene un totale combinato e in esecuzione per tutti gli studenti del gruppo.  
  
 [!code-csharp[csProgGuideLINQ#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_2.cs)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per eseguire questo codice, copiare e incollare il metodo nel valore `StudentClass` fornito in [Procedura: eseguire una query su una raccolta di oggetti](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md) e chiamarlo dal metodo `Main`.  
  
## <a name="see-also"></a>Vedere anche  
 [Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
 [Alberi delle espressioni](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)
