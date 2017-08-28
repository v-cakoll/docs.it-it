---
title: 'Procedura: Eseguire la ricerca di stringhe tramite espressioni regolari (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with RegEx
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fb05d1702c75be8fd224ee0f34d7d8d3fe71f207
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-search-strings-using-regular-expressions-c-programming-guide"></a>Procedura: Eseguire la ricerca di stringhe tramite espressioni regolari (Guida per programmatori C#)
La classe <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> può essere usata per eseguire la ricerca di stringhe. Queste ricerche possono avere livelli di complessità molto diversi, da molto semplici a casi in cui vengono usate espressioni regolari. Di seguito sono riportati due esempi di ricerca di stringhe tramite la classe <xref:System.Text.RegularExpressions.Regex>. Per altre informazioni, vedere [Espressioni regolari di .NET Framework](https://msdn.microsoft.com/library/hs600312).  
  
## <a name="example"></a>Esempio  
 Il codice seguente è un'applicazione console che esegue una semplice ricerca di stringhe in una matrice, senza distinzione tra maiuscole e minuscole. Il metodo statico <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> esegue la ricerca in base alla stringa da cercare e a una stringa contenente i criteri di ricerca. In questo caso viene usato un terzo argomento per indicare che la distinzione tra lettere maiuscole e minuscole deve essere ignorata. Per altre informazioni, vedere <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente rappresenta un'applicazione console che usa le espressioni regolari per convalidare il formato di ogni stringa in una matrice. Per la convalida è necessario che ogni stringa abbia il formato di un numero di telefono costituito da tre gruppi di cifre separate da trattini, di cui i primi due gruppi contengono tre cifre e il terzo ne contiene quattro. A tale scopo viene usata l'espressione regolare `^\\d{3}-\\d{3}-\\d{4}$`. Per altre informazioni, vedere [Linguaggio di espressioni regolari - Riferimento rapido](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).  
  
 [!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName>   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Stringhe](../../../csharp/programming-guide/strings/index.md)   
 [Espressioni regolari di .NET Framework](https://msdn.microsoft.com/library/hs600312)   
 [Linguaggio di espressioni regolari - Riferimento rapido](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)

