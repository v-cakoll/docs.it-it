---
title: Gestione delle eccezioni - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], handling
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
ms.openlocfilehash: ee1e5bd15183dad9ffe97824f9b194668e9d3b17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705301"
---
# <a name="exception-handling-c-programming-guide"></a>Gestione delle eccezioni (Guida per programmatori C#)
I programmatori C# usano un blocco [try](../../language-reference/keywords/try-catch.md) per creare partizioni di codice in cui potrebbe essere rilevata un'eccezione. I blocchi [catch](../../language-reference/keywords/try-catch.md) associati vengono usati per gestire tutte le eccezioni risultanti. Un blocco [finally](../../language-reference/keywords/try-finally.md) contiene il codice eseguito, indipendentemente dal fatto che venga generata o meno un'eccezione nel blocco `try`, ad esempio il codice relativo al rilascio delle risorse allocate nel blocco `try`. Un blocco `try` richiede uno o più blocchi `catch` associati, un blocco `finally` o entrambi.  
  
 Gli esempi seguenti illustrano un'istruzione `try-catch`, un'istruzione `try-finally` e un'istruzione `try-catch-finally`.  
  
 [!code-csharp[csProgGuideExceptions#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#6)]  
  
 [!code-csharp[csProgGuideExceptions#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#7)]  
  
 [!code-csharp[csProgGuideExceptions#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#8)]  
  
 Un blocco `try` senza un blocco `catch` o `finally` genera un errore del compilatore.  
  
## <a name="catch-blocks"></a>Blocchi catch  
 Un blocco `catch` consente di specificare il tipo di eccezione da intercettare. La specifica del tipo è chiamata *filtro eccezioni*. Il tipo di eccezione deve essere derivato da <xref:System.Exception>. In genere, specificare <xref:System.Exception> come filtro eccezioni solo se si sa come gestire tutte le eccezioni che potrebbero essere generate nel blocco `try` o se si è inclusa un'istruzione [throw](../../language-reference/keywords/throw.md) alla fine del blocco `catch`.  
  
 È possibile concatenare più blocchi `catch` con filtri eccezioni diversi. I blocchi `catch` vengono valutati dall'alto verso il basso nel codice, ma viene eseguito un solo blocco `catch` per ogni eccezione generata, in particolare il primo blocco `catch` che specifica il tipo esatto o una classe di base dell'eccezione generata. Se nessun blocco `catch` specifica un filtro eccezioni corrispondente, viene selezionato un blocco `catch` che non dispone di filtro, se presente nell'istruzione. È importante posizionare per primi i blocchi `catch` con i tipi di eccezione più specifici (ossia i più derivati).  
  
 È necessario intercettare le eccezioni quando le condizioni seguenti sono vere:  
  
- Si è compreso il motivo per cui è stata generata l'eccezione ed è possibile implementare un recupero specifico, ad esempio chiedendo all'utente di immettere un nuovo nome di file quando si intercetta un oggetto <xref:System.IO.FileNotFoundException>.  
  
- È possibile creare e generare una nuova eccezione più specifica.  
  
     [!code-csharp[csProgGuideExceptions#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#9)]  
  
- Si vuole gestire parzialmente un'eccezione prima di passarla a funzioni di gestione aggiuntive. Nell'esempio seguente un blocco `catch` viene usato per aggiungere una voce al log degli errori prima di generare di nuovo l'eccezione.  
  
     [!code-csharp[csProgGuideExceptions#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#10)]  
  
## <a name="finally-blocks"></a>Blocchi finally  
 Un blocco `finally` consente la pulizia delle azioni eseguite in un blocco `try`. Se presente, il blocco `finally` viene eseguito per ultimo, dopo il blocco `try` e i blocchi `catch` corrispondenti. Un blocco `finally` viene sempre eseguito, sia che venga o meno generata un'eccezione o che venga o meno individuato un blocco `catch` corrispondente al tipo di eccezione.  
  
 Il blocco `finally` può essere usato per rilasciare risorse quali flussi di file, connessioni di database e handle di elementi grafici, senza attendere che il Garbage Collector del runtime finalizzi gli oggetti. Per altre informazioni, vedere [Istruzione using](../../language-reference/keywords/using-statement.md).  
  
 Nell'esempio riportato di seguito viene usato il blocco `finally` per chiudere un file aperto nel blocco `try`. Si noti che prima della chiusura viene controllato lo stato dell'handle del file. Se il blocco `try` non riesce ad aprire il file, l'handle del file ha sempre valore `null` e il blocco `finally` non tenta di chiuderlo. In alternativa, se il file è aperto correttamente nel blocco `try`, il blocco `finally` chiude il file aperto.  
  
 [!code-csharp[csProgGuideExceptions#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#11)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  

Per altre informazioni, vedere [Eccezioni](~/_csharplang/spec/exceptions.md) e [Istruzione throw](~/_csharplang/spec/statements.md#the-try-statement) in [Specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.
  
## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../../language-reference/index.md)
- [Guida per programmatori C#](../index.md)
- [Eccezioni e gestione delle eccezioni](./index.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try...finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
- [Istruzione using](../../language-reference/keywords/using-statement.md)
