---
title: Passaggio di parametri (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
caps.latest.revision: 17
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
ms.openlocfilehash: 4b8c0c7f7b8c3820edbafbe90fb961c12da8fc84
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="passing-parameters-c-programming-guide"></a>Passaggio di parametri (Guida per programmatori C#)
In C# è possibile passare gli argomenti ai parametri per valore o per riferimento. Il passaggio per riferimento consente a membri di funzioni, metodi, proprietà, indicizzatori, operatori e costruttori di modificare il valore dei parametri e rendere permanenti le modifiche nell'ambiente chiamante. Per passare un parametro per riferimento, usare la parola chiave `ref` o `out`. Per semplicità, negli esempi riportati in questo argomento verrà utilizzata soltanto la parola chiave `ref`. Per altre informazioni sulla differenza tra `ref` e `out`, vedere [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md) e [Passaggio di matrici mediante ref e out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 L'esempio seguente illustra la differenza fra parametri di valore e di riferimento.  
  
 [!code-cs[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]  
  
 Per altre informazioni, vedere i seguenti argomenti:  
  
-   [Passaggio di parametri di tipo di valore](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [Passaggio di parametri di tipo di riferimento](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Metodi](../../../csharp/programming-guide/classes-and-structs/methods.md)

