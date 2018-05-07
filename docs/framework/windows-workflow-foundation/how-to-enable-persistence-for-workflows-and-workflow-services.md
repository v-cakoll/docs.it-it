---
title: 'Procedura: abilitare la persistenza per i flussi di lavoro e i relativi servizi'
ms.date: 03/30/2017
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
ms.openlocfilehash: 35158c45217e764bc2e27dac26f8d680e5897fa9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a>Procedura: abilitare la persistenza per i flussi di lavoro e i relativi servizi
In questo argomento viene descritto come abilitare la persistenza dei flussi di lavoro e dei servizi flusso di lavoro.  
  
## <a name="enable-persistence-for-workflows"></a>Abilitare la persistenza dei flussi di lavoro  
 È possibile associare un archivio di istanze con un **WorkflowApplication** utilizzando il <xref:System.Activities.WorkflowApplication.InstanceStore%2A> proprietà la <xref:System.Activities.WorkflowApplication> classe. Il metodo <xref:System.Activities.WorkflowApplication.Persist%2A> salva o rende persistente un flusso di lavoro nell'archivio di istanze associato all'applicazione. Il metodo <xref:System.Activities.WorkflowApplication.Unload%2A> rende persistente un flusso di lavoro nell'archivio di istanze, quindi scarica l'istanza dalla memoria. Il **carico** metodo carica un flusso di lavoro in memoria usando i dati del flusso di lavoro archiviati nell'archivio di persistenza di istanza.  
  
 Il **Persist** metodo esegue i passaggi seguenti:  
  
1.  Sospende l'utilità di pianificazione del flusso di lavoro e attende finché il flusso di lavoro non entra nello stato inattivo.  
  
2.  Rende persistente o salva il flusso di lavoro nell'archivio di persistenza.  
  
3.  Riprende l'utilità di pianificazione del flusso di lavoro.  
  
 Il **scaricamento** metodo esegue i passaggi seguenti:  
  
1.  Sospende l'utilità di pianificazione del flusso di lavoro e attende finché il flusso di lavoro non entra nello stato inattivo.  
  
2.  Rende persistente o salva il flusso di lavoro nell'archivio di persistenza.  
  
3.  Elimina l'istanza del flusso di lavoro nella memoria.  
  
 Entrambi i **Persist** e **scaricamento** metodi verranno bloccati mentre un flusso di lavoro è in una zona di non persistenza finché non esce da tale area. Il metodo continua l'operazione di persistenza o di scarico una volta completata l'area di non persistenza. Se l'area di non persistenza non viene completata prima della scadenza del timeout, o se il processo di persistenza impiega molto tempo, verrà generata un'eccezione TimeoutException.  
  
## <a name="enable-persistence-for-workflow-services-in-code"></a>Abilitare la persistenza dei servizi flusso di lavoro nel codice  
 Il **DurableInstancingOptions** appartenente il <xref:System.ServiceModel.WorkflowServiceHost> classe dispone di una proprietà denominata **InstanceStore** che è possibile utilizzare per associare un archivio di istanze con il **WorkflowServiceHost** .  
  
```  
// wsh is an instance of WorkflowServiceHost class  
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();  
```  
  
 Quando il **WorkflowServiceHost** è aperto, la persistenza viene abilitata automaticamente se il **Durableinstancingoptions** non è null.  
  
 In genere, un comportamento del servizio fornisce l'archivio di istanze concreto da usare con un host del servizio del flusso di lavoro utilizzando il **InstanceStore** proprietà. Ad esempio, l'oggetto SqlWorkflowInstanceStoreBehavior crea un'istanza del **SqlWorkflowInstanceStore**, configura e lo assegna al **Durableinstancingoptions**.  
  
## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a>Abilitare la persistenza per i servizi flusso di lavoro tramite un file di configurazione dell'applicazione.  
 È possibile abilitare la persistenza usando un file di configurazione dell'applicazione tramite l'aggiunta al file app.config o web.config del codice riportato di seguito:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="myBehavior">  
          <SqlWorkflowInstanceStore connectionString="Data Source=myDatatbaseServer;Initial Catalog=myPersistenceDatabase">  
        </behavior>  
      </serviceBehaviors>  
    <behaviors>  
  </system.serviceModel>  
</configuration>  
```
