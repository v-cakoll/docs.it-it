---
title: Debug, traccia e profilatura
ms.date: 03/30/2017
helpviewer_keywords:
- debugging [.NET Framework]
- .NET Framework application configuration, debugging
- debugging [.NET Framework], .NET Framework application debugging
- troubleshooting applications [.NET Framework], profiling
- application development [.NET Framework], debugging
- .NET Framework application configuration, profiling
- profiling applications
- troubleshooting applications [.NET Framework], debugging
- troubleshooting applications [.NET Framework]
- application development [.NET Framework], profiling
ms.assetid: 4a04863e-2475-46f4-bc3f-3c11510c2a4b
ms.openlocfilehash: 1a43c7fbcb810b22ff9bc409c233d2b1da67370e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217397"
---
# <a name="debugging-tracing-and-profiling"></a>Debug, traccia e profilatura
Per eseguire il debug di un'applicazione .NET Framework, l'ambiente del compilatore e di runtime deve essere configurato per consentire a un debugger di connettersi all'applicazione e di produrre simboli e mappe di linee, se possibile, per l'applicazione e il corrispondente Microsoft Intermediate Language (MSIL). Dopo il debug di un'applicazione gestita, è possibile eseguire la profilatura per migliorare le prestazioni. La profilatura valuta e descrive le righe del codice sorgente che generano il codice eseguito con maggiore frequenza e il tempo richiesto per eseguirle.  
  
 Il debug delle applicazioni .NET framework viene eseguito facilmente tramite Visual Studio, che gestisce molti dettagli della configurazione. Se Visual Studio non è installato, è possibile esaminare e migliorare le prestazioni delle applicazioni .NET Framework usando le classi di debug nello spazio dei nomi <xref:System.Diagnostics> di .NET Framework. Questo spazio dei nomi include le classi <xref:System.Diagnostics.Trace>, <xref:System.Diagnostics.Debug> e <xref:System.Diagnostics.TraceSource> per la traccia del flusso di esecuzione e le classi <xref:System.Diagnostics.Process>, <xref:System.Diagnostics.EventLog> e <xref:System.Diagnostics.PerformanceCounter> per il codice di profilatura.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Abilitazione del debug ad associazione JIT](enabling-jit-attach-debugging.md)  
 Mostra come configurare il Registro di sistema per eseguire l'associazione JIT di un motore di debug in un'applicazione .NET Framework.  
  
 [Semplificazione del debug di un'immagine](making-an-image-easier-to-debug.md)  
 Mostra come attivare il rilevamento JIT e disattivare l'ottimizzazione per rendere più semplice l'esecuzione del debug di un assembly.  
  
 [Traccia e strumentazione di applicazioni](tracing-and-instrumenting-applications.md)  
 Descrive come monitorare l'esecuzione dell'applicazione mentre è in esecuzione e come instrumentarla per visualizzare lo stato o gli errori durante l'esecuzione.  
  
 [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)  
 Descrive gli assistenti al debug gestito, strumenti di supporto al debug che funzionano in combinazione con Common Language Runtime (CLR) per fornire informazioni sullo stato di runtime.  
  
 [Miglioramento del debug tramite gli attributi di visualizzazione del debugger](enhancing-debugging-with-the-debugger-display-attributes.md)  
 Descrive in che modo lo sviluppatore di un tipo può specificarne l'aspetto quando viene visualizzato in un debugger.  
  
 [Contatori delle prestazioni](performance-counters.md)  
 Descrive i contatori che è possibile usare per registrare le prestazioni di un'applicazione.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Eseguire il debug di app ASP.NET o ASP.NET Core in Visual Studio](/visualstudio/debugger/how-to-enable-debugging-for-aspnet-applications)  
 Fornisce i prerequisiti e le istruzioni su come eseguire il debug di un'applicazione ASP.NET durante lo sviluppo o dopo la distribuzione.  
  
 [Guida di sviluppo](../development-guide.md)  
 Viene fornita una guida per tutte le aree e attività principali per lo sviluppo di applicazioni, quali la creazione, la configurazione, il debug, la sicurezza e la distribuzione dell'applicazione e informazioni su programmazione dinamica, interoperabilità, estendibilità, gestione della memoria e threading.
