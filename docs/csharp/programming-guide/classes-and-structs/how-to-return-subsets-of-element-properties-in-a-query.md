---
title: 'Procedura: Restituire sottoinsiemi di proprietà degli elementi in una query - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
ms.openlocfilehash: 2c9fea2189819058187020c2e67b8826659fbed4
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205442"
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a>Procedura: Restituire sottoinsiemi di proprietà degli elementi in una query (Guida per programmatori C#)
Usare un tipo anonimo in un'espressione di query quando si verificano entrambe le condizioni seguenti:  
  
- Si vogliono restituire solo alcune delle proprietà di ogni elemento di origine.  
  
- Non è necessario archiviare la query all'esterno dell'ambito del metodo in cui è stata eseguita.  
  
 Se si vuole restituire solo una proprietà o un campo da ogni elemento di origine, è sufficiente usare l'operatore punto nella clausola `select`. Per restituire, ad esempio, solo l'`ID` di ogni `student`, scrivere la clausola `select` come segue:  
  
```csharp  
select student.ID;  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come usare un tipo anonimo per restituire solo un sottoinsieme delle proprietà di ogni elemento di origine che corrisponde alla condizione specificata.  
  
 [!code-csharp[csProgGuideLINQ#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#31)]  
  
 Si noti che se per le proprietà non è specificato alcun nome, il tipo anonimo usa i nomi dell'elemento di origine. Per assegnare nuovi nomi alle proprietà nel tipo anonimo, scrivere l'istruzione `select` come segue:  
  
```csharp  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 Se si tenta questa operazione nell'esempio precedente, è necessario modificare anche l'istruzione `Console.WriteLine`:  
  
```csharp  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
Per eseguire questo codice, copiare e incollare la classe in un'applicazione console C# con una direttiva `using` per System.Linq.
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Tipi anonimi](./anonymous-types.md)
- [Espressioni di query LINQ](../linq-query-expressions/index.md)
