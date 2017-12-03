---
title: "Attività For"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ea751b4-36f0-48aa-a115-70a2ab89f6d8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3b97e4bcd8dd60aa2768a8346d120bdebdb55ba
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="for-activity"></a>Attività For
Nell'esempio For viene illustrato come compilare un'attività personalizzata che eredita da <xref:System.Activities.NativeActivity> e usarla in un flusso di lavoro per eseguire un esempio reale. L'attività personalizzata inclusa in questo esempio funziona come l'istruzione `for` di C#. T  
  
 L'attività personalizzata `For` dispone di proprietà denominate `InitAction`, `IterationAction`, `Condition` e `Body` che corrispondono rispettivamente all'istruzione dell'inizializzazione, all'istruzione iterativa, alla condizione di continuazione e all'istruzione del corpo disponibili nell'istruzione standard `For` di C#.  
  
 Nella tabella seguente vengono descritti i file principali dell'esempio.  
  
|File|Descrizione|  
|----------|-----------------|  
|For.cs|Definizione di classe per l'attività personalizzata `For` che estende la classe <xref:System.Activities.NativeActivity> per fornire la funzionalità dell'istruzione `For` di C#.|  
|Program.cs|Applicazione client che esegue lavoro iterativo di base in una raccolta usando l'attività `For` personalizzata.|  
  
> [!NOTE]
>  Quando si usa l'attività personalizzata `For`, assicurarsi che venga impostata la proprietà `Condition`. Diversamente si potrebbe verificare un ciclo infinito.  
  
## <a name="demonstrates"></a>Dimostrazione  
 Creare un'attività personalizzata che eredita da <xref:System.Activities.NativeActivity>.  
  
## <a name="discussion"></a>Discussione  
 Nella tabella seguente sono descritte le proprietà dell'attività inclusa in questo esempio.  
  
 InitAction  
 Istruzione di inizializzazione  
  
 IterationAction  
 Istruzione iterativa  
  
 Condizione  
 Istruzione di continuazione  
  
 Corpo  
 Istruzione del corpo  
  
 L'attività eredita da <xref:System.Activities.NativeActivity> per ottenere l'accesso alle funzionalità di runtime, quale la pianificazione di attività aggiuntive da eseguire, usando uno dei metodi `ScheduleActivity` di <xref:System.Activities.NativeActivityContext>.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione For.sln.  
  
2.  Premere CTRL+MAIUSC+B per compilare la soluzione.  
  
3.  Eseguire la soluzione premendo F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\For`