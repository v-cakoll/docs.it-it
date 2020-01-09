---
title: Come utilizzare le espressioni lambda in una query- C# Guida alla programmazione
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], in LINQ
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
ms.openlocfilehash: 92bdbf842c5c30b2f32e06f622f3e08f3c7a878f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711961"
---
# <a name="how-to-use-lambda-expressions-in-a-query-c-programming-guide"></a>Come usare le espressioni lambda in una query (C# guida per programmatori)
Le espressioni lambda non vengono usate direttamente nella sintassi delle query, ma nelle chiamate al metodo e le espressioni di query possono contenere chiamate al metodo. Di fatto, alcune operazioni di query possono essere espresse solo nella sintassi del metodo. Per altre informazioni sulle differenze tra la sintassi delle query e la sintassi dei metodi, vedere [Sintassi di query e sintassi di metodi in LINQ](../concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come usare un'espressione lambda in una query basata sul metodo tramite l'operatore query standard <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType>. Si noti che il metodo <xref:System.Linq.Enumerable.Where%2A> in questo esempio dispone di un parametro di input del tipo delegato <xref:System.Func%602> e che il delegato accetta come input un numero intero e restituisce un valore booleano. L'espressione lambda può essere convertita al delegato. Se si trattasse di una query [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] che usa il metodo <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>, il tipo di parametro sarebbe un `Expression<Func<int,bool>>` ma l'espressione lambda avrebbe esattamente lo stesso aspetto. Per altre informazioni sul tipo di espressione, vedere <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType>.  
  
 [!code-csharp[csProgGuideLINQ#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csrefLINQHowTos.cs#1)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come usare un'espressione lambda in una chiamata al metodo di un'espressione di query. L'espressione lambda è necessaria perché l'operatore query standard <xref:System.Linq.Enumerable.Sum%2A> non può essere richiamato tramite la sintassi della query.  
  
 La query raggruppa innanzitutto gli studenti in base alla classe, come definito nel valore enum `GradeLevel`. Quindi per ogni gruppo aggiunge il punteggio totale per ogni studente. Ciò richiede due operazioni `Sum`. La `Sum` interna calcola il punteggio totale per ogni studente, mentre la `Sum` esterna mantiene un totale combinato e in esecuzione per tutti gli studenti del gruppo.  
  
 [!code-csharp[csProgGuideLINQ#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csrefLINQHowTos.cs#2)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per eseguire questo codice, copiare e incollare il metodo nel `StudentClass` fornito in [eseguire una query su una raccolta di oggetti](../../linq/query-a-collection-of-objects.md) e chiamarlo dal metodo `Main`.
  
## <a name="see-also"></a>Vedere anche

- [Espressioni lambda](./lambda-expressions.md)
- [Alberi delle espressioni (C#)](../concepts/expression-trees/index.md)
