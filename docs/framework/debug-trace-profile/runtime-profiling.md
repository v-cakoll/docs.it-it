---
title: Profilatura runtime
ms.date: 03/30/2017
helpviewer_keywords:
- performance counters
- common language runtime, profiling
- Perfmon.exe
- System Monitor
- profiling
- runtime, profiling
- profiling applications
- Performance Console
ms.assetid: ccd68284-f3a8-47b8-bc3f-92e5fe3a1640
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7214fa0342d0946044861c4e375c7797ad6a06b1
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833767"
---
# <a name="runtime-profiling"></a>Profilatura runtime
La profilatura è un metodo di raccolta dei dati sulle prestazioni in qualsiasi scenario di sviluppo o distribuzione. Questa sezione è destinata agli sviluppatori e agli amministratori di sistema che vogliono raccogliere le informazioni sulle prestazioni delle applicazioni.  
  
## <a name="tracking-performance-using-the-performance-monitor-perfmonexe"></a>Rilevamento delle prestazioni con Performance Monitor (Perfmon.exe)  
 Il monitoraggio delle prestazioni è lo strumento più semplice da usare per profilare l'applicazione .NET Framework. Performance Monitor rappresenta graficamente i dati trovati nei contatori delle prestazioni .NET Framework installati con common language runtime e Windows Software Development Kit (SDK). Questi contatori possono essere usati per monitorare una serie di attività, dalla gestione della memoria alle prestazioni del compilatore JIT. Forniscono informazioni sulle risorse usate dall'applicazione, che indirettamente misurano le prestazioni dell'applicazione. Usare questi contatori per comprendere il funzionamento interno dell'applicazione.  
  
#### <a name="to-run-perfmonexe-on-windows-vista-and-later-versions"></a>Per eseguire Perfmon.exe in Windows Vista e versioni successive  
  
1. Al prompt dei comandi digitare **perfmon**. Viene visualizzata la console di **Performance Monitor** .  
  
2. Nella cartella **Strumenti di monitoraggio** fare clic su **Performance Monitor**.  
  
3. Nella barra degli strumenti di Performance Monitor fare clic sull'icona **Aggiungi** (il segno di addizione), se presente. Se non è presente, fare clic con il pulsante destro del mouse nella finestra di monitoraggio e selezionare l'opzione **Aggiungi contatori** .  
  
     Viene aperta la finestra di dialogo **Aggiungi contatori** . La casella di riepilogo **Contatori disponibili** visualizza gli oggetti prestazione disponibili. Esistono diversi oggetti predefiniti per le applicazioni .NET Framework, inclusi quelli per la gestione della memoria (**Memoria CLR .NET**), per l'interoperabilità (**Interoperabilità CLR .NET**), per la gestione delle eccezioni (**Eccezioni CLR .NET**) e per il multithreading (**LocksAndThreads CLR .NET**). Ogni oggetto prestazione include diversi contatori delle prestazioni singoli. Per un elenco dei contatori delle prestazioni disponibili in Performance Monitor, vedere [Performance Counters](../../../docs/framework/debug-trace-profile/performance-counters.md).  
  
4. Selezionare la casella di controllo accanto al nome di un oggetto prestazione per visualizzare l'elenco dei singoli contatori delle prestazioni che supporta.  
  
5. Fare clic sul contatore delle prestazioni da visualizzare:  
  
6. Nella casella di riepilogo **Istanze dell'oggetto selezionato** fare clic su **\<Tutte le istanze>** per specificare che si vuole monitorare il contatore delle prestazioni per Common Language Runtime globalmente, cioè a livello di sistema.  
  
     -oppure-  
  
     Nella casella di riepilogo **Istanze dell'oggetto selezionato** fare clic su un nome dell'applicazione per monitorare il relativo contatore delle prestazioni.  
  
     Per differenziare più versioni di runtime o per evitare ambiguità tra più applicazioni con lo stesso nome, è necessario modificare anche una chiave del Registro di sistema. Per altre informazioni, vedere [Performance Counters and In-Process Side-By-Side Applications](../../../docs/framework/debug-trace-profile/performance-counters-and-in-process-side-by-side-applications.md).  
  
> [!NOTE]
>  Quando vengono installati nuovi contatori delle prestazioni mentre è in esecuzione la console prestazioni, arrestare e riavviare la console per rendere visibili i nuovi contatori.  
  
 Per profilare un assembly esistente in un'area o in una condivisione remota, assicurarsi che l'assembly remoto sia totalmente attendibile nel computer che esegue i contatori delle prestazioni. Se l'assembly non ha l'attendibilità totale, i contatori delle prestazioni non funzioneranno. Per informazioni sulla concessione dell'attendibilità alle diverse aree, vedere [Caspol.exe (strumento per i criteri di sicurezza dall'accesso di codice)](../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md).  
  
> [!NOTE]
>  Nei sistemi in cui è installato .NET Framework 4, Performance Monitor potrebbe non visualizzare i dati per i contatori delle prestazioni in alcune categorie, ad esempio **dati CLR .NET** e **.NET CLR Networking**, per applicazioni sviluppate con .NET Framework 1.1. In questo caso, è possibile configurare Performance Monitor per visualizzare questi dati aggiungendo l'elemento [\<forcePerformanceCounterUniqueSharedMemoryReads>](../../../docs/framework/configure-apps/file-schema/runtime/forceperformancecounteruniquesharedmemoryreads-element.md) al file di configurazione dell'applicazione.  
  
## <a name="reading-and-creating-performance-counters-programmatically"></a>Lettura e creazione di contatori delle prestazioni a livello di codice  
 .NET Framework fornisce le classi che è possibile usare per accedere a livello di codice le stesse informazioni sulle prestazioni che sono disponibile nella console prestazioni. È anche possibile usare queste classi per creare contatori delle prestazioni personalizzati. Nella tabella seguente descrive alcune delle classi fornite in .NET Framework di monitoraggio delle prestazioni.  
  
|Classe|Descrizione|  
|-----------|-----------------|  
|<xref:System.Diagnostics.PerformanceCounter?displayProperty=nameWithType>|Rappresenta un componente del contatore delle prestazioni di Windows NT. Usare questa classe per leggere i contatori predefiniti o personalizzati esistenti e pubblicare i dati sulle prestazioni (scrittura) nei contatori personalizzati.|  
|<xref:System.Diagnostics.PerformanceCounterCategory?displayProperty=nameWithType>|Fornisce diversi metodi per interagire con i contatori e le categorie di contatori del computer.|  
|<xref:System.Diagnostics.PerformanceCounterInstaller?displayProperty=nameWithType>|Specifica un programma di installazione per il componente `PerformanceCounter` .|  
|<xref:System.Diagnostics.PerformanceCounterType?displayProperty=nameWithType>|Specifica la formula per calcolare il metodo `NextValue` per `PerformanceCounter`.|  
  
## <a name="see-also"></a>Vedere anche

- [Contatori delle prestazioni](../../../docs/framework/debug-trace-profile/performance-counters.md)
