---
title: Attività di promozione proprietà
ms.date: 03/30/2017
ms.assetid: 802196b7-1159-4c05-b41b-d3bfdfcc88d9
ms.openlocfilehash: 6e059a0d344e6c62833feaa890c459c141a49673
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43481137"
---
# <a name="property-promotion-activity"></a><span data-ttu-id="3b0a0-102">Attività di promozione proprietà</span><span class="sxs-lookup"><span data-stu-id="3b0a0-102">Property Promotion Activity</span></span>
<span data-ttu-id="3b0a0-103">In questo esempio viene fornita una soluzione end-to-end che integra direttamente la funzionalità di promozione <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> nella creazione di flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-103">This sample provides an end-to-end solution that integrates the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> Promotion feature directly into the workflow authoring experience.</span></span> <span data-ttu-id="3b0a0-104">Vengono forniti inoltre una raccolta di elementi di configurazione, attività ed estensioni del flusso di lavoro che semplificano l'uso della funzionalità di promozione.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-104">A collection of configuration elements, workflow activities, and workflow extensions that simplify the use of the Promotion feature are provided.</span></span> <span data-ttu-id="3b0a0-105">Nell'esempio è contenuto infine un semplice flusso di lavoro che dimostra come usare la raccolta.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-105">Additionally, the sample contains a simple workflow that demonstrates how to use this collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b0a0-106">Gli esempi vengono forniti solo a scopo didattico.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-106">Samples are provided for educational purposes only.</span></span> <span data-ttu-id="3b0a0-107">Non sono destinati né sono stati testati in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-107">They are not intended for a production environment, and have not been tested in a production environment.</span></span> <span data-ttu-id="3b0a0-108">Microsoft non fornisce supporto tecnico per questi esempi.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-108">Microsoft does not provide technical support for these samples.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3b0a0-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3b0a0-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="3b0a0-110">Un database <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> inizializzato</span><span class="sxs-lookup"><span data-stu-id="3b0a0-110">An initialized <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> database</span></span>  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]  
  
## <a name="sample-projects"></a><span data-ttu-id="3b0a0-111">Progetti di esempio</span><span class="sxs-lookup"><span data-stu-id="3b0a0-111">Sample Projects</span></span>  
  
-   <span data-ttu-id="3b0a0-112">Il **PropertyPromotionActivity** progetto contiene file relativi agli elementi di configurazione specifica dell'innalzamento di livello, le attività del flusso di lavoro e le estensioni del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-112">The **PropertyPromotionActivity** project contains files pertaining to the promotion-specific configuration elements, workflow activities, and workflow extensions.</span></span>  
  
-   <span data-ttu-id="3b0a0-113">Il **CounterServiceApplication** progetto contiene un flusso di lavoro di esempio che usa le **SqlWorkflowInstanceStorePromotion** progetto.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-113">The **CounterServiceApplication** project contains a sample workflow that uses the **SqlWorkflowInstanceStorePromotion** project.</span></span>  
  
-   <span data-ttu-id="3b0a0-114">Uno script SQL (PropertyPromotionActivitySQLSample.sql) che è necessario eseguire nel database <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-114">A SQL script (PropertyPromotionActivitySQLSample.sql) that must be run against the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> database.</span></span>  
  
-   <span data-ttu-id="3b0a0-115">Un file della soluzione che collega i due progetti [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] (`PropertyPromotionActivity.sln`)</span><span class="sxs-lookup"><span data-stu-id="3b0a0-115">A solution file that links the two [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] projects (`PropertyPromotionActivity.sln`)</span></span>  
  
## <a name="to-set-up-and-run-the-sample"></a><span data-ttu-id="3b0a0-116">Per impostare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="3b0a0-116">To set up and run the sample</span></span>  
  
1.  <span data-ttu-id="3b0a0-117">Inizializzare un database di persistenza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-117">Initialize a workflow persistence database.</span></span>  
  
    1.  <span data-ttu-id="3b0a0-118">Passare alla directory di esempio (\WF\Basic\Persistence\PropertyPromotionActivity) ed eseguire CreateInstanceStore.cmd.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-118">Navigate to the sample directory (\WF\Basic\Persistence\PropertyPromotionActivity) and run CreateInstanceStore.cmd.</span></span>  
  
    2.  <span data-ttu-id="3b0a0-119">Se i privilegi di amministratore non sono disponibili, creare un account di accesso di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-119">If Administrator privileges are not available, create a SQL Server login.</span></span> <span data-ttu-id="3b0a0-120">In SQL Server Management Studio, passare a **sicurezza**, **accessi**.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-120">In SQL Server Management Studio, go to **Security**, **Logins**.</span></span> <span data-ttu-id="3b0a0-121">Fare doppio clic su **gli account di accesso** e creare un nuovo account di accesso.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-121">Right-click **Logins** and create a new login.</span></span> <span data-ttu-id="3b0a0-122">Aggiungere l'utente ACL al ruolo SQL aprendo **database**, **InstanceStore**, **sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-122">Add your ACL user to the SQL role by opening **Databases**, **InstanceStore**, **Security**.</span></span> <span data-ttu-id="3b0a0-123">Fare doppio clic su **gli utenti** e selezionare **nuovo utente**.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-123">Right-click **Users** and select **New user**.</span></span> <span data-ttu-id="3b0a0-124">Impostare il **nome account di accesso** all'utente creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-124">Set the **Login name** to the user created above.</span></span> <span data-ttu-id="3b0a0-125">Aggiungere l'utente all'appartenenza ai ruoli del database System.Activities.DurableInstancing.InstanceStoreUsers (e altri).</span><span class="sxs-lookup"><span data-stu-id="3b0a0-125">Add the user to the Database role membership System.Activities.DurableInstancing.InstanceStoreUsers (and others).</span></span> <span data-ttu-id="3b0a0-126">Notare che l'utente potrebbe essere già presente (ad esempio, utente dbo).</span><span class="sxs-lookup"><span data-stu-id="3b0a0-126">Note that the user might exist already (for example, user dbo).</span></span>  
  
2.  <span data-ttu-id="3b0a0-127">Aprire il file della soluzione PropertyPromotionActivity.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b0a0-127">Open the PropertyPromotionActivity.sln solution file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="3b0a0-128">Se l'archivio di istanze è stato creato in un database diverso da un'installazione locale di SQL Server Express, è necessario aggiornare la stringa di connessione di database.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-128">If you created the instance store in a database other than a local installation of SQL Server Express, then you must update the database connection string.</span></span> <span data-ttu-id="3b0a0-129">Modificare il file app. config sotto il **CounterServiceApplication** impostando il valore della `connectionString` dell'attributo sul `sqlWorkflowInstanceStorePromotion` nodo in modo che punti al database di persistenza inizializzato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-129">Alter the App.config file under the **CounterServiceApplication** by setting the value of the `connectionString` attribute on the `sqlWorkflowInstanceStorePromotion` node so that it points to the persistence database that was initialized in step 1.</span></span>  
  
4.  <span data-ttu-id="3b0a0-130">Compilare ed eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-130">Build and run the solution.</span></span> <span data-ttu-id="3b0a0-131">Verranno avviati il servizio Counter WF e, automaticamente, un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-131">This will start the Counter WF service and automatically start a workflow instance.</span></span>  
  
5.  <span data-ttu-id="3b0a0-132">Selezionare rapidamente tutte le righe nella vista [dbo].[CounterService] del database di persistenza (aggiunta tramite l'esecuzione di CreateInstanceStore.cmd nel passaggio 1).</span><span class="sxs-lookup"><span data-stu-id="3b0a0-132">Quickly select all the rows in the [dbo].[CounterService] view in your persistence database (this view was added by running CreateInstanceStore.cmd in step 1).</span></span> <span data-ttu-id="3b0a0-133">Il set di risultati sarà analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="3b0a0-133">You will see a result set similar to the following:</span></span>  
  
    |<span data-ttu-id="3b0a0-134">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3b0a0-134">InstanceId</span></span>|<span data-ttu-id="3b0a0-135">CounterValue</span><span class="sxs-lookup"><span data-stu-id="3b0a0-135">CounterValue</span></span>|<span data-ttu-id="3b0a0-136">CounterValueLastUpdated</span><span class="sxs-lookup"><span data-stu-id="3b0a0-136">CounterValueLastUpdated</span></span>|  
    |----------------|------------------|-----------------------------|  
    |<span data-ttu-id="3b0a0-137">2FA2C302-929E-4C0D-8C25-768A3DA20CE5</span><span class="sxs-lookup"><span data-stu-id="3b0a0-137">2FA2C302-929E-4C0D-8C25-768A3DA20CE5</span></span>|<span data-ttu-id="3b0a0-138">12</span><span class="sxs-lookup"><span data-stu-id="3b0a0-138">12</span></span>|<span data-ttu-id="3b0a0-139">2010-02-18 22:48:01.740</span><span class="sxs-lookup"><span data-stu-id="3b0a0-139">2010-02-18 22:48:01.740</span></span>|  
  
     <span data-ttu-id="3b0a0-140">Man mano che si procede con l'aggiornamento della vista, si noterà che gli elementi CounterValue e CounterValueLastUpdated vengono modificati ogni due secondi,</span><span class="sxs-lookup"><span data-stu-id="3b0a0-140">As you keep refreshing the view, you will notice that CounterValue and CounterValueLastUpdated change every two seconds.</span></span> <span data-ttu-id="3b0a0-141">che rappresentano l'intervallo di aggiornamento del contatore.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-141">This is the interval at which the counter updates itself.</span></span> <span data-ttu-id="3b0a0-142">CounterValue e CounterValueLastUpdated rappresentano proprietà promosse per questo flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-142">CounterValue and CounterValueLastUpdated represent promoted properties for this workflow.</span></span>  
  
## <a name="to-remove-the-sample"></a><span data-ttu-id="3b0a0-143">Per rimuovere l'esempio</span><span class="sxs-lookup"><span data-stu-id="3b0a0-143">To remove the sample</span></span>  
  
-   <span data-ttu-id="3b0a0-144">Eseguire RemoveInstanceStore.cmd nella directory di esempio (\WF\Basic\Persistence\PropertyPromotionActivity).</span><span class="sxs-lookup"><span data-stu-id="3b0a0-144">Run RemoveInstanceStore.cmd in the sample directory (\WF\Basic\Persistence\PropertyPromotionActivity).</span></span>  
  
## <a name="understanding-this-sample"></a><span data-ttu-id="3b0a0-145">Informazioni sull'esempio</span><span class="sxs-lookup"><span data-stu-id="3b0a0-145">Understanding This Sample</span></span>  
 <span data-ttu-id="3b0a0-146">Nell'esempio sono contenuti due progetti e un file SQL:</span><span class="sxs-lookup"><span data-stu-id="3b0a0-146">The sample contains two projects and an SQL file:</span></span>  
  
-   <span data-ttu-id="3b0a0-147">**CounterServiceApplication** è un'applicazione console che ospita un servizio Counter WF semplice.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-147">**CounterServiceApplication** is a console application that hosts a simple Counter WF service.</span></span> <span data-ttu-id="3b0a0-148">Alla ricezione di un messaggio unidirezionale tramite l'endpoint `Start`, il flusso di lavoro conta da 0 a 29, incrementando una variabile del contatore ogni due secondi.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-148">Upon receiving a one-way message through the `Start` endpoint, the workflow counts from 0 to 29, incrementing a counter variable every two seconds.</span></span> <span data-ttu-id="3b0a0-149">Dopo ogni incremento del contatore, il flusso di lavoro è persistente e le proprietà promosse vengono aggiornate nella vista [dbo].[CounterService].</span><span class="sxs-lookup"><span data-stu-id="3b0a0-149">After every counter increment, the workflow persists, and the promoted properties are updated in the [dbo].[CounterService] view.</span></span> <span data-ttu-id="3b0a0-150">Quando viene eseguita, l'applicazione console ospita il servizio WF e invia un messaggio all'endpoint `Start`, creando un'istanza di Counter WF.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-150">When the console application is run, it hosts the WF service and sends a message to the `Start` endpoint, creating a Counter WF instance.</span></span>  
  
-   <span data-ttu-id="3b0a0-151">**PropertyPromotionActivity** è una libreria di classi che contiene gli elementi di configurazione, le attività del flusso di lavoro e le estensioni del flusso di lavoro che il **CounterServiceApplication** Usa.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-151">**PropertyPromotionActivity** is a class library that contains the configuration elements, workflow activities, and workflow extensions that the **CounterServiceApplication** uses.</span></span>  
  
-   <span data-ttu-id="3b0a0-152">**Propertypromotionactivitysqlsample. SQL** crea e aggiunge la vista [dbo]. [ CounterService] al database.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-152">**PropertyPromotionActivitySQLSample.sql** creates and adds the view [dbo].[CounterService] to the database.</span></span>  
  
### <a name="counterserviceapplication"></a><span data-ttu-id="3b0a0-153">CounterServiceApplication</span><span class="sxs-lookup"><span data-stu-id="3b0a0-153">CounterServiceApplication</span></span>  
  
#### <a name="using-the-sqlworkflowinstancestorepromotion-configuration-element"></a><span data-ttu-id="3b0a0-154">Utilizzo dell'elemento di configurazione SqlWorkflowInstanceStorePromotion</span><span class="sxs-lookup"><span data-stu-id="3b0a0-154">Using the SqlWorkflowInstanceStorePromotion Configuration Element</span></span>  
 <span data-ttu-id="3b0a0-155">L'elemento di configurazione `SqlWorkflowInstanceStorePromotion` eredita dall'elemento di configurazione `SqlWorkflowInstanceStore`, ma aggiunge un ulteriore elemento denominato `promotionSets`.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-155">The `SqlWorkflowInstanceStorePromotion` configuration element inherits from the `SqlWorkflowInstanceStore` configuration element, but adds an additional configuration element called `promotionSets`.</span></span> <span data-ttu-id="3b0a0-156">L'elemento `promotionSets` consente all'utente di specificare proprietà promosse tramite la configurazione.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-156">The `promotionSets` element enables the user to specify promoted properties through configuration.</span></span> <span data-ttu-id="3b0a0-157">Il file di configurazione usato nell'esempio è il seguente:</span><span class="sxs-lookup"><span data-stu-id="3b0a0-157">This is the configuration file that is used by the sample:</span></span>  
  
```xml  
<sqlWorkflowInstanceStorePromotion connectionString ="Data Source=.;Initial Catalog=SqlWorkflowInstanceStoreTest;Integrated Security=True;">  
  <promotionSets>  
    <promotionSet name="CounterService">  
      <promotedValue propertyName="Count"/>  
      <promotedValue propertyName="LastIncrementedAt"/>  
    </promotionSet>  
  </promotionSets>  
</sqlWorkflowInstanceStorePromotion>  
```  
  
 <span data-ttu-id="3b0a0-158">Esaminare la definizione per la vista [dbo].[CounterService].</span><span class="sxs-lookup"><span data-stu-id="3b0a0-158">Examine the definition for the [dbo].[CounterService] view.</span></span>  
  
```sql  
create view [dbo].[CounterService] as  
      select [InstanceId],  
 [Value1] as [CounterValue],  
 [Value2] as [CounterValueLastUpdated]  
      from [System.Activities.DurableInstancing].[InstancePromotedProperties]  
      where [PromotionName] = 'CounterService'  
go  
```  
  
 <span data-ttu-id="3b0a0-159">Quando un'istanza del flusso di lavoro è persistente, una riga viene inserita nella vista `InstancePromotedProperties` per ogni `PromotionSet` definito nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-159">When a workflow instance persists, a row is inserted into the `InstancePromotedProperties` view for each `PromotionSet` defined in the configuration.</span></span> <span data-ttu-id="3b0a0-160">Questa riga contiene tutte le proprietà promosse di `PromotionSet` (una proprietà promossa per colonna).</span><span class="sxs-lookup"><span data-stu-id="3b0a0-160">This row contains all the promoted properties of the `PromotionSet` (one promoted property per column).</span></span> <span data-ttu-id="3b0a0-161">Questo elemento `PromotionSet` è collegato con chiave dalla tupla `InstanceId, PromotionName`.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-161">This `PromotionSet` is keyed by the tuple: `InstanceId, PromotionName`.</span></span> <span data-ttu-id="3b0a0-162">In questo esempio è presente un elemento `PromotionSet` definito in una configurazione il cui attributo name è `CounterService`.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-162">In this sample, we have one `PromotionSet` defined in configuration whose name attribute is `CounterService`.</span></span> <span data-ttu-id="3b0a0-163">Si noti che il valore della colonna `PromotionName` è uguale all'attributo name `PromotionSet`.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-163">Note how the `PromotionName` column value is equal to the name attribute of the `PromotionSet` element.</span></span>  
  
 <span data-ttu-id="3b0a0-164">L'ordine degli elementi di `promotedValue` è correlato alla posizione delle proprietà promosse nella visualizzazione `InstancePromotedProperties`.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-164">The order of the `promotedValue` elements correlates with the placement of the promoted properties in the `InstancePromotedProperties` view.</span></span> <span data-ttu-id="3b0a0-165">`Count` è il primo elemento di `promotedValue`.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-165">`Count` is the first `promotedValue` element.</span></span> <span data-ttu-id="3b0a0-166">Di conseguenza, tale elemento viene mappato alla colonna `Value1` nella vista `InstancePromotedProperties`.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-166">As a result, it is mapped to the `Value1` column in the `InstancePromotedProperties` view.</span></span> <span data-ttu-id="3b0a0-167">`LastIncrementedAt` è il secondo elemento di `promotedValue`.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-167">`LastIncrementedAt` is the second `promotedValue` element.</span></span> <span data-ttu-id="3b0a0-168">Di conseguenza, tale elemento viene mappato alla colonna `Value2` nella vista `InstancePromotedProperties`.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-168">As a result, it is mapped to the `Value2` column in the `InstancePromotedProperties` view.</span></span>  
  
#### <a name="using-the-promotevalue-activity"></a><span data-ttu-id="3b0a0-169">Utilizzo dell'attività PromoteValue</span><span class="sxs-lookup"><span data-stu-id="3b0a0-169">Using the PromoteValue Activity</span></span>  
 <span data-ttu-id="3b0a0-170">Esaminare il file Counterservice in Windows Workflow Foundation Designer.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-170">Examine the CounterService.xamlx file in the Windows Workflow Foundation Designer.</span></span> <span data-ttu-id="3b0a0-171">Si noti che sono presenti due attività speciali nella definizione WF, ovvero `PromoteValue<DateTime>` e `PromoteValue<Int32>`.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-171">Notice that there are two special activities in the WF definition: `PromoteValue<DateTime>` and `PromoteValue<Int32>`.</span></span>  
  
 <span data-ttu-id="3b0a0-172">All'attività `PromoteValue<Int32>` è associato il membro `Name` definito come `Count`.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-172">The `PromoteValue<Int32>` activity has its `Name` member defined as `Count`.</span></span> <span data-ttu-id="3b0a0-173">che corrisponde al primo elemento `promotedValue` nella configurazione e per cui il relativo elemento `Value` è definito come variabile del flusso di lavoro `Counter`.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-173">This matches with the first `promotedValue` element in the configuration, and has its `Value` defined as the `Counter` workflow variable.</span></span> <span data-ttu-id="3b0a0-174">Quando il flusso di lavoro è persistente, la variabile del flusso di lavoro `Counter` viene resa persistente come proprietà promossa nella colonna `Value1` della vista `InstancePromotedProperties`.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-174">When the workflow persists, the `Counter` workflow variable is persisted as a promoted property into the `Value1` column of the `InstancePromotedProperties` view.</span></span>  
  
 <span data-ttu-id="3b0a0-175">All'attività `PromoteValue<DateTime>` è associato il membro `Name` definito come `LastIncrementedAt`</span><span class="sxs-lookup"><span data-stu-id="3b0a0-175">The `PromoteValue<DateTime>` activity has its `Name` member defined as `LastIncrementedAt`.</span></span> <span data-ttu-id="3b0a0-176">che corrisponde al secondo elemento `promotedValue` nella configurazione e per cui il relativo elemento `Value` è definito come variabile del flusso di lavoro `TimeLastIncremented`.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-176">This matches with the second `promotedValue` element in the configuration, and has its `Value` defined as the `TimeLastIncremented` workflow variable.</span></span> <span data-ttu-id="3b0a0-177">Questo significa che quando il flusso di lavoro è persistente, la variabile del flusso di lavoro `TimeLastIncremented` verrà resa persistente come proprietà promossa nella colonna `Value2` della vista `InstancePromotedProperties`.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-177">This means that when the workflow persists, the value for the `TimeLastIncremented` workflow variable will be persisted as a promoted property into the `Value2` column of the `InstancePromotedProperties` view.</span></span>  
  
 <span data-ttu-id="3b0a0-178">Si noti che all'attività `PromotedValue` è inoltre associato un membro di tipo Boolean denominato `ClearExistingPromotedData`.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-178">Note that the `PromotedValue` activity also has a Boolean member called `ClearExistingPromotedData`.</span></span> <span data-ttu-id="3b0a0-179">Quando questo membro è impostato su `true`, vengono cancellate tutti i valori della proprietà promossa fino al punto specifico nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-179">When this member is set to `true`, this clears all the promoted property values up to that point in the workflow.</span></span> <span data-ttu-id="3b0a0-180">Se ad esempio un'attività Sequence è definita come segue:</span><span class="sxs-lookup"><span data-stu-id="3b0a0-180">For example, if a Sequence activity is defined as follows:</span></span>  
  
1.  <span data-ttu-id="3b0a0-181">PromoteValue {Name = "Conteggio", valore = 3}</span><span class="sxs-lookup"><span data-stu-id="3b0a0-181">PromoteValue { Name = "Count", Value = 3}</span></span>  
  
2.  <span data-ttu-id="3b0a0-182">PromoteValue {Name = "LastIncrementedAt", valore = 1-1 a 2000}</span><span class="sxs-lookup"><span data-stu-id="3b0a0-182">PromoteValue {Name = "LastIncrementedAt", Value = 1-1-2000 }</span></span>  
  
3.  <span data-ttu-id="3b0a0-183">Persist</span><span class="sxs-lookup"><span data-stu-id="3b0a0-183">Persist</span></span>  
  
4.  <span data-ttu-id="3b0a0-184">PromoteValue {Name = "Conteggio", valore = 4, ClearExistingPromotedData = true}</span><span class="sxs-lookup"><span data-stu-id="3b0a0-184">PromoteValue {Name = "Count", Value = 4, ClearExistingPromotedData = true}</span></span>  
  
5.  <span data-ttu-id="3b0a0-185">Persist</span><span class="sxs-lookup"><span data-stu-id="3b0a0-185">Persist</span></span>  
  
 <span data-ttu-id="3b0a0-186">Al secondo Persist, il valore promosso per `Count` sarà 4</span><span class="sxs-lookup"><span data-stu-id="3b0a0-186">On the second persist, the promoted value for `Count` will be 4.</span></span> <span data-ttu-id="3b0a0-187">Tuttavia, il valore promosso per `LastIncrementedAt` saranno `NULL`.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-187">However, the promoted value for `LastIncrementedAt` will be `NULL`.</span></span> <span data-ttu-id="3b0a0-188">Se `ClearExistingPromotedData` non fosse stato impostato su `true` nel passaggio 4, dopo il secondo Persist il valore promosso per Count sarebbe 4.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-188">If `ClearExistingPromotedData` was not set to `true` for step 4, then after the second persist, the promoted value for Count would be 4.</span></span> <span data-ttu-id="3b0a0-189">Di conseguenza, il valore promosso per `LastIncrementedAt` sarebbe ancora 1-1-2000.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-189">As a result, the promoted value for `LastIncrementedAt` would still be 1-1-2000.</span></span>  
  
### <a name="propertypromotionactivity"></a><span data-ttu-id="3b0a0-190">PropertyPromotionActivity</span><span class="sxs-lookup"><span data-stu-id="3b0a0-190">PropertyPromotionActivity</span></span>  
 <span data-ttu-id="3b0a0-191">Questa libreria di classi contiene le seguenti classi pubbliche che consentono di semplificare l'uso della funzionalità di promozione <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-191">This class library contains the following public classes to simplify use of the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> Promotion feature.</span></span>  
  
#### <a name="promotevalue-class"></a><span data-ttu-id="3b0a0-192">Classe PromoteValue</span><span class="sxs-lookup"><span data-stu-id="3b0a0-192">PromoteValue Class</span></span>  
 <span data-ttu-id="3b0a0-193">Questa classe promuove una proprietà.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-193">This class promotes one property.</span></span> <span data-ttu-id="3b0a0-194">Il nome della proprietà promossa deve corrispondere a un attributo name dell'elemento `promotedValue` nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-194">The name of the promoted property should match a name attribute of a `promotedValue` element in the configuration.</span></span> <span data-ttu-id="3b0a0-195">Questa attività può essere usata in Progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-195">This activity can be used in the Workflow Designer.</span></span> <span data-ttu-id="3b0a0-196">Per un esempio di utilizzo, vedere CounterServiceApplication.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-196">See the CounterServiceApplication for an example usage.</span></span>  
  
```csharp  
public class PromoteValue<T> : CodeActivity  
{  
    public PromoteValue()  
    {  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public string Name { get; set; }  
    public InArgument<T> Value { get; set; }  
}  
```  
  
 <span data-ttu-id="3b0a0-197">ClearExistingPromotedData (Bool)</span><span class="sxs-lookup"><span data-stu-id="3b0a0-197">ClearExistingPromotedData (Bool)</span></span>  
 <span data-ttu-id="3b0a0-198">Cancella tutti i valori promossi prima di questa attività.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-198">Clears all values that were promoted before this activity.</span></span>  
  
 <span data-ttu-id="3b0a0-199">Name (stringa)</span><span class="sxs-lookup"><span data-stu-id="3b0a0-199">Name (string)</span></span>  
 <span data-ttu-id="3b0a0-200">Nome che rappresenta la proprietà.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-200">The name that represents this property.</span></span> <span data-ttu-id="3b0a0-201">Deve corrispondere all'attributo name di un \<promotedValue > nella configurazione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-201">This should match the name attribute of a \<promotedValue> element in the configuration.</span></span>  
  
 <span data-ttu-id="3b0a0-202">Valore (InArgument\<T >)</span><span class="sxs-lookup"><span data-stu-id="3b0a0-202">Value (InArgument\<T>)</span></span>  
 <span data-ttu-id="3b0a0-203">La variabile o il valore da desidera archiviare nella colonna.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-203">The variable / value that you want to store in the column.</span></span>  
  
#### <a name="promotevalues-class"></a><span data-ttu-id="3b0a0-204">Classe PromoteValues</span><span class="sxs-lookup"><span data-stu-id="3b0a0-204">PromoteValues Class</span></span>  
 <span data-ttu-id="3b0a0-205">Questa classe promuove più proprietà.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-205">Promotes multiple properties.</span></span> <span data-ttu-id="3b0a0-206">I nomi delle proprietà promosse devono corrispondere a tutti gli attributi name degli elementi `promotedValue` nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-206">The names of the promoted properties should match all name attributes in the `promotedValue` elements in the configuration.</span></span> <span data-ttu-id="3b0a0-207">L'utilizzo è analogo a quello dell'attività `PromoteValue`, ad eccezione del fatto che è possibile promuovere più proprietà contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-207">Usage is similar to the `PromoteValue` activity, except for the fact that multiple properties can be promoted at the same time.</span></span> <span data-ttu-id="3b0a0-208">Questa attività non può essere usata in Progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-208">This activity cannot be used in the Workflow Designer.</span></span>  
  
```  
public class PromoteValues : CodeActivity  
{  
    public PromoteValues()  
    {  
        this.ValuesToPromote = new Dictionary<string, InArgument>();  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public IDictionary<string, InArgument> ValuesToPromote { get; set; }  
}  
```  
  
#### <a name="sqlworkflowinstancestorepromotionbehavior"></a><span data-ttu-id="3b0a0-209">SqlWorkflowInstanceStorePromotionBehavior</span><span class="sxs-lookup"><span data-stu-id="3b0a0-209">SqlWorkflowInstanceStorePromotionBehavior</span></span>  
 <span data-ttu-id="3b0a0-210">Classe derivata da `SqlWorkflowInstanceStoreBehavior`</span><span class="sxs-lookup"><span data-stu-id="3b0a0-210">Derives from `SqlWorkflowInstanceStoreBehavior`.</span></span> <span data-ttu-id="3b0a0-211">che aggiunge un partecipante di persistenza personalizzato (appartenente anche a questa libreria) come estensione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-211">This derived class adds a custom persistence participant (also a part of this library) as a workflow extension.</span></span> <span data-ttu-id="3b0a0-212">L'implementazione delle due attività del flusso di lavoro precedenti si basa su questo partecipante di persistenza personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-212">The implementation of the previous two workflow activities relies on this custom persistence participant.</span></span>  
  
```  
public class SqlWorkflowInstanceStorePromotionBehavior :  
             SqlWorkflowInstanceStoreBehavior, IServiceBehavior  
{  
        public void Promote(string name, IEnumerable<string> promoteAsSqlVariant,  
                            IEnumerable<string> promoteAsBinary)  
  
}  
```  
  
 <span data-ttu-id="3b0a0-213">Questa libreria di classi contiene inoltre l'implementazione di `ConfigurationElement` per `SqlWorkflowInstanceStorePromotionElement` e un partecipante di persistenza personalizzato usati dalle attività di promozione precedenti.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-213">This class library also contains the `ConfigurationElement` implementation for the `SqlWorkflowInstanceStorePromotionElement` and a custom persistence participant used by the previous promotion activities.</span></span>  
  
### <a name="propertypromotionactivitysqlsample"></a><span data-ttu-id="3b0a0-214">PropertyPromotionActivitySQLSample</span><span class="sxs-lookup"><span data-stu-id="3b0a0-214">PropertyPromotionActivitySQLSample</span></span>  
 <span data-ttu-id="3b0a0-215">Questo file SQL crea una vista `[dbo].[CounterService]`, oltre alla vista `[InstancePromotedProperties]`, per l'esecuzione di query su tutte le istanze a cui è associato una promozione CounterService impostata.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-215">This SQL file creates a `[dbo].[CounterService]` view in addition to the `[InstancePromotedProperties]` view for querying all instances that have a CounterService Promotion set.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3b0a0-216">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-216">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3b0a0-217">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-217">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3b0a0-218">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-218">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3b0a0-219">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="3b0a0-219">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\PropertyPromotionActivity`  
  
## <a name="see-also"></a><span data-ttu-id="3b0a0-220">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b0a0-220">See Also</span></span>  
 [<span data-ttu-id="3b0a0-221">Hosting di AppFabric e salvataggio permanente</span><span class="sxs-lookup"><span data-stu-id="3b0a0-221">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
