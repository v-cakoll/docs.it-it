---
title: Costruttori - Guida per programmatori C#
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: 9c57ff6dd9acd8a8bcff6de4fce7d898f1135703
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714959"
---
# <a name="constructors-c-programming-guide"></a>Costruttori (Guida per programmatori C#)

Quando si crea una [classe](../../language-reference/keywords/class.md) o uno [struct](../../language-reference/keywords/struct.md), viene chiamato il relativo costruttore. Una classe o uno struct può avere più costruttori che accettano argomenti diversi. I costruttori consentono al programmatore di impostare i valori predefiniti, limitare la creazione di istanze e scrivere codice flessibile e facile da leggere. Per altre informazioni ed esempi, vedere [Utilizzo di costruttori](./using-constructors.md) e [Costruttori di istanze](./instance-constructors.md).  

## <a name="parameterless-constructors"></a>Costruttori senza parametri
  
Se non si specifica un costruttore per la classe, C# ne definisce uno per impostazione predefinita che crea istanze dell'oggetto e imposta le variabili dei membri sui valori predefiniti elencati nella [tabella dei valori predefiniti](../../language-reference/keywords/default-values-table.md). Se non si specifica un costruttore per lo struct, C# usa un *costruttore senza parametri implicito* per inizializzare automaticamente ogni campo di un tipo valore sul rispettivo valore predefinito indicato nella [tabella dei valori predefiniti](../../language-reference/keywords/default-values-table.md). Per altre informazioni, vedere [Costruttori di istanze](./instance-constructors.md).  

## <a name="constructor-syntax"></a>Sintassi del costruttore

Un costruttore è un metodo il cui nome è identico al nome del tipo relativo. La firma di questo metodo include solo il nome metodo e l'elenco dei parametri, ma non include un tipo restituito. L'esempio seguente illustra il costruttore di una classe denominata `Person`.

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

Se un costruttore può essere implementato come istruzione unica, è possibile usare una [definizione del corpo dell'espressione](../statements-expressions-operators/expression-bodied-members.md). L'esempio seguente definisce una classe `Location` il cui costruttore ha un solo parametro di stringa denominato *name*. La definizione del corpo dell'espressione assegna l'argomento al campo `locationName`.

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a>Costruttori statici

Tutti gli esempi precedenti hanno illustrato costruttori di istanza, che creano un nuovo oggetto. Una classe o uno struct può avere anche un costruttore statico, che inizializza i membri statici del tipo.  I costruttori statici non hanno parametri. Se non si specifica un costruttore statico per inizializzare campi statici, il compilatore C# inizializza i campi statici sul relativo valore predefinito come indicato nella [tabella dei valori predefiniti](../../language-reference/keywords/default-values-table.md).

L'esempio seguente usa un costruttore statico per inizializzare un campo statico.

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

È anche possibile definire un costruttore statico con una definizione di corpo dell'espressione, come illustrato nell'esempio seguente. 

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

Per altre informazioni, vedere [Costruttori statici](./static-constructors.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Uso dei costruttori](./using-constructors.md)  
  
 [Costruttori di istanza](./instance-constructors.md)  
  
 [Costruttori privati](./private-constructors.md)  
  
 [Costruttori statici](./static-constructors.md)  
  
 [Come scrivere un costruttore di copia](./how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](./index.md)
- [Finalizzatori](./destructors.md)
- [static](../../language-reference/keywords/static.md)
- [Perché gli inizializzatori vengono eseguiti nell'ordine opposto come costruttori? Parte 1](https://blogs.msdn.microsoft.com/ericlippert/2008/02/15/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)
