---
title: Espressioni con valore predefinito (Guida per programmatori C#)
description: Le espressioni con valore predefinito producono il valore predefinito per qualsiasi tipo riferimento o tipo valore
ms.date: 2017-08-23
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 0dc2fcee3903b80816c98bab47e2b9a2e5ef78b0
ms.openlocfilehash: 7b5b53d7ed92c6f6377a3e494daf1d02a4cf0934
ms.contentlocale: it-it
ms.lasthandoff: 08/28/2017

---
# <a name="default-value-expressions-c-programming-guide"></a>espressioni con valore predefinito (guida per programmatori C#)

Un'espressione con valore predefinito produce il valore predefinito per un tipo. Le espressioni con valore predefinito risultano particolarmente utili nelle classi e nei metodi generici. Un problema relativo all'uso dei metodi generici riguarda l'assegnazione di un valore predefinito a un tipo con parametri `T` quando non è noto quanto segue:

- Se `T` è un tipo riferimento o un tipo valore.
- Nel caso in cui `T` sia un tipo valore, se è un valore numerico o uno struct definito dall'utente.

 Data una variabile `t` di un tipo con parametri `T`, l'istruzione `t = null` è valida solo se `T` è un tipo riferimento. L'assegnazione `t = 0` funziona solo per i tipi di valore numerico ma non per gli struct. La soluzione consiste nell'usare un'espressione con valore predefinito, che restituisce `null` per i tipi di riferimento (tipi di classe e tipi di interfaccia) e zero per i tipi di valore numerico. Per gli struct definiti dall'utente restituisce lo struct inizializzato in base allo schema di bit zero, che produce 0 o `null` per ogni membro, in base al fatto che il tipo del membro sia valore o riferimento. Per i tipi di valore nullable, `default` restituisce <xref:System.Nullable%601?displayProperty=fullName>, che viene inizializzato come qualsiasi struct.

L'espressione `default(T)` non è limitata a classi e metodi generici. Le espressioni con valore predefinito possono essere usate con qualsiasi tipo gestito. Tutte le espressioni seguenti sono valide:

 [!code-cs[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]

 L'esempio seguente dalla classe `GenericList<T>` mostra come usare l'operatore `default(T)` in una classe generica. Per altre informazioni, vedere [Generics Overview](../generics/introduction-to-generics.md) (Panoramica dei generics).

 [!code-cs[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]

## <a name="default-literal-and-type-inference"></a>Valore letterale e inferenza del tipo

A partire dalla versione C# 7.1, il valore letterale `default` può essere usato per le espressioni con valore predefinito quando il compilatore è in grado di eseguire l'inferenza del tipo dell'espressione. Il valore letterale `default` produce lo stesso valore dell'equivalente `default(T)` dove `T` è il tipo dedotto. Questo approccio può consentire di rendere più conciso il codice, riducendo la ridondanza dovuta alla dichiarazione ripetuta di un tipo. Il valore letterale `default` può essere usato in una qualsiasi delle posizioni seguenti:

- Inizializzatore di variabile
- assegnazione di variabili
- Dichiarazione del valore predefinito per un parametro facoltativo
- Specifica del valore per l'argomento della chiamata di un metodo
- Istruzione return (o espressione in un membro con corpo di espressione)

L'esempio seguente mostra molti utilizzi del valore letterale `default` in un'espressione con valore predefinito:

[!code-cs[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]

## <a name="see-also"></a>Vedere anche

 <xref:System.Collections.Generic> [Guida per programmatori C#](../index.md)   
 [Generics](../generics/index.md)   
 [Metodi generici](../generics/generic-methods.md)   
 [Generics](~/docs/standard/generics/index.md)   

