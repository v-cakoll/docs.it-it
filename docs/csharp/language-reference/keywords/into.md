---
title: into (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: 9bc7d50b77fe42861f92cc5bec946678d11d73d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="into-c-reference"></a>into (Riferimenti per C#)
La parola chiave contestuale `into` può essere usata per creare un identificatore temporaneo al fine di archiviare i risultati di una clausola [group](../../../csharp/language-reference/keywords/group-clause.md), [join](../../../csharp/language-reference/keywords/join-clause.md) o [select](../../../csharp/language-reference/keywords/select-clause.md) in un nuovo identificatore. Questo identificatore può essere un generatore per altri comandi di query. Se usato in una clausola `group` o `select`, l'utilizzo del nuovo identificatore viene talvolta definito *continuazione*.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato l'utilizzo della parola chiave `into` per attivare un identificatore temporaneo `fruitGroup` che contiene un tipo dedotto di `IGrouping`. Usando l'identificatore, è possibile richiamare il metodo <xref:System.Linq.Enumerable.Count%2A> su ogni gruppo e selezionare solo i gruppi che contengono due o più parole.  
  
 [!code-csharp[cscsrefQueryKeywords#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/into_1.cs)]  
  
 L'utilizzo di `into` in una clausola `group` è necessario solo quando si vuole eseguire operazioni di query aggiuntive in ogni gruppo. Per altre informazioni, vedere [Clausola group](../../../csharp/language-reference/keywords/group-clause.md).  
  
 Per un esempio di utilizzo di `into` in una clausola `join`, vedere [Clausola join](../../../csharp/language-reference/keywords/join-clause.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Parole chiave di query (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
 [Espressioni di query LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [Clausola group](../../../csharp/language-reference/keywords/group-clause.md)
