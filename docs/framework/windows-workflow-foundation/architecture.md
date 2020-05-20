---
title: Architettura del flusso di lavoro di Windows
description: Windows Workflow Foundation incapsula unità di lavoro come attività, che vengono eseguite in un ambiente con controllo di flusso, gestione delle eccezioni e altre funzionalità.
ms.date: 03/30/2017
ms.assetid: 1d4c6495-d64a-46d0-896a-3a01fac90aa9
ms.openlocfilehash: 22ebeb7d95342ad6843e0721da8b213ed4a4d9b6
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420136"
---
# <a name="windows-workflow-architecture"></a>Architettura del flusso di lavoro di Windows
Windows Workflow Foundation (WF) eleva il livello di astrazione per lo sviluppo di applicazioni interattive a esecuzione prolungata. Le unità di lavoro vengono incapsulate come attività. Le attività vengono eseguite in un ambiente che fornisce funzionalità per il controllo del flusso, gestione delle eccezioni, propagazione degli errori, persistenza dei dati relativi allo stato, caricamento e scaricamento di flussi di lavoro in corso dalla memoria, rilevamento e flusso della transazione.  
  
## <a name="activity-architecture"></a>Architettura dell'attività  
 Le attività vengono sviluppate come tipi CLR che derivano dall'oggetto <xref:System.Activities.Activity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> o <xref:System.Activities.NativeActivity> oppure dalle relative varianti che restituiscono un valore, <xref:System.Activities.Activity%601>, <xref:System.Activities.CodeActivity%601>, <xref:System.Activities.AsyncCodeActivity%601> o <xref:System.Activities.NativeActivity%601>. Lo sviluppo di attività che derivano dall'oggetto <xref:System.Activities.Activity> consente all'utente di assemblare attività preesistenti per creare rapidamente unità di lavoro che vengono eseguite nell'ambiente del flusso di lavoro. L'oggetto <xref:System.Activities.CodeActivity>, d'altra parte, consente la creazione della logica di esecuzione nel codice gestito usando l'oggetto <xref:System.Activities.CodeActivityContext> principalmente per accedere agli argomenti delle attività. L'oggetto <xref:System.Activities.AsyncCodeActivity> è simile a <xref:System.Activities.CodeActivity> con la differenza che può essere usato per implementare attività asincrone. Lo sviluppo di attività che derivano dall'oggetto <xref:System.Activities.NativeActivity> consente agli utenti di accedere al runtime tramite l'oggetto <xref:System.Activities.NativeActivityContext> per funzionalità quali la pianificazione di elementi figlio, la creazione di segnalibri, il richiamo di lavori asincroni, la registrazione di transazioni e così via.  
  
 La creazione di attività che derivano dall'oggetto <xref:System.Activities.Activity> è dichiarativa e questa attività possono essere create in XAML. Nell'esempio seguente viene creata un'attività denominata `Prompt` usando altre attività per il corpo dell'esecuzione.  
  
```xml  
<Activity x:Class='Prompt'  
  xmlns:x='http://schemas.microsoft.com/winfx/2006/xaml'  
    xmlns:z='http://schemas.microsoft.com/netfx/2008/xaml/schema'  
xmlns:my='clr-namespace:XAMLActivityDefinition;assembly=XAMLActivityDefinition'  
xmlns:s="clr-namespace:System;assembly=mscorlib"  
xmlns="http://schemas.microsoft.com/2009/workflow">  
<z:SchemaType.Members>  
    <z:SchemaType.SchemaProperty Name='Text' Type=' InArgument(s:String)' />  
  <z:SchemaType.SchemaProperty Name='Response' Type='OutArgument(s:String)' />  
</z:SchemaType.Members>  
  <Sequence>  
    <my:WriteLine Text='[Text]' />  
    <my:ReadLine BookmarkName='r1' Result='[Response]' />  
  </Sequence>  
</Activity>  
```  
  
## <a name="activity-context"></a>Contesto dell'attività  
 L'oggetto <xref:System.Activities.ActivityContext> rappresenta l'interfaccia tra l'autore di attività e l'esecuzione del flusso di lavoro e fornisce l'accesso alle numerose funzionalità di esecuzione. Nell'esempio seguente viene definita un'attività che usa il contesto di esecuzione per creare un segnalibro (meccanismo che consente a un'attività di registrare un punto di continuazione nella relativa esecuzione che può essere ripresa da un host che passa dati all'attività).  
  
 [!code-csharp[CFX_WorkflowApplicationExample#15](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#15)]  
  
## <a name="activity-life-cycle"></a>Ciclo di vita dell'attività  
 Un'istanza di un'attività viene avviata nello stato <xref:System.Activities.ActivityInstanceState.Executing>. A meno che non si verifichino eccezioni, rimane in questo stato finché non vengono completati l'esecuzione di tutte le attività figlio e qualsiasi altro lavoro in sospeso (ad esempio gli oggetti <xref:System.Activities.Bookmark>); a questo punto passa allo stato <xref:System.Activities.ActivityInstanceState.Closed>. L'elemento padre di un istanza dell'attività può richiedere l'annullamento di un elemento figlio. Se quest'ultimo può essere annullato, viene completato nello stato <xref:System.Activities.ActivityInstanceState.Canceled>. Se durante l'esecuzione viene generata un'eccezione, il runtime inserisce l'attività nello stato <xref:System.Activities.ActivityInstanceState.Faulted> e propaga l'eccezione fino alla catena di attività padre. Di seguito sono riportati i tre stati di completamento di un'attività:
  
- **Chiuso:** L'attività ha completato il proprio lavoro ed è stata chiusa.  
  
- Operazione **annullata:** L'attività ha abbandonato normalmente il lavoro ed è stata chiusa. Quando viene immesso questo stato, il lavoro non viene sottoposto a rollback in modo esplicito.  
  
- **Errore:** L'attività ha rilevato un errore ed è stata chiusa senza completare il lavoro.  
  
 Le attività rimangono nello stato <xref:System.Activities.ActivityInstanceState.Executing> quando vengono rese persistenti o scaricate.
