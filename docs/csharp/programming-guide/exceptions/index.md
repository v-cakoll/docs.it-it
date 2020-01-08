---
title: Eccezioni e gestione delle eccezioni - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#]
- exceptions [C#]
- C# language, exceptions
ms.assetid: 0001887f-4fa2-47e2-8034-2819477e2344
ms.openlocfilehash: 9229c1524a400112a1b48bc40866d6dd1b7cf21b
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346232"
---
# <a name="exceptions-and-exception-handling-c-programming-guide"></a>Eccezioni e gestione delle eccezioni (Guida per programmatori C#)

Le funzionalità di gestione delle eccezioni del linguaggio C# sono utili per gestire qualsiasi situazione imprevista o eccezionale che può verificarsi durante l'esecuzione di un programma. Per la gestione delle eccezioni vengono usate le parole chiave `try`, `catch` e `finally` per provare a eseguire azioni che potrebbero non riuscire, per gestire gli errori quando si decide che è ragionevole farlo e per pulire le risorse in un secondo momento. Le eccezioni possono essere generate da CLR (Common Language Runtime), da .NET Framework o qualsiasi libreria di terze parti o dal codice dell'applicazione. Per creare le eccezioni viene usata la parola chiave `throw`.

In molti casi, un'eccezione può essere generata non da un metodo che chiamato direttamente dal codice, ma da qualsiasi metodo più in basso nello stack di chiamate. In questo caso, CLR ripercorrerà lo stack alla ricerca di un metodo con un blocco `catch` per il tipo di eccezione specifico ed eseguirà il primo blocco `catch` trovato. Se non trova un blocco `catch` appropriato nello stack di chiamate, terminerà il processo e visualizzerà un messaggio all'utente.

In questo esempio, un metodo verifica la presenza di divisioni per zero e intercetta l'errore. Senza la gestione delle eccezioni, il programma verrebbe chiuso con un errore **DivideByZeroException non è stata gestita**.

[!code-csharp[csProgGuideExceptions#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#18)]

## <a name="exceptions-overview"></a>Panoramica delle eccezioni

Le eccezioni hanno le proprietà seguenti:  

- Le eccezioni sono tipi che derivano fondamentalmente tutti da `System.Exception`.
- Racchiudere all'interno di un blocco `try` le istruzioni che potrebbero generare un'eccezione.
- Quando si verifica un'eccezione nel blocco `try`, il flusso di controllo passa al primo gestore delle eccezioni associato presente in qualsiasi punto nello stack di chiamate. In C#, per definire un gestore di eccezioni viene usata la parola chiave `catch`.
- Se non è presente alcun gestore di eccezioni per una determinata eccezione, il programma interrompe l'esecuzione con un messaggio di errore.
- Non intercettare un'eccezione a meno che non sia possibile gestirla e lasciare l'applicazione in uno stato noto. Se si rilevano `System.Exception`, generarlo nuovamente utilizzando la parola chiave `throw` alla fine del blocco `catch`.
- Se un blocco `catch` definisce una variabile di eccezione, è possibile usarla per ottenere altre informazioni sul tipo di eccezione che si è verificato.
- Le eccezioni possono essere generate in modo esplicito da un programma usando la parola chiave `throw`.
- Gli oggetti eccezione contengono informazioni dettagliate sull'errore, ad esempio lo stato dello stack di chiamate e una descrizione testuale dell'errore.
- Il codice in un blocco `finally` viene eseguito anche se viene generata un'eccezione. Usare un blocco `finally` per rilasciare le risorse, ad esempio per chiudere eventuali flussi o file aperti nel blocco `try`.
- Le eccezioni gestite in .NET Framework vengono implementate sulla base del meccanismo di gestione strutturata delle eccezioni in Win32. Per altre informazioni, vedere [Gestione strutturata delle eccezioni (C/C++)](/cpp/cpp/structured-exception-handling-c-cpp) e [A Crash Course on the Depths of Win32 Structured Exception Handling](https://bytepointer.com/resources/pietrek_crash_course_depths_of_win32_seh.htm) (Corso intensivo su tutti i concetti fondamentali della gestione delle eccezioni strutturata in Win32).

## <a name="related-sections"></a>Sezioni correlate

Per ulteriori informazioni sulle eccezioni e la gestione delle eccezioni, vedere gli articoli seguenti:

- [Uso delle eccezioni](using-exceptions.md)
- [Gestione delle eccezioni](exception-handling.md)
- [Creazione e generazione di eccezioni](creating-and-throwing-exceptions.md)
- [Eccezioni generate dal compilatore](compiler-generated-exceptions.md)
- [Come gestire un'eccezione usando try/catch (C# guida per programmatori)](how-to-handle-an-exception-using-try-catch.md)
- [Come eseguire il codice di pulitura usando infine](how-to-execute-cleanup-code-using-finally.md)
- [Come intercettare un'eccezione non CLS](how-to-catch-a-non-cls-exception.md)

## <a name="c-language-specification"></a>Specifica del linguaggio C#

Per altre informazioni, vedere [Eccezioni](~/_csharplang/spec/exceptions.md) nella [Specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.

## <a name="see-also"></a>Vedere anche

- <xref:System.SystemException>
- [Guida per programmatori C#](../index.md)
- [Parole chiave di C#](../../language-reference/keywords/index.md)
- [throw](../../language-reference/keywords/throw.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
- [Eccezioni](../../../standard/exceptions/index.md)
