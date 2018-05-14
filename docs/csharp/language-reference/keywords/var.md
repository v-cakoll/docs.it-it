---
title: var (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: 58c7e29840cfb536e2d1afd48b0ff2ca65b1c0c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="var-c-reference"></a>var (Riferimenti per C#)
A partire da Visual C# 3.0, le variabili dichiarate in corrispondenza dell'ambito del metodo possono contenere un oggetto `var` di"tipo" implicito. Una variabile locale tipizzata in modo implicito è fortemente tipizzata come se si fosse dichiarato il tipo stesso, ma è il compilatore ha determinare il tipo. Le due dichiarazioni seguenti di `i` sono equivalenti dal punto di vista funzionale:  
  
```  
var i = 10; // implicitly typed  
int i = 10; //explicitly typed  
```  
  
 Per altre informazioni, vedere [Variabili locali tipizzate in modo implicito](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) e [Relazioni tra i tipi nelle operazioni di query LINQ](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra due espressioni di query. Nella prima espressione l'uso di `var` è consentito, ma non necessario, perché il tipo del risultato della query può essere dichiarato in modo esplicito come `IEnumerable<string>`. Nella seconda espressione, tuttavia, `var` consente che il risultato sia una raccolta di tipi anonimi e il nome di tale tipo non è accessibile tranne che al compilatore stesso. L'uso di `var` elimina la necessità di creare una nuova classe per il risultato. Si noti che nel secondo esempio anche la variabile di iterazione `foreach``item` deve essere tipizzata in modo implicito.  
  
 [!code-csharp[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Variabili locali tipizzate in modo implicito](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
