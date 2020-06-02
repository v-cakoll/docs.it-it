---
title: Threading gestito
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
ms.openlocfilehash: e4c19b664e8fc040fdc4a284b30f6104d676088d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279154"
---
# <a name="managed-threading"></a>Threading gestito
Indipendentemente dal numero di processori usati nello sviluppo per i computer, l'applicazione dovrà offrire l'interazione più reattiva possibile con l'utente, anche se sono in corso altre attività. L'uso di più thread di esecuzione è uno dei modi più efficaci per mantenere la reattività dell'applicazione con l'utente e contemporaneamente usare il processore tra un evento utente e l'altro o persino durante gli eventi. Oltre a introdurre i concetti di base del threading, questa sezione è incentrata sui concetti di threading gestito e di uso del threading gestito.  
  
> [!NOTE]
> A partire da .NET Framework 4, la programmazione multithreading è notevolmente semplificata con le classi <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md), le nuove classi di raccolta simultanee nello spazio dei nomi <xref:System.Collections.Concurrent?displayProperty=nameWithType> e un nuovo modello di programmazione che si basa sul concetto di attività anziché di thread. Per ulteriori informazioni, vedere [programmazione parallela](../parallel-programming/index.md).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Nozioni fondamentali sul threading gestito](managed-threading-basics.md)  
 Fornisce una panoramica del threading gestito e illustra quando usare più thread.  
  
 [Utilizzo di thread e threading](using-threads-and-threading.md)  
 Illustra come creare, avviare, sospendere, riprendere e interrompere i thread.  
  
 [Procedure consigliate per il threading gestito](managed-threading-best-practices.md)  
 Illustra i livelli di sincronizzazione, come evitare deadlock e race condition e altri problemi di threading.  
  
 [Oggetti e funzionalità di threading](threading-objects-and-features.md)  
 Descrive le classi gestite che è possibile usare per sincronizzare le attività dei thread e i dati di oggetti accessibili su thread differenti e fornisce una panoramica dei thread del pool.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.Threading>  
 Contiene classi per l'uso e la sincronizzazione dei thread gestiti.  
  
 <xref:System.Collections.Concurrent>  
 Contiene le classi di raccolta che sono sicure per l'uso con più thread.  
  
 <xref:System.Threading.Tasks>  
 Contiene classi per la creazione e la pianificazione delle attività di elaborazione simultanee.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Domini applicazione](../../framework/app-domains/application-domains.md)  
 Fornisce una panoramica dei domini dell'applicazione e del loro uso da parte di Common Language Runtime.  
  
 [I/O file asincrono](../io/asynchronous-file-i-o.md)  
 Vengono descritti il funzionamento di base dell'I/O asincrono e i relativi vantaggi in termini di prestazioni.  
  
 [Modello asincrono basato su attività (TAP)](../asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)  
 Offre una panoramica del modello consigliato per la programmazione asincrona in .NET.  
  
 [Chiamata di metodi sincroni in modalità asincrona](../asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 Illustra come chiamare metodi sul thread del pool usando le funzionalità predefinite dei delegati.  
  
 [Programmazione parallela](../parallel-programming/index.md)  
 Descrive le librerie per la programmazione parallela, che semplificano l'uso di più thread nelle applicazioni.  
  
 [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md)  
 Descrive un sistema per l'esecuzione di query in parallelo, in modo da sfruttare più processori.
