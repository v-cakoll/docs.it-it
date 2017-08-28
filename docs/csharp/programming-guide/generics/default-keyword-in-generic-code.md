---
title: Parola chiave default in codice generico (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b5f5995b720d377717a5fff8a5e7e6e2196c612c
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="default-keyword-in-generic-code-c-programming-guide"></a>Parola chiave default in codice generico (Guida per programmatori C#)
Un problema comune con le classi e i metodi generici riguarda l'assegnazione di un valore predefinito a un tipo con parametri T quando non è noto quanto segue:  
  
-   Se T sarà un tipo riferimento o un tipo valore.  
  
-   Se T è un tipo valore, se sarà un valore numerico o uno struct.  
  
 Considerando una variabile t di un tipo con parametri T, l'istruzione t = null è valida solo se T è un tipo riferimento, mentre t = 0 è valida solo per i tipi valore numerici e non per gli struct. La soluzione consiste nell'usare la parola chiave `default`, che restituisce null per i tipi riferimento e zero per i tipi valore numerici. Per gli struct, la parola chiave restituisce ogni membro dello struct inizializzato in zero o null, a seconda che si tratti di tipi valore o tipi riferimento. Per i tipi valore nullable, default restituisce <xref:System.Nullable%601?displayProperty=fullName>, che viene inizializzato come qualsiasi struct.  
  
 L'esempio seguente dalla classe `GenericList<T>` mostra come usare la parola chiave `default`. Per altre informazioni, vedere [Generics Overview](../../../csharp/programming-guide/generics/introduction-to-generics.md) (Panoramica dei generics).  
  
 [!code-cs[csProgGuideGenerics#41](../../../csharp/programming-guide/generics/codesnippet/CSharp/default-keyword-in-generic-code_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Collections.Generic>   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Generics](../../../csharp/programming-guide/generics/index.md)   
 [Metodi generici](../../../csharp/programming-guide/generics/generic-methods.md)   
 [Generics](~/docs/standard/generics/index.md)

