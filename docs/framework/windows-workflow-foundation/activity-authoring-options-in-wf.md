---
title: Opzioni di creazione di attività in WF
ms.date: 03/30/2017
ms.assetid: b9061f5f-12c3-47f0-adbe-1330e2714c94
ms.openlocfilehash: f91c74b4e3dc002ed2abf979619b84a81db65e78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516400"
---
# <a name="activity-authoring-options-in-wf"></a>Opzioni di creazione di attività in WF
In [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] sono disponibili numerose opzioni per la creazione di attività personalizzate. Il metodo corretto da usare per la creazione di un'attività specifica dipende dalle funzionalità di runtime richieste.  
  
## <a name="deciding-which-base-activity-class-to-use-for-authoring-custom-activities"></a>Scelta della classe di attività di base da usare per la creazione di attività personalizzate  
 Nella tabella seguente sono elencate le funzionalità disponibili nelle classi di base di attività personalizzate.  
  
|Classe di attività di base|Funzionalità disponibili|  
|-------------------------|------------------------|  
|<xref:System.Activities.Activity>|Compone gruppi di attività fornite dal sistema e personalizzate in un'attività composita.|  
|<xref:System.Activities.CodeActivity>|Implementa la funzionalità imperativa fornendo un metodo <xref:System.Activities.CodeActivity%601.Execute%2A> di cui può essere eseguito l'override. Inoltre fornisce l'accesso a rilevamenti, variabili e argomenti.|  
|<xref:System.Activities.NativeActivity>|Fornisce tutte le funzionalità dell'oggetto <xref:System.Activities.CodeActivity>, oltre all'interruzione dell'esecuzione di attività, all'annullamento dell'esecuzione di attività figlio, all'utilizzo di segnalibri e alla pianificazione di attività, azioni di attività e funzioni.|  
|<xref:System.Activities.DynamicActivity>|Fornisce un approccio di tipo DOM alla costruzione di attività che si interfacciano con la finestra di progettazione WF e il sistema in fase di esecuzione tramite <!--zz <xref:System.ComponentModel.IcustomTypeDescriptor>--> `IcustomTypeDescriptor`, consentendo la nuova attività da creare senza definire nuovi tipi.|  
  
## <a name="authoring-activities-using-activity"></a>Creazione di attività tramite la classe Activity  
 Le attività che derivano dalla classe <xref:System.Activities.Activity> compongono la funzionalità assemblando altre attività esistenti. Queste attività possono essere attività personalizzate esistenti e attività dell'apposita libreria di [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]. L'assemblaggio di queste attività è il modo più comunemente usato per creare la funzionalità personalizzata. Questo approccio viene generalmente adottato quando si usa un ambiente di progettazione visiva per la creazione di flussi di lavoro.  
  
## <a name="authoring-activities-using-codeactivity-or-asynccodeactivity"></a>Creazione di attività tramite CodeActivity o AsyncCodeActivity  
 Le attività che derivano dalla classe <xref:System.Activities.CodeActivity> o <xref:System.Activities.AsyncCodeActivity> possono implementare la funzionalità imperativa eseguendo l'override del metodo <xref:System.Activities.CodeActivity%601.Execute%2A> con codice imperativo personalizzato. Il codice personalizzato viene eseguito quando l'attività viene eseguita dal runtime. Le attività create in questo modo possono accedere alla funzionalità personalizzata, ma non a tutte le funzionalità del runtime, ad esempio non dispongono dell'accesso completo all'ambiente di esecuzione, non dispongono della capacità di pianificare le attività figlio, di creare segnalibri o di supportare un metodo Cancel o Abort. Quando una classe <xref:System.Activities.CodeActivity> viene eseguita, dispone dell'accesso a una versione ridotta dell'ambiente di esecuzione (tramite la classe <xref:System.Activities.CodeActivityContext> o <xref:System.Activities.AsyncCodeActivityContext>). Le attività create usando la classe <xref:System.Activities.CodeActivity> dispongono dell'accesso alla risoluzione di argomenti e variabili, alle estensioni e ai rilevamenti. La pianificazione di attività asincrone può essere eseguita usando la classe <xref:System.Activities.AsyncCodeActivity>.  
  
## <a name="authoring-activities-using-nativeactivity"></a>Creazione di attività tramite la classe NativeActivity  
 Le attività che derivano dalla classe <xref:System.Activities.NativeActivity>, come quelle che derivano dalla classe <xref:System.Activities.CodeActivity> creano la funzionalità imperativa eseguendo l'override del metodo <xref:System.Activities.NativeActivity.Execute%2A>, ma dispongono anche dell'accesso a tutta la funzionalità del runtime del flusso di lavoro tramite la classe <xref:System.Activities.NativeActivityContext> che viene passata al metodo <xref:System.Activities.NativeActivity.Execute%2A>. In questo contesto dispone del supporto per la pianificazione e l'annullamento delle attività figlio, eseguendo <xref:System.Activities.ActivityAction> e <!--zz <xref:System.Activities.ActivityFunc>--> `ActivityFunc` oggetti, propagazione delle transazioni in un flusso di lavoro, richiamando i processi asincroni, annullando e interrompendo l'esecuzione, l'accesso a le proprietà di esecuzione e alle estensioni e ai segnalibri (handle per la ripresa dei flussi di lavoro in pausa).  
  
## <a name="authoring-activities-using-dynamicactivity"></a>Creazione di attività tramite la classe DynamicActivity  
 A differenza degli altri tre tipi di attività, non viene creata una nuova funzionalità derivando nuovi tipi dalla classe <xref:System.Activities.DynamicActivity> (la classe è sealed), bensì assemblando la funzionalità nelle proprietà <xref:System.Activities.DynamicActivity.Properties%2A> e <xref:System.Activities.DynamicActivity.Implementation%2A> tramite un modello a oggetti documento (DOM) dell'attività.  
  
## <a name="authoring-activities-that-return-a-result"></a>Creazione di attività che restituiscono un risultato  
 Molte attività devono restituire un risultato dopo la relativa esecuzione. Anche se a tal fine è sempre possibile definire un oggetto <xref:System.Activities.OutArgument%601> personalizzato in un'attività, è consigliabile usare invece l'oggetto <xref:System.Activities.Activity%601> o derivare dall'oggetto <xref:System.Activities.CodeActivity%601> o <xref:System.Activities.NativeActivity%601>. Ognuna di queste classi di base dispone di un oggetto <xref:System.Activities.OutArgument%601> denominato Result che l'attività può usare per il relativo valore restituito. Le attività che restituiscono un risultato devono essere usate solo se solo un risultato deve essere restituito da un'attività. Se devono essere restituiti più risultati, è necessario usare i membri <xref:System.Activities.OutArgument%601> separati.
