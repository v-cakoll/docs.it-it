---
title: Gestione e generazione di eccezioni
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions [.NET Framework], handling
- runtime, exceptions
- filtering exceptions
- errors [.NET Framework], exceptions
- exceptions [.NET Framework], throwing
- exceptions [.NET Framework]
- common language runtime, exceptions
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b71ffd9bfcfcb048f148ac1a3a418c03b9834ea2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575453"
---
# <a name="handling-and-throwing-exceptions-in-net"></a>Gestione e generazione di eccezioni in .NET

Le applicazioni devono essere in grado di gestire in modo coerente gli errori che si verificano durante l'esecuzione. .NET offre un modello coerente per l'invio alle applicazioni di notifiche relative agli errori: le operazioni di .NET indicano l'errore generando eccezioni.

## <a name="exceptions"></a>Eccezioni

Un'eccezione è una condizione di errore o un comportamento imprevisto riscontrato da un programma in esecuzione. Le eccezioni possono essere generate in caso di errori nel codice dell'applicazione o nel codice chiamato (ad esempio una libreria condivisa), in caso di risorse del sistema operativo non disponibili, di condizioni impreviste riscontrate dal runtime (ad esempio codice impossibile da verificare) e così via. L'applicazione è in grado di gestire alcune di queste condizioni, altre no. Sebbene sia possibile gestire gran parte delle eccezioni dell'applicazione, la maggior parte delle eccezioni di runtime risulta ingestibile.

In .NET un'eccezione è un oggetto che eredita dalla classe <xref:System.Exception?displayProperty=nameWithType>. Le eccezioni vengono generate dalle aree di codice in cui si è verificato un problema. Ogni eccezione viene passata ai livelli superiori dello stack finché non viene gestita dall'applicazione o non si arresta il programma.

## <a name="exceptions-vs-traditional-error-handling-methods"></a>Confronto tra eccezioni e metodi di gestione degli errori tradizionali

In precedenza, il modello di gestione degli errori di un linguaggio si basava sul metodo specifico usato da tale linguaggio per rilevare gli errori e individuarne i gestori oppure sul meccanismo di gestione degli errori fornito dal sistema operativo. La modalità di gestione delle eccezioni di .NET offre i vantaggi seguenti:

- La generazione e la gestione delle eccezioni ha lo stesso funzionamento nei linguaggi di programmazione .NET.

- Senza la necessità di una sintassi di linguaggio apposita, ma con la possibilità per ciascun linguaggio di definire la propria sintassi.

- È possibile generare eccezioni anche a livello di più processi e addirittura di più computer differenti.

- È possibile aggiungere codice per la gestione delle eccezioni a un'applicazione per aumentare l'affidabilità dei programmi.

Le eccezioni presentano vantaggi rispetto ad altri metodi di notifica degli errori, quali i codici restituiti. Gli errori vengono sempre rilevati poiché se viene generata un'eccezione e l'eccezione non viene gestita, il runtime termina l'applicazione. I valori non validi non continuano a propagarsi nel sistema quando il codice non riesce a verificare la presenza di un codice di errore restituito. 

## <a name="common-exceptions"></a>Eccezioni comuni

Nella tabella seguente sono elencate alcune eccezioni comuni con esempi di possibili cause.

| Tipo di eccezione | Tipo base | Descrizione | Esempio |
| -------------- | --------- | ----------- | ------- |
| <xref:System.Exception> | <xref:System.Object> | Classe base per tutte le eccezioni. | Nessuno (usare una classe derivata di questa eccezione). |
| <xref:System.IndexOutOfRangeException> | <xref:System.Exception> | Generata dal runtime solo quando una matrice viene indicizzata in modo non corretto. | Indicizzazione di una matrice esternamente al relativo intervallo valido: `arr[arr.Length+1]` |
| <xref:System.NullReferenceException> | <xref:System.Exception> | Generata dal runtime solo quando viene fatto riferimento a un oggetto Null. | `object o = null; o.ToString();` |
| <xref:System.InvalidOperationException> | <xref:System.Exception> | Generata dai metodi con uno stato non valido. | Chiamata di `Enumerator.GetNext()` dopo la rimozione di un elemento dalla raccolta sottostante. |
| <xref:System.ArgumentException> | <xref:System.Exception> | Classe base per tutte le eccezioni di argomento. | Nessuno (usare una classe derivata di questa eccezione). |
| <xref:System.ArgumentNullException> | <xref:System.Exception> | Generata dai metodi che non consentono un argomento Null. | `String s = null; "Calculate".IndexOf (s);` |
| <xref:System.ArgumentOutOfRangeException> | <xref:System.Exception> | Generata dai metodi che verificano se gli argomenti sono compresi in un determinato intervallo. | `String s = "string"; s.Substring(s.Length+1);` |

## <a name="see-also"></a>Vedere anche

* [Classe e proprietà dell'eccezione](exception-class-and-properties.md)
* [Procedura: Usare il blocco try/catch per l'intercettazione di eccezioni](how-to-use-the-try-catch-block-to-catch-exceptions.md)
* [Procedura: Usare eccezioni specifiche in un blocco catch](how-to-use-specific-exceptions-in-a-catch-block.md)
* [Procedura: Come generare in modo esplicito le eccezioni](how-to-explicitly-throw-exceptions.md)
* [Procedura: Creare eccezioni definite dall'utente](how-to-create-user-defined-exceptions.md)
* [Uso di gestori eccezioni filtrati dall'utente](using-user-filtered-exception-handlers.md)
* [Procedura: Usare blocchi Finally](how-to-use-finally-blocks.md)
* [Gestione di eccezioni per interoperabilità COM](handling-com-interop-exceptions.md)
* [Procedure consigliate per le eccezioni](best-practices-for-exceptions.md)

Per altre informazioni sull'uso delle eccezioni in .NET, vedere [What Every Dev needs to Know About Exceptions in the Runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/exceptions.md) (Informazioni per gli sviluppatori sulle eccezioni nel runtime).
