---
title: Metodi anonimi (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- anonymous methods [C#]
- methods [C#], anonymous
- delegates [C#], anonymous methods
ms.assetid: a62441fa-f0a3-4acb-9aa6-93762a635275
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 96e78257c5aab84562cd8cdb336bb5a91ba59534
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2018
---
# <a name="anonymous-methods-c-programming-guide"></a>Metodi anonimi (Guida per programmatori C#)
Nelle versioni di C# precedenti alla 2.0, l'unico modo per dichiarare un [delegato](../../../csharp/language-reference/keywords/delegate.md) consiste nell'usare [metodi denominati](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md). In C# 2.0 sono stati introdotti i metodi anonimi e in C# versione 3.0 e successive le espressioni lambda sostituiscono i metodi anonimi come modalità preferita per la scrittura di codice inline. Le informazioni sui metodi anonimi in questo argomento, tuttavia, si applicano anche alle espressioni lambda. Esiste un caso in cui un metodo anonimo fornisce funzionalità non disponibili nelle espressioni lambda. I metodi anonimi consentono di omettere l'elenco di parametri. Ciò significa che un metodo anonimo può essere convertito in delegati con un'ampia gamma di firme. Questo non è possibile con le espressioni lambda. Per altre informazioni specifiche sulle espressioni lambda, vedere [Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 La creazione di metodi anonimi è essenzialmente un modo per passare un blocco di codice come un parametro del delegato. Di seguito sono riportati due esempi:  
  
 [!code-csharp[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_1.cs)]  
  
 [!code-csharp[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_2.cs)]  
  
 L'uso dei metodi anonimi consente di ridurre il carico di scrittura del codice correlato alla creazione di istanze dei delegati, perché non è necessario creare un metodo separato.  
  
 Specificare un blocco di codice invece di un delegato, ad esempio, può rivelarsi utile in una situazione in cui la creazione di un metodo può sembrare un sovraccarico inutile. Un buon esempio può essere l'avvio di un nuovo thread. Questa classe crea un thread e contiene anche il codice eseguito dal thread senza creare un metodo aggiuntivo per il delegato.  
  
 [!code-csharp[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_3.cs)]  
  
## <a name="remarks"></a>Note  
 L'ambito dei parametri di un metodo anonimo è il *blocco del metodo anonimo*.  
  
 È errato inserire all'interno del blocco del metodo anonimo un'istruzione di salto come [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md) o [continue](../../../csharp/language-reference/keywords/continue.md), se la destinazione è esterna al blocco. È un errore anche inserire all'esterno del blocco del metodo anonimo un'istruzione di salto come `goto`, `break` o `continue`, se la destinazione è interna al blocco.  
  
 Le variabili e i parametri locali, il cui ambito contiene una dichiarazione di metodo anonimo, sono denominati variabili *esterne* del metodo anonimo. Nel segmento di codice seguente, ad esempio, `n` è una variabile esterna:  
  
 [!code-csharp[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_4.cs)]  
  
 Un riferimento alla variabile esterna `n` viene detto *acquisito* al momento della creazione del delegato. A differenza delle variabili locali, la durata di una variabile acquisita si estende fino a quando i delegati che fanno riferimento ai metodi anonimi sono idonei per l'operazione di Garbage Collection.  
  
 Un metodo anonimo non può accedere ai parametri [in](../../../csharp/language-reference/keywords/in.md), [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) di un ambito esterno.  
  
 Nessun codice non gestito è accessibile all'interno di un *blocco di metodo anonimo*.  
  
 I metodi anonimi non sono consentiti a sinistra dell'operatore [is](../../../csharp/language-reference/keywords/is.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente dimostra due modi per creare un'istanza di un delegato:  
  
-   Associazione del delegato a un metodo anonimo.  
  
-   Associazione del delegato con un metodo denominato (`DoWork`).  
  
 In ogni caso, viene visualizzato un messaggio quando viene richiamato il delegato.  
  
 [!code-csharp[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_5.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Delegati](../../../csharp/programming-guide/delegates/index.md)  
 [Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
 [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [Metodi](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [Delegati con metodi denominati o metodi anonimi](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)
