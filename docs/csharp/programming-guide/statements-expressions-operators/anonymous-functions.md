---
title: Funzioni anonime - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: cfb0190ee263e65e8130a8925f76357a382eafa3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712000"
---
# <a name="anonymous-functions-c-programming-guide"></a>Funzioni anonime (Guida per programmatori C#)

Una funzione anonima è un'istruzione o un'espressione "inline" che può essere usata in tutti i casi in cui è previsto un tipo delegato. Consente di inizializzare un delegato denominato o passarlo al posto di un tipo delegato denominato come parametro del metodo.

Per creare una funzione anonima, è possibile usare un'[espressione lambda](lambda-expressions.md) o un [metodo anonimo](../../language-reference/operators/delegate-operator.md). È consigliabile usare le espressioni lambda perché forniscono un modo più conciso ed espressivo per scrivere codice inline. A differenza dei metodi anonimi, è possibile convertire alcuni tipi di espressioni lambda nei tipi di albero delle espressioni.

## <a name="the-evolution-of-delegates-in-c"></a>Evoluzione dei delegati in C\#

 In C# 1.0 è stata creata un'istanza di un delegato inizializzandola in modo esplicito con un metodo che è stato definito altrove nel codice. C# 2.0 ha introdotto il concetto di metodi anonimi come modo per scrivere blocchi di istruzioni inline senza nome che possono essere eseguiti in una chiamata a delegati. C# 3.0 ha introdotto le espressioni lambda, che sono concettualmente analoghe ai metodi anonimi, ma più espressive e concise. Queste due funzionalità sono noti collettivamente come *funzioni anonime*. In generale, le applicazioni destinate alla versione 3.5 o successiva di .NET Framework devono usare le espressioni lambda.  
  
 L'esempio seguente illustra l'evoluzione della creazione di delegati da C# 1.0 a C# 3.0:  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Espressioni di funzioni anonime](~/_csharplang/spec/expressions.md#anonymous-function-expressions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).
  
## <a name="see-also"></a>Vedere anche

- [Istruzioni, espressioni e operatori](./index.md)
- [Espressioni lambda](./lambda-expressions.md)
- [Delegati](../delegates/index.md)
- [Alberi delle espressioni (C#)](../concepts/expression-trees/index.md)
