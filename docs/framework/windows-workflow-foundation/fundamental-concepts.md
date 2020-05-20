---
title: Concetti di base del flusso di lavoro di Windows
description: In questo articolo vengono descritti alcuni concetti relativi allo sviluppo di flussi di lavoro nel .NET Framework 4.6.1 che potrebbero non essere noti ad alcuni sviluppatori.
ms.date: 03/30/2017
ms.assetid: 0e930e80-5060-45d2-8a7a-95c0690105d4
ms.openlocfilehash: 07498241280191fb62a35a559a3391f7148c05b9
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419889"
---
# <a name="fundamental-windows-workflow-concepts"></a>Concetti di base del flusso di lavoro di Windows
Nello sviluppo del flusso di lavoro in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] vengono usati concetti che potrebbero essere nuovi per alcuni sviluppatori. In questo argomento vengono descritti alcuni dei concetti e la relativa implementazione.  
  
## <a name="workflows-and-activities"></a>Flussi di lavoro e attività  
 Un flusso di lavoro è una raccolta strutturata di azioni che modella un processo. Ogni azione del flusso di lavoro viene modellata come un'attività. Un host interagisce con un flusso di lavoro usando l'oggetto <xref:System.Activities.WorkflowInvoker> per richiamare un flusso di lavoro come se si trattasse di un metodo, l'oggetto <xref:System.Activities.WorkflowApplication> per controllare in modo esplicito l'esecuzione di una singola istanza del flusso di lavoro e l'oggetto <xref:System.ServiceModel.WorkflowServiceHost> per le interazioni basate su messaggi negli scenari a istanza multipla. Poiché i passaggi del flusso di lavoro sono definiti come una gerarchia di attività, si può affermare che l'attività in primo piano nella gerarchia definisce il flusso di lavoro stesso. Questo modello di gerarchia sostituisce le classi `SequentialWorkflow` e `StateMachineWorkflow` esplicite delle versioni precedenti. Le attività stesse vengono sviluppate come raccolte di altre attività (usando la classe <xref:System.Activities.Activity> come base che generalmente viene definita tramite XAML) oppure personalizzate tramite la classe <xref:System.Activities.CodeActivity> che può usare il runtime per accedere ai dati oppure la classe <xref:System.Activities.NativeActivity> che espone la varietà del runtime del flusso di lavoro all'autore di attività. Le attività sviluppate usando <xref:System.Activities.CodeActivity> e <xref:System.Activities.NativeActivity> vengono create tramite linguaggi conformi a CLR, ad esempio C#.  
  
## <a name="activity-data-model"></a>Modello di dati delle attività  
 Le attività archiviano e condividono i dati usando i tipi mostrati nella tabella seguente.  
  
|||  
|-|-|  
|Variabile|Archivia i dati in un'attività.|  
|Argomento|Sposta i dati all'interno e all'esterno di un'attività.|  
|Espressione|Attività con un valore restituito elevato usato nelle associazioni degli argomenti.|  
  
## <a name="workflow-runtime"></a>Fase di esecuzione flusso di lavoro  
 Il runtime del flusso di lavoro è un ambiente in cui vengono eseguiti i flussi di lavoro. <xref:System.Activities.WorkflowInvoker> è la modalità di base per eseguire un flusso di lavoro. L'host usa l'oggetto <xref:System.Activities.WorkflowInvoker> per eseguire le operazioni seguenti:  
  
- Per richiamare in modo sincrono un flusso di lavoro.  
  
- Per fornire input o recuperare output da un flusso di lavoro.  
  
- Per aggiungere estensioni che devono essere usate dalle attività.  
  
 L'oggetto <xref:System.Activities.ActivityInstance> è il proxy thread-safe che gli host possono usare per interagire con il runtime. L'host usa l'oggetto <xref:System.Activities.ActivityInstance> per eseguire le operazioni seguenti:  
  
- Per acquisire un'istanza creandola o caricandola da un archivio di istanze.  
  
- Per ricevere una notifica sugli eventi del ciclo di vita delle istanze.  
  
- Per controllare l'esecuzione del flusso di lavoro.  
  
- Per fornire input o recuperare output da un flusso di lavoro.  
  
- Per segnalare la continuazione di un flusso di lavoro e passare i valori a tale flusso.  
  
- Per rendere persistenti i dati del flusso di lavoro.  
  
- Per aggiungere estensioni che devono essere usate dalle attività.  
  
 Le attività accedono all'ambiente di runtime del flusso di lavoro tramite la classe derivata <xref:System.Activities.ActivityContext> appropriata, quale <xref:System.Activities.NativeActivityContext> o <xref:System.Activities.CodeActivityContext>. In questo modo possono risolvere argomenti e variabili, pianificare le attività figlio ed eseguire molte altre operazioni.  
  
## <a name="services"></a>Servizi  
 I flussi di lavoro rappresentano un modo semplice per implementare e accedere a servizi loosely-coupled usando le attività di messaggistica. Le attività di messaggistica sono basate su WCF e rappresentano il meccanismo principale utilizzato per ottenere i dati all'interno e all'esterno di un flusso di lavoro. È possibile comporre insieme attività di messaggistica per modellare qualsiasi tipo di modello di scambio di messaggi desiderato. Per altre informazioni, vedere [attività di messaggistica](../wcf/feature-details/messaging-activities.md). I servizi flusso di lavoro sono ospitati usando la classe <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Per ulteriori informazioni, vedere [Panoramica dei servizi flusso di lavoro di hosting](../wcf/feature-details/hosting-workflow-services-overview.md). Per ulteriori informazioni sui servizi del flusso di lavoro, vedere [Servizi flussi di lavoro](../wcf/feature-details/workflow-services.md)  
  
## <a name="persistence-unloading-and-long-running-workflows"></a>Persistenza, scaricamento e flussi di lavoro con esecuzione prolungata  
 Il flusso di lavoro di Windows semplifica la creazione di programmi reattivi con esecuzione prolungata fornendo:  
  
- Attività che accedono all'input esterno.  
  
- Possibilità di creare oggetti <xref:System.Activities.Bookmark> che possono essere ripresi da un listener di host.  
  
- Possibilità di rendere persistenti i dati di un flusso di lavoro e di scaricare quest'ultimo, quindi di ricaricarlo e riattivarlo in risposta alla ripresa di oggetti <xref:System.Activities.Bookmark> in un particolare flusso di lavoro.  
  
 Un flusso di lavoro esegue continuamente attività finché non sono terminate o finché tutte le attività attualmente in esecuzione stanno aspettando l'input. In quest'ultimo caso, il flusso di lavoro è inattivo. È normale che i flussi di lavoro che si trovano nello stato di inattività vengono scaricati e ricaricati dall'host per continuare l'esecuzione quando arriva un messaggio. <xref:System.ServiceModel.Activities.WorkflowServiceHost> fornisce la funzionalità per questa funzione e fornisce un criterio estendibile di scaricamento. Per i blocchi di esecuzione che usando dati allo stato volatile o altri dati che non possono essere resi persistenti, un'attività può indicare a un host che non deve essere resa persistente usando l'oggetto <xref:System.Activities.NoPersistHandle>. Un flusso di lavoro può rendere esplicitamente persistenti i propri dati in un supporto di archiviazione durevole tramite l'attività <xref:System.Activities.Statements.Persist>.
