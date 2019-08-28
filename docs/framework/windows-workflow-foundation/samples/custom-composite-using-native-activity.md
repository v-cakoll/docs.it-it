---
title: Attività composta personalizzata tramite l'oggetto NativeActivity
ms.date: 03/30/2017
ms.assetid: ef9e739c-8a8a-4d11-9e25-cb42c62e3c76
ms.openlocfilehash: 8a0d1077c058ecdbad10a2e7bd61ff5eb75e1cb5
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044315"
---
# <a name="custom-composite-using-native-activity"></a>Attività composta personalizzata tramite l'oggetto NativeActivity
In questo esempio viene illustrato come scrivere un oggetto <xref:System.Activities.NativeActivity> che pianifica altri oggetti <xref:System.Activities.Activity> per controllare il flusso dell'esecuzione di un flusso di lavoro. In questo esempio vengono usati due flussi di controllo comuni, Sequence e While, per illustrate le operazioni da eseguire.

## <a name="sample-details"></a>Dettagli dell'esempio
 Iniziando da `MySequence`, la prima cosa da notare è che deriva da <xref:System.Activities.NativeActivity>. <xref:System.Activities.NativeActivity> è l'oggetto <xref:System.Activities.Activity> che espone l'intero runtime del flusso di lavoro attraverso l'oggetto <xref:System.Activities.NativeActivityContext> passato al metodo `Execute`.

 L'oggetto `MySequence` espone una raccolta pubblica di oggetti <xref:System.Activities.Activity> che viene popolata dall'autore del flusso di lavoro. Prima dell'esecuzione del flusso di lavoro, il relativo runtime chiama il metodo <xref:System.Activities.Activity.CacheMetadata%2A> in ogni attività di un flusso di lavoro. Durante questo processo, il runtime stabilisce relazioni padre-figlio per l'ambito dei dati e la gestione di durata. L'implementazione <xref:System.Activities.Activity.CacheMetadata%2A> predefinita del metodo usa la <xref:System.ComponentModel.TypeDescriptor> classe dell'istanza affinché l' `MySequence` attività aggiunga qualsiasi proprietà pubblica di tipo <xref:System.Activities.Activity> o <xref:System.Collections.IEnumerable> \< <xref:System.Activities.Activity>> come elementi figlio del `MySequence` attività.

 Ogni volta che un'attività espone una raccolta pubblica di attività figlio, è probabile che queste ultime condividano lo stato. Una procedura consigliata per l'attività padre, in questo caso `MySequence`, consiste nell'esporre anche una raccolta di variabili tramite cui le attività figlio possono portare a termine questa operazione. Analogamente alle attività figlio <xref:System.Activities.Activity.CacheMetadata%2A> , il metodo aggiunge proprietà pubbliche <xref:System.Activities.Variable> di <xref:System.Collections.IEnumerable>tipo o \< <xref:System.Activities.Variable>> come variabili associate `MySequence` all'attività.

 Oltre alle variabili pubbliche, che vengono modificati gli elementi figlio del `MySequence`, `MySequence` deve anche tenere traccia di in cui è in esecuzione dei relativi elementi figlio. Per eseguire questa operazione, usa una variabile privata, ovvero `currentIndex`. Questa variabile viene registrata come parte dell'ambiente `MySequence` aggiungendo una chiamata al metodo <xref:System.Activities.NativeActivityMetadata.AddImplementationVariable%2A> all'interno del metodo `MySequence` dell'attività <xref:System.Activities.Activity.CacheMetadata%2A>. Gli oggetti <xref:System.Activities.Activity> aggiunti alla raccolta `MySequence``Activities` non possono accedere alle variabili aggiunte in questo modo.

 Quando l'oggetto `MySequence` viene eseguito dal runtime, quest'ultimo chiama il metodo <xref:System.Activities.NativeActivity.Execute%2A>, passando un oggetto <xref:System.Activities.NativeActivityContext>. L'oggetto <xref:System.Activities.NativeActivityContext> è il proxy dell'attività di nuovo nel runtime per dereferenziare gli argomenti e le variabili nonché pianificare altri oggetti <xref:System.Activities.Activity> o `ActivityDelegates`. `MySequence` usa un metodo `InternalExecute` per incapsulare la logica di pianificazione del primo elemento figlio e di tutti gli elementi figlio successivi in un singolo metodo. Inizia dereferenziando il riferimento `currentIndex`. Se è uguale al conteggio nella raccolta `Activities`, la sequenza è completata, l'attività viene restituita senza pianificare nessuna operazione e lo stato del runtime viene impostato su <xref:System.Activities.ActivityInstanceState.Closed>. <xref:System.Activities.CompletionCallback> `MySequence` `Activities` `InternalExecute` <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>Se è minore del conteggio delle attività, l'elemento figlio successivo viene ottenuto dalla raccolta e chiama, passando l'elemento figlio da pianificare e un oggetto che punta all'oggetto `currentIndex` Metodo. Infine, viene incrementato l'oggetto `currentIndex` e il controllo viene di nuovo restituito al runtime. Finché un'istanza dell'oggetto `MySequence` dispone di un oggetto <xref:System.Activities.Activity> figlio pianificato, il runtime considera che si trovi nello stato Executing.

 Una volta completata l'attività figlio, viene eseguito l'oggetto <xref:System.Activities.CompletionCallback>. Il ciclo continua dall'inizio. Come per `Execute`, un oggetto <xref:System.Activities.CompletionCallback> accetta un oggetto <xref:System.Activities.NativeActivityContext>, consentendo al responsabile dell'implementazione di accedere al runtime.

 `MyWhile`si differenzia da `MySequence` in quanto pianifica un singolo <xref:System.Activities.Activity> oggetto ripetutamente e in quanto usa un <xref:System.Activities.Activity%601>< bool\> denominato `Condition` per determinare se la pianificazione deve essere eseguita. Come per `MySequence`, l'oggetto `MyWhile` usa un metodo `InternalExecute` per centralizzare la relativa logica di pianificazione. Pianifica `Condition`l' <xref:System.Activities.Activity>< bool\> con una <xref:System.Activities.CompletionCallback%601> >bool`OnEvaluationCompleted`denominata. \< Quando viene completata l'esecuzione dell'oggetto `Condition`, il risultato diventa disponibile tramite questo oggetto <xref:System.Activities.CompletionCallback> in un parametro fortemente tipizzato denominato `result`. Se `true`, l'oggetto `MyWhile` chiama il metodo <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, passando gli oggetti `Body`<xref:System.Activities.Activity> e `InternalExecute` come oggetto <xref:System.Activities.CompletionCallback>. Quando viene completata l'esecuzione dell'oggetto `Body`, l'oggetto `Condition` viene nuovamente pianificato in `InternalExecute`, avviando di nuovo il ciclo. Quando l'oggetto `Condition` restituisce `false`, un'istanza dell'oggetto `MyWhile` restituisce il controllo al runtime senza pianificare l'oggetto `Body` e il runtime ne imposta lo stato su <xref:System.Activities.ActivityInstanceState.Closed>.

#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Aprire la soluzione di esempio Composite. sln in Visual Studio 2010.

2. Compilare ed eseguire la soluzione.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ed esempi. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\CustomCompositeNativeActivity`
