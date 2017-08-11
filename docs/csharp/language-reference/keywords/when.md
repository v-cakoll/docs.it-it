---
title: when (Riferimenti per C#)
ms.date: 2017-03-07
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- when_CSharpKeyword
- when
dev_langs:
- CSharp
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
caps.latest.revision: 30
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
ms.openlocfilehash: ae869fa04d2dfb963694f258624c5cd594ff1184
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
 # <a name="when-c-reference"></a>when (Riferimenti per C#)

È possibile usare la parola chiave contestuale `when` per specificare una condizione di filtro in due contesti:

- Nell'istruzione `catch` di un blocco [try/catch](try-catch.md) o [try/catch/finally](try-catch-finally.md).
- Nell'etichetta `case` di un'istruzione [switch](switch.md).

## <a name="when-in-a-catch-statement"></a>`when` in un'istruzione `catch`

A partire da C# 6 `When` può essere usata in un'istruzione `catch` per specificare una condizione che deve essere vera per eseguire il gestore di una determinata eccezione. La sintassi è la seguente:

```csharp
catch ExceptionType [e] when (expr)
```
dove *expr* è un'espressione che dà come risultato un valore booleano. Se restituisce `true`, il gestore di eccezioni viene eseguito, se restituisce `false`, non viene eseguito. 

Nell'esempio seguente viene usata la parola chiave `when` per eseguire in modo condizionale i gestori per un elemento @System.Net.HttpRequestException in base al testo del messaggio dell'eccezione.

 [!code-cs[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]  
  
## <a name="when-in-a-switch-statement"></a>`when` in un'istruzione `switch`

A partire da 7 non è più necessario che le etichette `case` siano reciprocamente esclusive e l'ordine in cui le etichette `case` appaiono in un'istruzione `switch` può determinare quale blocco switch eseguire. La parola chiave `when` può essere usata per specificare una condizione di filtro che fa sì che l'etichetta case associata sia vera solo se è vera anche la condizione di filtro. La sintassi è la seguente:

```csharp
case (expr) when (when-condition):
```
dove *expr* è un modello costante o un modello del tipo che viene confrontato con l'espressione di corrispondenza e *when-condition* è qualsiasi espressione booleana. 

Nell'esempio seguente viene usata la parola chiave `when` per testare gli oggetti `Shape` che hanno un'area pari a zero, nonché una varietà di oggetti `Shape` che hanno un'area maggiore di zero. 

 [!code-cs[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]  

## <a name="see-also"></a>Vedere anche 
  [Istruzione switch](switch.md)  
  [Istruzione try/catch](try-catch.md)  
  [Istruzione try/catch/finally](try-catch-finally.md) 


