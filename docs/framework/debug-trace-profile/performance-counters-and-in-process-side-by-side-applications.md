---
title: Contatori delle prestazioni e applicazioni affiancate in-process
description: Esaminare i contatori delle prestazioni e le applicazioni affiancate in-process in .NET. Usare Perfmon.exe per distinguere i contatori delle prestazioni in base al runtime.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- performance counters
- performance counters,and in-process side-by-side applications
- performance,.NET Framework applications
- performance monitoring,counters
ms.assetid: 6888f9be-c65b-4b03-a07b-df7ebdee2436
ms.openlocfilehash: eb05d9f5f930420827c6b3d94ea0ed34f64464fd
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803859"
---
# <a name="performance-counters-and-in-process-side-by-side-applications"></a>Contatori delle prestazioni e applicazioni affiancate in-process
Con Performance Monitor (Perfmon.exe) è possibile distinguere i contatori delle prestazioni in base al runtime. Questo argomento descrive la modifica del Registro di sistema necessaria per abilitare questa funzionalità.  
  
## <a name="the-default-behavior"></a>Comportamento predefinito  
 Per impostazione predefinita, Performance Monitor visualizza i contatori delle prestazioni in base all'applicazione. In due scenari, tuttavia, ciò può rappresentare un problema:  
  
- Quando viene eseguito il monitoraggio di due applicazioni con lo stesso nome. Ad esempio, se entrambe le applicazioni sono denominate app.exe, una verrà visualizzata come **app** e l'altra come **app#1** nella colonna **Istanza**. In questo caso, è difficile associare un contatore delle prestazioni a un'applicazione specifica. Non è chiaro se i dati raccolti per **app #1** fanno riferimento alla prima o alla seconda app.exe.  
  
- Quando un'applicazione usa più istanze di Common Language Runtime. Il .NET Framework 4 supporta gli scenari di hosting affiancato in-process. ovvero un singolo processo o un'applicazione può caricare più istanze del Common Language Runtime. Se una singola applicazione denominata app.exe carica due istanze di runtime, per impostazione predefinita verranno designate come **app** e **app#1** nella colonna **Istanza**. In questo caso, non è chiaro se **app** e **app#1** fanno riferimento a due applicazioni con lo stesso nome o alla stessa applicazione con due runtime. Se più applicazioni con lo stesso nome caricano più runtime, l'ambiguità è ancora maggiore.  
  
 È possibile impostare una chiave del Registro di sistema per evitare questa ambiguità. Per le applicazioni sviluppate utilizzando il .NET Framework 4, questa modifica del registro di sistema aggiunge un identificatore di processo seguito da un identificatore dell'istanza di runtime al nome dell'applicazione nella colonna dell' **istanza** . Invece di *#1 dell'applicazione o* dell' *applicazione*, l'applicazione è ora identificata come *Application*_ `p` *ProcessID* \_ `r` *IDruntime* nella colonna dell' **istanza** . Se un'applicazione è stata sviluppata utilizzando una versione precedente del Common Language Runtime, tale istanza viene rappresentata *come \_ * `p` *ProcessID* dell'applicazione purché sia installato il .NET Framework 4.  
  
## <a name="performance-counters-for-in-process-side-by-side-applications"></a>Contatori delle prestazioni per applicazioni affiancate in-process  
 Per gestire i contatori delle prestazioni per più versioni di Common Language Runtime ospitate in una singola applicazione, è necessario modificare una chiave del Registro di sistema, come illustrato nella tabella seguente.  
  
|||  
|-|-|  
|Nome della chiave|HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\.NETFramework\Performance|  
|Nome del valore|ProcessNameFormat|  
|Tipo valore|REG_DWORD|  
|Valore|1 (0x00000001)|  
  
 Il valore 0 per `ProcessNameFormat` indica che è abilitato il comportamento predefinito, ovvero Perfmon.exe visualizza i contatori delle prestazioni in base alle singole applicazioni. Quando si imposta questo valore su 1, Perfmon.exe risolve l'ambiguità per più versioni di un'applicazione e fornisce i contatori delle prestazioni in base al runtime. Qualsiasi altro valore per l'impostazione della chiave del Registro di sistema `ProcessNameFormat` non è supportato ed è riservato per usi futuri.  
  
 Dopo aver aggiornato l'impostazione della chiave del Registro di sistema `ProcessNameFormat`, è necessario riavviare Perfmon.exe o qualsiasi altro consumer di contatori delle prestazioni, in modo che la nuova funzionalità di denominazione delle istanze funzioni correttamente.  
  
 L'esempio seguente mostra come modificare il valore `ProcessNameFormat` a livello di codice.  
  
 [!code-csharp[Conceptual.PerfCounters.InProSxS#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.perfcounters.inprosxs/cs/regsetting1.cs#1)]
 [!code-vb[Conceptual.PerfCounters.InProSxS#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.perfcounters.inprosxs/vb/regsetting1.vb#1)]  
  
 Quando si modifica il registro di sistema, Perfmon.exe Visualizza i nomi delle applicazioni destinate a .NET Framework 4 come *Application*_ `p` *ProcessID* \_ `r` *IDruntime*, dove *applicazione* è il nome dell'applicazione, *ProcessID* è l'identificatore del processo dell'applicazione e *IDruntime* è un identificatore Common Language Runtime. Ad esempio, se un'applicazione denominata app.exe carica due istanze di Common Language Runtime, Perfmon.exe può identificare un'istanza come app_p1416_r10 e la seconda come app_p3160_r10. L'identificatore di runtime risolve solo eventuali ambiguità per i runtime all'interno di un processo e non fornisce informazioni sul runtime. (Ad esempio, l'ID di runtime non ha alcuna relazione con la versione o lo SKU del runtime.)  
  
 Se la .NET Framework 4 è installata, la modifica del registro di sistema influiscono anche sulle applicazioni sviluppate con versioni precedenti del .NET Framework. Questi vengono visualizzati in Perfmon.exe come *application_* `p` *ProcessID*, dove *applicazione* è il nome dell'applicazione e *ProcessID* è l'identificatore del processo. Ad esempio, se vengono monitorati i contatori delle prestazioni di due applicazioni denominate app.exe, una potrebbe essere visualizzata come app_p23900 e l'altra come app_p24908.  
  
> [!NOTE]
> L'identificatore di processo elimina l'ambiguità per la risoluzione di due applicazioni con lo stesso nome che usano versioni precedenti del runtime. Un identificatore di runtime non è obbligatorio per le versioni precedenti, perché le versioni precedenti di Common Language Runtime non supportano gli scenari affiancati.  
  
 Se la .NET Framework 4 non è presente o è stata disinstallata, l'impostazione della chiave del registro di sistema non ha alcun effetto. Questo significa che due applicazioni con lo stesso nome continueranno a essere visualizzate in Perfmon.exe come *applicazione* e *applicazione#1* (ad esempio, come **app** e **app#1**).
