---
title: "Procedura: restituire sottoinsiemi di proprietà degli elementi in una query (Guida per programmatori C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6654b162fbdeb59ed2a135d7d8cf58c8b3406c13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a>Procedura: restituire sottoinsiemi di proprietà degli elementi in una query (Guida per programmatori C#)
Usare un tipo anonimo in un'espressione di query quando si verificano entrambe le condizioni seguenti:  
  
-   Si vogliono restituire solo alcune delle proprietà di ogni elemento di origine.  
  
-   Non è necessario archiviare la query all'esterno dell'ambito del metodo in cui è stata eseguita.  
  
 Se si vuole restituire solo una proprietà o un campo da ogni elemento di origine, è sufficiente usare l'operatore punto nella clausola `select`. Per restituire, ad esempio, solo l'`ID` di ogni `student`, scrivere la clausola `select` come segue:  
  
```  
select student.ID;  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come usare un tipo anonimo per restituire solo un sottoinsieme delle proprietà di ogni elemento di origine che corrisponde alla condizione specificata.  
  
 [!code-csharp[csProgGuideLINQ#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-return-subsets-of-element-properties-in-a-query_1.cs)]  
  
 Si noti che se per le proprietà non è specificato alcun nome, il tipo anonimo usa i nomi dell'elemento di origine. Per assegnare nuovi nomi alle proprietà nel tipo anonimo, scrivere l'istruzione `select` come segue:  
  
```  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 Se si tenta questa operazione nell'esempio precedente, è necessario modificare anche l'istruzione `Console.WriteLine`:  
  
```  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
-   Per eseguire questo codice, copiare e incollare la classe in un progetto di applicazione console di Visual C# creato in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)]. Per impostazione predefinita, questo progetto usa la versione 3.5 di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] e contiene un riferimento a System.Core.dll e una direttiva `using` per System.Linq. Se uno o più di questi requisiti non sono presenti nel progetto, è possibile aggiungerli manualmente.   
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Tipi anonimi](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [Espressioni di query LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)
