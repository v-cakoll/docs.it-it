---
title: 'Procedura: usare espressioni lambda in una guida per la C# programmazione di query'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], in LINQ
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
ms.openlocfilehash: e7e7da211599b5ce0263377ecaf25b404399ce9c
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423171"
---
# <a name="how-to-use-lambda-expressions-in-a-query-c-programming-guide"></a>Procedura: utilizzare espressioni lambda in una query (Guida per programmatori C#)
Le espressioni lambda non vengono usate direttamente nella sintassi delle query, ma nelle chiamate al metodo e le espressioni di query possono contenere chiamate al metodo. Di fatto, alcune operazioni di query possono essere espresse solo nella sintassi del metodo. Per altre informazioni sulle differenze tra la sintassi delle query e la sintassi dei metodi, vedere [Sintassi di query e sintassi di metodi in LINQ](../concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come usare un'espressione lambda in una query basata sul metodo tramite l'operatore query standard <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType>. Si noti che il metodo <xref:System.Linq.Enumerable.Where%2A> in questo esempio dispone di un parametro di input del tipo delegato <xref:System.Func%602> e che il delegato accetta come input un numero intero e restituisce un valore booleano. L'espressione lambda può essere convertita al delegato. Se si trattasse di una query [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] che usa il metodo <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>, il tipo di parametro sarebbe un `Expression<Func<int,bool>>` ma l'espressione lambda avrebbe esattamente lo stesso aspetto. Per altre informazioni sul tipo di espressione, vedere <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType>.  
  
 [!code-csharp[csProgGuideLINQ#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csrefLINQHowTos.cs#1)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come usare un'espressione lambda in una chiamata al metodo di un'espressione di query. L'espressione lambda è necessaria perché l'operatore query standard <xref:System.Linq.Enumerable.Sum%2A> non può essere richiamato tramite la sintassi della query.  
  
 La query raggruppa innanzitutto gli studenti in base alla classe, come definito nel valore enum `GradeLevel`. Quindi per ogni gruppo aggiunge il punteggio totale per ogni studente. Ciò richiede due operazioni `Sum`. La `Sum` interna calcola il punteggio totale per ogni studente, mentre la `Sum` esterna mantiene un totale combinato e in esecuzione per tutti gli studenti del gruppo.  
  
 [!code-csharp[csProgGuideLINQ#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csrefLINQHowTos.cs#2)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per eseguire questo codice, copiare e incollare il metodo nel valore `StudentClass` fornito in [Procedura: eseguire una query su una raccolta di oggetti](../../linq/query-a-collection-of-objects.md) e chiamarlo dal metodo `Main`.  
  
## <a name="see-also"></a>Vedere anche

- [Espressioni lambda](./lambda-expressions.md)
- [Alberi delle espressioni (C#)](../concepts/expression-trees/index.md)
