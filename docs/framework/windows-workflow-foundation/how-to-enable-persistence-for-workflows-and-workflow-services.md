---
title: 'Procedura: abilitare la persistenza per i flussi di lavoro e i relativi servizi'
ms.date: 03/30/2017
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
ms.openlocfilehash: 5d0eeb8ad40f2f4f3349ab48487316014a561a1b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460888"
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a><span data-ttu-id="ad26f-102">Procedura: abilitare la persistenza per i flussi di lavoro e i relativi servizi</span><span class="sxs-lookup"><span data-stu-id="ad26f-102">How to: Enable Persistence for Workflows and Workflow Services</span></span>

<span data-ttu-id="ad26f-103">In questo argomento viene descritto come abilitare la persistenza dei flussi di lavoro e dei servizi flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ad26f-103">This topic describes how to enable persistence for workflows and workflow services.</span></span>

## <a name="enable-persistence-for-workflows"></a><span data-ttu-id="ad26f-104">Abilitare la persistenza dei flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="ad26f-104">Enable Persistence for Workflows</span></span>

<span data-ttu-id="ad26f-105">È possibile associare un archivio di istanze a un **WorkflowApplication** usando la proprietà <xref:System.Activities.WorkflowApplication.InstanceStore%2A> della classe <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="ad26f-105">You can associate an instance store with a **WorkflowApplication** by using the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property of the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="ad26f-106">Il metodo <xref:System.Activities.WorkflowApplication.Persist%2A> salva o rende persistente un flusso di lavoro nell'archivio di istanze associato all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ad26f-106">The <xref:System.Activities.WorkflowApplication.Persist%2A> method saves or persists a workflow into the instance store associated with the application.</span></span> <span data-ttu-id="ad26f-107">Il metodo <xref:System.Activities.WorkflowApplication.Unload%2A> rende persistente un flusso di lavoro nell'archivio di istanze, quindi scarica l'istanza dalla memoria.</span><span class="sxs-lookup"><span data-stu-id="ad26f-107">The <xref:System.Activities.WorkflowApplication.Unload%2A> method persists a workflow into the instance store and then unloads the instance from the memory.</span></span> <span data-ttu-id="ad26f-108">Il metodo **Load** carica un flusso di lavoro in memoria usando i dati del flusso di lavoro archiviati nell'archivio di persistenza dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="ad26f-108">The **Load** method loads a workflow into memory using the workflow data stored in the instance persistence store.</span></span>

<span data-ttu-id="ad26f-109">Il metodo di **salvataggio permanente** esegue i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad26f-109">The **Persist** method performs the following steps:</span></span>

1. <span data-ttu-id="ad26f-110">Sospende l'utilità di pianificazione del flusso di lavoro e attende finché il flusso di lavoro non entra nello stato inattivo.</span><span class="sxs-lookup"><span data-stu-id="ad26f-110">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>

2. <span data-ttu-id="ad26f-111">Rende persistente o salva il flusso di lavoro nell'archivio di persistenza.</span><span class="sxs-lookup"><span data-stu-id="ad26f-111">Persists or saves the workflow into the persistence store.</span></span>

3. <span data-ttu-id="ad26f-112">Riprende l'utilità di pianificazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ad26f-112">Resumes the workflow scheduler.</span></span>

 <span data-ttu-id="ad26f-113">Il metodo **unload** esegue i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad26f-113">The **Unload** method performs the following steps:</span></span>

1. <span data-ttu-id="ad26f-114">Sospende l'utilità di pianificazione del flusso di lavoro e attende finché il flusso di lavoro non entra nello stato inattivo.</span><span class="sxs-lookup"><span data-stu-id="ad26f-114">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>

2. <span data-ttu-id="ad26f-115">Rende persistente o salva il flusso di lavoro nell'archivio di persistenza.</span><span class="sxs-lookup"><span data-stu-id="ad26f-115">Persists or saves the workflow into the persistence store.</span></span>

3. <span data-ttu-id="ad26f-116">Elimina l'istanza del flusso di lavoro nella memoria.</span><span class="sxs-lookup"><span data-stu-id="ad26f-116">Disposes the workflow instance in the memory.</span></span>

<span data-ttu-id="ad26f-117">Entrambi i metodi di **salvataggio permanente** e di **scaricamento** si bloccherà mentre un flusso di lavoro si trova in un'area di non salvataggio permanente finché il flusso di lavoro non esce dall'area di non salvataggio permanente.</span><span class="sxs-lookup"><span data-stu-id="ad26f-117">Both the **Persist** and **Unload** methods will block while a workflow is in a no-persist zone until the workflow exits the no-persist zone.</span></span> <span data-ttu-id="ad26f-118">Il metodo continua l'operazione di persistenza o di scarico una volta completata l'area di non persistenza.</span><span class="sxs-lookup"><span data-stu-id="ad26f-118">The method continues with the persist or unload operation after the no-persist zone completes.</span></span> <span data-ttu-id="ad26f-119">Se l'area di non persistenza non viene completata prima della scadenza del timeout, o se il processo di persistenza impiega molto tempo, verrà generata un'eccezione TimeoutException.</span><span class="sxs-lookup"><span data-stu-id="ad26f-119">If the no-persist zone does not complete before the time-out elapses, or if the persistence process takes too long, a TimeoutException will be thrown.</span></span>

## <a name="enable-persistence-for-workflow-services-in-code"></a><span data-ttu-id="ad26f-120">Abilitare la persistenza dei servizi flusso di lavoro nel codice</span><span class="sxs-lookup"><span data-stu-id="ad26f-120">Enable Persistence for Workflow Services in Code</span></span>

<span data-ttu-id="ad26f-121">Il membro **DurableInstancingOptions** della classe <xref:System.ServiceModel.WorkflowServiceHost> dispone di una proprietà denominata **InstanceStore** che è possibile utilizzare per associare un archivio di istanze a **WorkflowServiceHost**.</span><span class="sxs-lookup"><span data-stu-id="ad26f-121">The **DurableInstancingOptions** member of the <xref:System.ServiceModel.WorkflowServiceHost> class has a property named **InstanceStore** that you can use to associate an instance store with the **WorkflowServiceHost**.</span></span>

```csharp
// wsh is an instance of WorkflowServiceHost class
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();
```

<span data-ttu-id="ad26f-122">Quando l'oggetto **WorkflowServiceHost** viene aperto, la persistenza viene abilitata automaticamente se **DurableInstancingOptions. InstanceStore** non è null.</span><span class="sxs-lookup"><span data-stu-id="ad26f-122">When the **WorkflowServiceHost** is opened, persistence is automatically enabled if the **DurableInstancingOptions.InstanceStore** is not null.</span></span>

<span data-ttu-id="ad26f-123">In genere, un comportamento del servizio fornisce l'archivio di istanze concrete da usare con un host del servizio flusso di lavoro usando la proprietà **InstanceStore** .</span><span class="sxs-lookup"><span data-stu-id="ad26f-123">Typically, a service behavior provides the concrete instance store to be used with a workflow service host by using the **InstanceStore** property.</span></span> <span data-ttu-id="ad26f-124">Ad esempio, SqlWorkflowInstanceStoreBehavior crea un'istanza di **SqlWorkflowInstanceStore**, la configura e la assegna a **DurableInstancingOptions. InstanceStore**.</span><span class="sxs-lookup"><span data-stu-id="ad26f-124">For example, the SqlWorkflowInstanceStoreBehavior creates an instance of the **SqlWorkflowInstanceStore**, configures it, and assigns it to the **DurableInstancingOptions.InstanceStore**.</span></span>

## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a><span data-ttu-id="ad26f-125">Abilitare la persistenza per i servizi flusso di lavoro tramite un file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ad26f-125">Enable Persistence for Workflow Services Using an Application Configuration File</span></span>

<span data-ttu-id="ad26f-126">È possibile abilitare la persistenza usando un file di configurazione dell'applicazione tramite l'aggiunta al file app.config o web.config del codice riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ad26f-126">Persistence can be enabled using an application configuration file by adding the following code to your app.config or web.config file:</span></span>

```xml
<configuration>
  <system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior name="myBehavior">
          <sqlWorkflowInstanceStore connectionString="Data Source=myDatabaseServer;Initial Catalog=myPersistenceDatabase" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```
