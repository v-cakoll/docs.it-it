---
title: Threading gestito
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f51920bceef6e83af4f6ef029eb49ae495a58b9b
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490850"
---
# <a name="managed-threading"></a>Threading gestito
Indipendentemente dal numero di processori usati nello sviluppo per i computer, l'applicazione dovrà offrire l'interazione più reattiva possibile con l'utente, anche se sono in corso altre attività. L'uso di più thread di esecuzione è uno dei modi più efficaci per mantenere la reattività dell'applicazione con l'utente e contemporaneamente usare il processore tra un evento utente e l'altro o persino durante gli eventi. Oltre a introdurre i concetti di base del threading, questa sezione è incentrata sui concetti di threading gestito e di uso del threading gestito.  
  
> [!NOTE]
>  A partire da .NET Framework 4, la programmazione multithreading è notevolmente semplificata con il <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> classi [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md), nuove classi collection simultanee nel <xref:System.Collections.Concurrent?displayProperty=nameWithType> dello spazio dei nomi e un nuovo modello di programmazione che si basa sul concetto di attività anziché di thread. Per altre informazioni, vedere [Programmazione parallela](../../../docs/standard/parallel-programming/index.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Nozioni di base sul threading gestito](../../../docs/standard/threading/managed-threading-basics.md)  
 Fornisce una panoramica del threading gestito e illustra quando usare più thread.  
  
 [Utilizzo di thread e threading](../../../docs/standard/threading/using-threads-and-threading.md)  
 Illustra come creare, avviare, sospendere, riprendere e interrompere i thread.  
  
 [Suggerimenti per l'utilizzo del threading gestito](../../../docs/standard/threading/managed-threading-best-practices.md)  
 Illustra i livelli di sincronizzazione, come evitare deadlock e race condition e altri problemi di threading.  
  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)  
 Descrive le classi gestite che è possibile usare per sincronizzare le attività dei thread e i dati di oggetti accessibili su thread differenti e fornisce una panoramica dei thread del pool.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Threading>  
 Contiene classi per l'uso e la sincronizzazione dei thread gestiti.  
  
 <xref:System.Collections.Concurrent>  
 Contiene le classi di raccolta che sono sicure per l'uso con più thread.  
  
 <xref:System.Threading.Tasks>  
 Contiene classi per la creazione e la pianificazione delle attività di elaborazione simultanee.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Domini dell'applicazione](../../../docs/framework/app-domains/application-domains.md)  
 Fornisce una panoramica dei domini dell'applicazione e del loro uso da parte di Common Language Runtime.  
  
 [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md)  
 Vengono descritti il funzionamento di base dell'I/O asincrono e i relativi vantaggi in termini di prestazioni.  
  
 [Modello asincrono basato su attività (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)  
 Offre una panoramica del modello consigliato per la programmazione asincrona in .NET.  
  
 [Chiamata sincrona dei metodi asincroni](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 Illustra come chiamare metodi sul thread del pool usando le funzionalità predefinite dei delegati.  
  
 [Programmazione parallela](../../../docs/standard/parallel-programming/index.md)  
 Descrive le librerie per la programmazione parallela, che semplificano l'uso di più thread nelle applicazioni.  
  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 Descrive un sistema per l'esecuzione di query in parallelo, in modo da sfruttare più processori.
