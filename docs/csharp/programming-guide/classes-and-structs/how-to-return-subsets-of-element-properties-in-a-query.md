---
title: Come restituire subset di proprietà degli elementi in una query-Guida per programmatori C#
description: Informazioni su come usare un tipo anonimo in un'espressione di query in C# per restituire alcune delle proprietà di ogni elemento di origine.
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
ms.openlocfilehash: 882d94bc82527c14bd6c038f4bf574c2211b9089
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864371"
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a>Come restituire subset di proprietà degli elementi in una query (Guida per programmatori C#)
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
  
## <a name="see-also"></a>Vedi anche

- [Guida per programmatori C#](../index.md)
- [Tipi anonimi](./anonymous-types.md)
- [LINQ in C#](../../linq/index.md)
