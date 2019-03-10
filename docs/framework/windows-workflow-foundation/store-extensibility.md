---
title: Estensibilità dell'archivio
ms.date: 03/30/2017
ms.assetid: 7c3f4a46-4bac-4138-ae6a-a7c7ee0d28f5
ms.openlocfilehash: 46c1ea40925a5c79180171da9a705d7e6b7c8b89
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703265"
---
# <a name="store-extensibility"></a><span data-ttu-id="1f42c-102">Estensibilità dell'archivio</span><span class="sxs-lookup"><span data-stu-id="1f42c-102">Store Extensibility</span></span>

<span data-ttu-id="1f42c-103"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> consente agli utenti di promuovere proprietà personalizzate specifiche dell'applicazione che possono essere usate per eseguire query per istanze nel database di persistenza.</span><span class="sxs-lookup"><span data-stu-id="1f42c-103"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> allows users to promote custom, application-specific properties that can be used to query for instances in the persistence database.</span></span> <span data-ttu-id="1f42c-104">L'atto di promuovere una proprietà fa in modo che il valore sia disponibile all'interno di una visualizzazione speciale nel database.</span><span class="sxs-lookup"><span data-stu-id="1f42c-104">The act of promoting a property causes the value to be available within a special view in the database.</span></span> <span data-ttu-id="1f42c-105">Queste proprietà promosse, ovvero proprietà che possono essere usate nelle query utente, possono essere di tipi semplici, ad esempio Int64, Guid, String e DateTime o di un tipo binario serializzato (byte[]).</span><span class="sxs-lookup"><span data-stu-id="1f42c-105">These promoted properties (properties that can be used in user queries) can be of simple types such as Int64, Guid, String, and DateTime or of a serialized binary type (byte[]).</span></span>

<span data-ttu-id="1f42c-106">La classe <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> dispone del metodo <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.Promote%2A> che può essere usato per promuovere una proprietà come proprietà utilizzabile nelle query.</span><span class="sxs-lookup"><span data-stu-id="1f42c-106">The <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> class has the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.Promote%2A> method that you can use to promote a property as a property that can be used in queries.</span></span> <span data-ttu-id="1f42c-107">Il seguente è un esempio end-to-end di estensibilità dell'archivio.</span><span class="sxs-lookup"><span data-stu-id="1f42c-107">The following example is an end-to-end example of store extensibility.</span></span>

1. <span data-ttu-id="1f42c-108">In questo scenario di esempio un'applicazione di elaborazione dei documenti (DP, Document Processing) dispone di flussi di lavoro in ognuno dei quali vengono usate attività personalizzate per l'elaborazione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="1f42c-108">In this example scenario, a document processing (DP) application has workflows, each of which uses custom activities for document processing.</span></span> <span data-ttu-id="1f42c-109">Questi flussi di lavoro dispongono di un set di variabili di stato che devono essere rese visibili all'utente finale.</span><span class="sxs-lookup"><span data-stu-id="1f42c-109">These workflows have a set of state variables that need to be made visible to the end user.</span></span> <span data-ttu-id="1f42c-110">A tale scopo, l'applicazione DP fornisce un'estensione dell'istanza di tipo <xref:System.Activities.Persistence.PersistenceParticipant>, usata da attività per fornire le variabili di stato.</span><span class="sxs-lookup"><span data-stu-id="1f42c-110">To achieve this, the DP application provides an instance extension of type <xref:System.Activities.Persistence.PersistenceParticipant>, which is used by activities to supply the state variables.</span></span>

    ```csharp
    class DocumentStatusExtension : PersistenceParticipant
    {
        public string DocumentId;
        public string ApprovalStatus;
        public string UserName;
        public DateTime LastUpdateTime;
    }
    ```

2. <span data-ttu-id="1f42c-111">La nuova estensione viene quindi aggiunta all'host.</span><span class="sxs-lookup"><span data-stu-id="1f42c-111">The new extension is then added to the host.</span></span>

    ```csharp
    static Activity workflow = CreateWorkflow();
    WorkflowApplication application = new WorkflowApplication(workflow);
    DocumentStatusExtension documentStatusExtension = new DocumentStatusExtension ();
    application.Extensions.Add(documentStatusExtension);
    ```

     <span data-ttu-id="1f42c-112">Per altre informazioni sull'aggiunta di un partecipante di persistenza personalizzato, vedere la [partecipanti di persistenza](persistence-participants.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="1f42c-112">For more details about adding a custom persistence participant, see the [Persistence Participants](persistence-participants.md) sample.</span></span>

3. <span data-ttu-id="1f42c-113">Le attività personalizzate nell'applicazione DP popolano diversi campi di stato nel **Execute** (metodo).</span><span class="sxs-lookup"><span data-stu-id="1f42c-113">The custom activities in the DP application populate various status fields in the **Execute** method.</span></span>

    ```csharp
    public override void Execute(CodeActivityContext context)
    {
        // ...
        context.GetExtension<DocumentStatusExtension>().DocumentId = Guid.NewGuid();
        context.GetExtension<DocumentStatusExtension>().UserName = "John Smith";
        context.GetExtension<DocumentStatusExtension>().ApprovalStatus = "Approved";
        context.GetExtension<DocumentStatusExtension>().LastUpdateTime = DateTime.Now();
        // ...
    }
    ```

4. <span data-ttu-id="1f42c-114">Quando un'istanza del flusso di lavoro raggiunge un punto di persistenza, il **CollectValues** metodo per il **DocumentStatusExtension** partecipante di persistenza Salva queste proprietà nei dati di persistenza raccolta.</span><span class="sxs-lookup"><span data-stu-id="1f42c-114">When a workflow instance reaches a persistence point, the **CollectValues** method of the **DocumentStatusExtension** persistence participant saves these properties into the persistence data collection.</span></span>

    ```csharp
    class DocumentStatusExtension : PersistenceParticipant
    {
        const XNamespace xNS = XNamespace.Get("http://contoso.com/DocumentStatus");

        protected override void CollectValues(out IDictionary<XName, object> readWriteValues, out IDictionary<XName, object> writeOnlyValues)
        {
            readWriteValues = new Dictionary<XName, object>();
            readWriteValues.Add(xNS.GetName("UserName"), this.UserName);
            readWriteValues.Add(xNS.GetName("ApprovalStatus"), this.ApprovalStatus);
            readWriteValues.Add(xNS.GetName("DocumentId"), this.DocumentId);
            readWriteValues.Add(xNS.GetName("LastModifiedTime"), this.LastUpdateTime);

            writeOnlyValues = null;
        }
        // ...
    }
    ```

    > [!NOTE]
    > <span data-ttu-id="1f42c-115">Tutte queste proprietà vengono passate a **SqlWorkflowInstanceStore** con il framework di persistenza tramite il **Saveworkflowcommand** raccolta.</span><span class="sxs-lookup"><span data-stu-id="1f42c-115">All these properties are passed to **SqlWorkflowInstanceStore** by the persistence framework through the **SaveWorkflowCommand.InstanceData** collection.</span></span>

5. <span data-ttu-id="1f42c-116">L'applicazione DP Inizializza il Store di istanza del flusso di lavoro SQL e richiama il **Promote** metodo per promuovere questi dati.</span><span class="sxs-lookup"><span data-stu-id="1f42c-116">The DP application initializes the SQL Workflow Instance Store and invokes the **Promote** method to promote this data.</span></span>

    ```csharp
    SqlWorkflowInstanceStore store = new SqlWorkflowInstanceStore(connectionString);

    List<XName> variantProperties = new List<XName>()
    {
        xNS.GetName("UserName"),
        xNS.GetName("ApprovalStatus"),
        xNS.GetName("DocumentId"),
        xNS.GetName("LastModifiedTime")
    };

    store.Promote("DocumentStatus", variantProperties, null);
    ```

    <span data-ttu-id="1f42c-117">Queste informazioni di innalzamento di livello, in base **SqlWorkflowInstanceStore** inserisce le proprietà dei dati nelle colonne delle [InstancePromotedProperties](#InstancePromotedProperties) visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="1f42c-117">Based on this promotion information, **SqlWorkflowInstanceStore** places the data properties in the columns of the [InstancePromotedProperties](#InstancePromotedProperties) view.</span></span>

6. <span data-ttu-id="1f42c-118">Per eseguire una query su un subset dei dati dalla tabella di promozione, viene aggiunta una vista personalizzata nella parte superiore di tale vista da parte dell'applicazione DP.</span><span class="sxs-lookup"><span data-stu-id="1f42c-118">To query a subset of the data from the promotion table, the DP application adds a customized view on top of the promotion view.</span></span>

    ```sql
    create view [dbo].[DocumentStatus] with schemabinding
    as
        select  P.[InstanceId] as [InstanceId],
            P.Value1 as [UserName],
            P.Value2 as [ApprovalStatus],
            P.Value3 as [DocumentId],
            P.Value4 as [LastUpdatedTime]
    from [System.Activities.DurableInstancing].[InstancePromotedProperties] as P
    where P.PromotionName = N'DocumentStatus'
    go
    ```

## <a name="InstancePromotedProperties"></a> <span data-ttu-id="1f42c-119">[System.Activities.DurableInstancing.InstancePromotedProperties] view</span><span class="sxs-lookup"><span data-stu-id="1f42c-119">[System.Activities.DurableInstancing.InstancePromotedProperties] view</span></span>

|<span data-ttu-id="1f42c-120">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="1f42c-120">Column Name</span></span>|<span data-ttu-id="1f42c-121">Tipo di colonna</span><span class="sxs-lookup"><span data-stu-id="1f42c-121">Column Type</span></span>|<span data-ttu-id="1f42c-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1f42c-122">Description</span></span>|
|-----------------|-----------------|-----------------|
|<span data-ttu-id="1f42c-123">InstanceId</span><span class="sxs-lookup"><span data-stu-id="1f42c-123">InstanceId</span></span>|<span data-ttu-id="1f42c-124">GUID</span><span class="sxs-lookup"><span data-stu-id="1f42c-124">GUID</span></span>|<span data-ttu-id="1f42c-125">Istanza del flusso di lavoro a cui appartiene questa promozione.</span><span class="sxs-lookup"><span data-stu-id="1f42c-125">The workflow instance that this promotion belongs to.</span></span>|
|<span data-ttu-id="1f42c-126">PromotionName</span><span class="sxs-lookup"><span data-stu-id="1f42c-126">PromotionName</span></span>|<span data-ttu-id="1f42c-127">nvarchar(400)</span><span class="sxs-lookup"><span data-stu-id="1f42c-127">nvarchar(400)</span></span>|<span data-ttu-id="1f42c-128">Nome della promozione stessa.</span><span class="sxs-lookup"><span data-stu-id="1f42c-128">The name of the promotion itself.</span></span>|
|<span data-ttu-id="1f42c-129">Value1, Value2, Value3,..,Value32</span><span class="sxs-lookup"><span data-stu-id="1f42c-129">Value1, Value2, Value3,..,Value32</span></span>|<span data-ttu-id="1f42c-130">sql_variant</span><span class="sxs-lookup"><span data-stu-id="1f42c-130">sql_variant</span></span>|<span data-ttu-id="1f42c-131">Valore della proprietà promossa stessa.</span><span class="sxs-lookup"><span data-stu-id="1f42c-131">The value of the promoted property itself.</span></span> <span data-ttu-id="1f42c-132">In sql_variant possono rientrare la maggior parte dei tipi di dati primitivi SQL, eccetto stringhe e blob binari la cui lunghezza supera gli 8000 byte.</span><span class="sxs-lookup"><span data-stu-id="1f42c-132">Most SQL primitive data types except binary blobs and strings over 8000 bytes in length can fit in sql_variant.</span></span>|
|<span data-ttu-id="1f42c-133">Value33, Value34, Value35, …, Value64</span><span class="sxs-lookup"><span data-stu-id="1f42c-133">Value33, Value34, Value35, …, Value64</span></span>|<span data-ttu-id="1f42c-134">varbinary(max)</span><span class="sxs-lookup"><span data-stu-id="1f42c-134">varbinary(max)</span></span>|<span data-ttu-id="1f42c-135">Valore di proprietà promosse dichiarate in modo esplicito come varbinary (valore massimo).</span><span class="sxs-lookup"><span data-stu-id="1f42c-135">The value of promoted properties that are explicitly declared as varbinary(max).</span></span>|
