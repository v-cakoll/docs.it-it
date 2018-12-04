---
title: Passaggio di parametri (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
ms.openlocfilehash: 241beb56b0e0f00dae63e12ea775b2b982200efc
ms.sourcegitcommit: 82a3f7882bc03ed733af91fc2a0b113195bf5dc7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2018
ms.locfileid: "44194852"
---
# <a name="passing-parameters-c-programming-guide"></a>Passaggio di parametri (Guida per programmatori C#)
In C# è possibile passare gli argomenti ai parametri per valore o per riferimento. Il passaggio per riferimento consente a membri di funzioni, metodi, proprietà, indicizzatori, operatori e costruttori di modificare il valore dei parametri e rendere permanenti le modifiche nell'ambiente chiamante. Per passare un parametro per riferimento con l'intenzione di modificare il valore, usare la parola chiave `ref` o `out`. Per passare per riferimento con l'intenzione di evitare la copia, ma non la modifica del valore, usare il modificatore `in`. Per semplicità, negli esempi riportati in questo argomento verrà utilizzata soltanto la parola chiave `ref`. Per altre informazioni sulla differenza tra `in`, `ref` e `out`, vedere [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) e [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md).  
  
 L'esempio seguente illustra la differenza fra parametri di valore e di riferimento.  
  
 [!code-csharp[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]  
  
 Per altre informazioni, vedere i seguenti argomenti:  
  
-   [Passaggio di parametri di tipo di valore](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [Passaggio di parametri di tipo di riferimento](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  

Per altre informazioni, vedere [Elenchi di argomenti](~/_csharplang/spec/expressions.md#argument-lists) nella [specifica del linguaggio C#](../../language-reference/language-specification/index.md). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Metodi](../../../csharp/programming-guide/classes-and-structs/methods.md)
