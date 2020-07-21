---
title: Costruttori - Guida per programmatori C#
description: Un costruttore in C# viene chiamato quando viene creata una classe o uno struct. Utilizzare i costruttori per impostare i valori predefiniti, limitare la creazione di istanze e scrivere codice flessibile e di facile lettura.
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: 4a731e648143f5e0ecf8860625962d8baa29fe26
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474904"
---
# <a name="constructors-c-programming-guide"></a>Costruttori (Guida per programmatori C#)

Quando si crea una [classe](../../language-reference/keywords/class.md) o uno [struct](../../language-reference/builtin-types/struct.md), viene chiamato il relativo costruttore. Una classe o uno struct può avere più costruttori che accettano argomenti diversi. I costruttori consentono al programmatore di impostare i valori predefiniti, limitare la creazione di istanze e scrivere codice flessibile e facile da leggere. Per altre informazioni ed esempi, vedere [Utilizzo di costruttori](./using-constructors.md) e [Costruttori di istanze](./instance-constructors.md).  

## <a name="parameterless-constructors"></a>Costruttori senza parametri
  
Se non si specifica un costruttore per la classe, C# ne crea uno per impostazione predefinita che crea un'istanza dell'oggetto e imposta le variabili membro sui valori predefiniti elencati nell'articolo [valori predefiniti di tipi C#](../../language-reference/builtin-types/default-values.md) . Se non si specifica un costruttore per lo struct, C# si basa su un *costruttore senza parametri implicito* per inizializzare automaticamente ogni campo sul valore predefinito. Per ulteriori informazioni ed esempi, vedere [costruttori di istanze](instance-constructors.md).  

## <a name="constructor-syntax"></a>Sintassi del costruttore

Un costruttore è un metodo il cui nome è identico al nome del tipo relativo. La firma di questo metodo include solo il nome metodo e l'elenco dei parametri, ma non include un tipo restituito. L'esempio seguente illustra il costruttore di una classe denominata `Person`.

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

Se un costruttore può essere implementato come istruzione unica, è possibile usare una [definizione del corpo dell'espressione](../statements-expressions-operators/expression-bodied-members.md). L'esempio seguente definisce una classe `Location` il cui costruttore ha un solo parametro di stringa denominato *name*. La definizione del corpo dell'espressione assegna l'argomento al campo `locationName`.

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a>Costruttori statici

Tutti gli esempi precedenti hanno illustrato costruttori di istanza, che creano un nuovo oggetto. Una classe o uno struct può avere anche un costruttore statico, che inizializza i membri statici del tipo.  I costruttori statici non hanno parametri. Se non si fornisce un costruttore statico per inizializzare i campi statici, il compilatore C# Inizializza i campi statici sul valore predefinito come elencato nell'articolo [valori predefiniti di tipi C#](../../language-reference/builtin-types/default-values.md) .

L'esempio seguente usa un costruttore statico per inizializzare un campo statico.

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

È anche possibile definire un costruttore statico con una definizione di corpo dell'espressione, come illustrato nell'esempio seguente.

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

Per altre informazioni, vedere [Costruttori statici](./static-constructors.md).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Utilizzo di costruttori](./using-constructors.md)  
  
 [Costruttori di istanza](./instance-constructors.md)  
  
 [Costruttori privati](./private-constructors.md)  
  
 [Costruttori statici](./static-constructors.md)  
  
 [Come scrivere un costruttore di copia](./how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](./index.md)
- [Finalizzatori](./destructors.md)
- [static](../../language-reference/keywords/static.md)
- [Perché gli inizializzatori vengono eseguiti nell'ordine opposto come costruttori? Parte 1](https://docs.microsoft.com/archive/blogs/ericlippert/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)
