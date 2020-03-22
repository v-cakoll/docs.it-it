---
title: Procedure dettagliate del linguaggioLanguage Walkthroughs
description: Istruzioni dettagliate per scenari comuni nello sviluppo di Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, walkthroughs
- examples [Visual Basic]
- Visual Basic code, walkthroughs
- walkthroughs [Visual Basic]
ms.assetid: e4e1f849-e1ce-4cf7-8483-d9b4c4887a8e
ms.openlocfilehash: 76f9b428bc5f613296e24d893f49f124bb13c089
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75636042"
---
# <a name="visual-basic-language-walkthroughs"></a>Procedure dettagliate relative al linguaggio Visual Basic

Le procedure dettagliate forniscono istruzioni specifiche per scenari comuni, che li rende un ottimo strumento per apprendere l'utilizzo del prodotto o di una determinata area funzionale.

- [Scrittura di un programma asincrono](./programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  
 Viene illustrato come creare una soluzione asincrona utilizzando [Async](language-reference/modifiers/async.md) e [Await](language-reference/operators/await-operator.md).

- [Dichiarazione e generazione di eventi](programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)  
 Illustra come dichiarare e generare eventi in Visual Basic.

- [Gestione degli eventiHandling Events](programming-guide/language-features/events/walkthrough-handling-events.md)  
 Spiega come gestire gli eventi usando la parola chiave standard `WithEvents` o le nuove parole chiave `AddHandler`/`RemoveHandler`.

- [Creazione e implementazione di interfacce](programming-guide/language-features/interfaces/walkthrough-creating-and-implementing-interfaces.md)  
 Illustra come dichiarare e implementare le interfacce in Visual Basic.

- [Definizione delle classi](programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)  
 Descrive la procedura di dichiarazione di una classe e dei relativi campi, proprietà, metodi ed eventi.

- [Scrittura delle query in Visual Basic](programming-guide/concepts/linq/walkthrough-writing-queries.md)  
 Viene illustrato come utilizzare le funzionalità del linguaggio Visual Basic per scrivere espressioni di query LINQ (Language-Integrated Query).

- [Implementazione di IEnumerable(Of T) in Visual Basic](programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md)  
 Viene illustrato come creare una classe che implementa l'interfaccia `IEnumerable(Of String)` e una classe che implementa l'interfaccia `IEnumerator(Of String)` per leggere un file di testo una riga alla volta.

- [Chiamata delle API di Windows](programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 Spiega come usare le istruzioni `Declare` e chiamare le API di Windows. Include informazioni sull'uso degli attributi per controllare il marshalling per la chiamata API e su come esporre una chiamata API come metodo di una classe.

- [Creazione di oggetti COM con Visual Basic](programming-guide/com-interop/walkthrough-creating-com-objects.md)  
 Illustra come creare oggetti COM in Visual Basic, con e senza il modello di classe COM.

- [Implementazione dell'ereditarietà con gli oggetti COM](programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 Spiega come usare Visual Basic 6.0 per creare un oggetto COM contenente una classe che verrà poi usata come classe di base in Visual Basic.

- [Determinazione della posizione in cui My.Application.Log scrive informazioniDetermining Where My.Application.Log Writes Information](developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)  
 Descrive le impostazioni predefinite di `My.Application.Log` e spiega come determinare le impostazioni dell'applicazione.

- [Modifica della posizione in cui my.Application.Log scrive informazioni](developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)  
 Spiega come eseguire l'override delle impostazioni predefinite di `My.Application.Log` e `My.Log` per registrare le informazioni sull'evento e fare in modo che l'oggetto `Log` scriva in altri listener di log.

- [Filtraggio dell'output di My.Application.LogFiltering My.Application.Log Output](developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)  
 Viene illustrato come modificare il filtro di log predefinito per l'oggetto `My.Application.Log`.

- [Creazione di listener di log personalizzatiCreating Custom Log Listeners](developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)  
 Spiega come creare un listener di log personalizzato e configurarlo in modo che resti in ascolto dell'output dell'oggetto `My.Application.Log`.

- [Incorporamento dei tipi da assembly gestiti](../standard/assembly/embed-types-visual-studio.md)  
 Viene descritto come creare un assembly e un programma client che ne incorpori i tipi.

- [Verifica della complessità delle password (Visual Basic)](programming-guide/language-features/strings/walkthrough-validating-that-passwords-are-complex.md)  
 Spiega come verificare le caratteristiche delle password complesse e aggiornare un parametro di stringa con le informazioni sui controlli che una password non ha superato.

- [Crittografia e decrittografia di stringhe in Visual Basic](programming-guide/language-features/strings/walkthrough-encrypting-and-decrypting-strings.md)  
 Illustra come usare la classe <xref:System.Security.Cryptography.DESCryptoServiceProvider> per crittografare e decrittografare le stringhe.

- [Modifica di file e cartelle in Visual Basic](developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)  
 Illustra come usare le funzioni Visual Basic per determinare informazioni su un file, cercare una stringa in un file e scrivere in un file.

- [Modifica di file mediante i metodi .NET Framework](developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)  
 Illustra come usare i metodi .NET Framework per determinare informazioni su un file, cercare una stringa in un file e scrivere in un file.

- [Persistenza di un oggetto in Visual Basic](programming-guide/concepts/serialization/walkthrough-persisting-an-object-in-visual-studio.md)  
 Viene illustrato come creare un oggetto semplice e rendere persistenti i relativi dati in un file.

- [Procedura dettagliata: supporto test preliminare con la funzionalità di generazione dall'uso](/visualstudio/ide/walkthrough-test-first-support-with-the-generate-from-usage-feature)  
 Spiega come eseguire uno sviluppo con test preliminare, in cui prima si scrivono gli unit test e successivamente il codice sorgente in modo che il test abbia esito positivo.
