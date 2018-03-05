---
title: 'Procedura: Eseguire la ricerca di stringhe tramite espressioni regolari (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with RegEx
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c851c57b44f1343816b905db002e530121fb6c0a
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2018
---
# <a name="how-to-search-strings-using-regular-expressions-c-programming-guide"></a>Procedura: Eseguire la ricerca di stringhe tramite espressioni regolari (Guida per programmatori C#)
La classe <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> può essere usata per eseguire la ricerca di stringhe. Queste ricerche possono avere livelli di complessità molto diversi, da molto semplici a casi in cui vengono usate espressioni regolari. Di seguito sono riportati due esempi di ricerca di stringhe tramite la classe <xref:System.Text.RegularExpressions.Regex>. Per altre informazioni, vedere [Espressioni regolari di .NET Framework](https://msdn.microsoft.com/library/hs600312).  
  
## <a name="example"></a>Esempio  
 Il codice seguente è un'applicazione console che esegue una semplice ricerca di stringhe in una matrice, senza distinzione tra maiuscole e minuscole. Il metodo statico <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> esegue la ricerca in base alla stringa da cercare e a una stringa contenente i criteri di ricerca. In questo caso viene usato un terzo argomento per indicare che la distinzione tra lettere maiuscole e minuscole deve essere ignorata. Per altre informazioni, vedere <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.  
  
 [!code-csharp[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente rappresenta un'applicazione console che usa le espressioni regolari per convalidare il formato di ogni stringa in una matrice. Per la convalida è necessario che ogni stringa abbia il formato di un numero di telefono costituito da tre gruppi di cifre separate da trattini, di cui i primi due gruppi contengono tre cifre e il terzo ne contiene quattro. A tale scopo viene usata l'espressione regolare `^\\d{3}-\\d{3}-\\d{4}$`. Per altre informazioni, vedere [Linguaggio di espressioni regolari - Riferimento rapido](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).  
  
 [!code-csharp[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Stringhe](../../../csharp/programming-guide/strings/index.md)  
 [Espressioni regolari di .NET Framework](https://msdn.microsoft.com/library/hs600312)  
 [Linguaggio di espressioni regolari - Riferimento rapido](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)
