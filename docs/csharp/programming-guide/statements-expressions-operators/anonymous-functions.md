---
title: Funzioni anonime - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: f7ab471514cd437b7b1816d7e0bde30459f281a9
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2019
ms.locfileid: "57203324"
---
# <a name="anonymous-functions-c-programming-guide"></a>Funzioni anonime (Guida per programmatori C#)
Una funzione anonima è un'istruzione o un'espressione "inline" che può essere usata in tutti i casi in cui è previsto un tipo delegato. Consente di inizializzare un delegato denominato o passarlo al posto di un tipo delegato denominato come parametro del metodo.  
  
 Ci sono due tipi di funzioni anonime, illustrati singolarmente negli argomenti seguenti:  
  
-   [Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
  
-   [Metodi anonimi](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  Le espressioni lambda possono essere associate ad alberi di espressioni e a delegati.  
  
## <a name="the-evolution-of-delegates-in-c"></a>Evoluzione dei delegati in C\#
 In C# 1.0 è stata creata un'istanza di un delegato inizializzandola in modo esplicito con un metodo che è stato definito altrove nel codice. C# 2.0 ha introdotto il concetto di metodi anonimi come modo per scrivere blocchi di istruzioni inline senza nome che possono essere eseguiti in una chiamata a delegati. C# 3.0 ha introdotto le espressioni lambda, che sono concettualmente analoghe ai metodi anonimi, ma più espressive e concise. Queste due funzionalità sono noti collettivamente come *funzioni anonime*. In generale, le applicazioni destinate alla versione 3.5 o successiva di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] devono usare le espressioni lambda.  
  
 L'esempio seguente illustra l'evoluzione della creazione di delegati da C# 1.0 a C# 3.0:  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzioni, espressioni e operatori](../../../csharp/programming-guide/statements-expressions-operators/index.md)
- [Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
- [Delegati](../../../csharp/programming-guide/delegates/index.md)
- [Alberi delle espressioni (C#)](../concepts/expression-trees/index.md)
