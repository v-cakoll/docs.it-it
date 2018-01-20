---
title: 'Procedura: creare un servizio dati tramite un''origine dati ADO.NET Entity Framework (WCF Data Services)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e90b11800685707460171e5e2d250ef757979c44
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a><span data-ttu-id="cf613-102">Procedura: creare un servizio dati tramite un'origine dati ADO.NET Entity Framework (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="cf613-102">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="cf613-103"> espone i dati di entità come servizio dati.</span><span class="sxs-lookup"><span data-stu-id="cf613-103"> exposes entity data as a data service.</span></span> <span data-ttu-id="cf613-104">Questi dati di entità viene eseguiti il [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] quando l'origine dati è un database relazionale.</span><span class="sxs-lookup"><span data-stu-id="cf613-104">This entity data is provided by the [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)][!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] when the data source is a relational database.</span></span> <span data-ttu-id="cf613-105">In questo argomento viene illustrato come creare un modello di dati basato su [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] in un'applicazione Web [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] in base a un database esistente e come usarlo per creare un nuovo servizio dati.</span><span class="sxs-lookup"><span data-stu-id="cf613-105">This topic shows you how to create an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-based data model in a [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web application that is based on an existing database and use this data model to create a new data service.</span></span>  
  
 <span data-ttu-id="cf613-106">In [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] è disponibile inoltre uno strumento da riga di comando che può generare un modello di [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] all'esterno di un progetto [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf613-106">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] also provides a command line tool that can generate an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] model outside of a [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] project.</span></span> <span data-ttu-id="cf613-107">Per ulteriori informazioni, vedere [procedura: utilizzare EdmGen.exe per generare il modello e i file di Mapping](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="cf613-107">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
### <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a><span data-ttu-id="cf613-108">Per aggiungere un modello di Entity Framework basato su un database esistente a un'applicazione Web esistente</span><span class="sxs-lookup"><span data-stu-id="cf613-108">To add an Entity Framework model that is based on an existing database to an existing Web application</span></span>  
  
1.  <span data-ttu-id="cf613-109">Nel **progetto** menu, fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="cf613-109">On the **Project** menu, click **Add new item**.</span></span>  
  
2.  <span data-ttu-id="cf613-110">Nel **modelli** riquadro, fare clic su di **dati** categoria e quindi selezionare **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="cf613-110">In the **Templates** pane, click the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>  
  
3.  <span data-ttu-id="cf613-111">Digitare il nome del modello e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cf613-111">Type the model name and then click **Add**.</span></span>  
  
     <span data-ttu-id="cf613-112">Verrà visualizzata la prima pagina della Procedura guidata [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf613-112">The first page of the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] Wizard is displayed.</span></span>  
  
4.  <span data-ttu-id="cf613-113">Nel **Scegli contenuto Model** nella finestra di dialogo **genera da database**.</span><span class="sxs-lookup"><span data-stu-id="cf613-113">In the **Choose Model Contents** dialog box, select **Generate from database**.</span></span> <span data-ttu-id="cf613-114">Scegliere quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf613-114">Then click **Next**.</span></span>  
  
5.  <span data-ttu-id="cf613-115">Fare clic su di **nuova connessione** pulsante.</span><span class="sxs-lookup"><span data-stu-id="cf613-115">Click the **New Connection** button.</span></span>  
  
6.  <span data-ttu-id="cf613-116">Nel **le proprietà di connessione** nella finestra di dialogo digitare il nome del server, selezionare il metodo di autenticazione, digitare il nome del database e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf613-116">In the **Connection Properties** dialog box, type your server name, select the authentication method, type the database name, and then click **OK**.</span></span>  
  
     <span data-ttu-id="cf613-117">Il **Seleziona connessione dati**nella finestra di dialogo viene aggiornata con le impostazioni di connessione di database.</span><span class="sxs-lookup"><span data-stu-id="cf613-117">The **Choose Your Data Connection**s dialog box is updated with your database connection settings.</span></span>  
  
7.  <span data-ttu-id="cf613-118">Verificare che il **Salva entità di impostazioni di connessione in App. config come:** casella di controllo è selezionata.</span><span class="sxs-lookup"><span data-stu-id="cf613-118">Ensure that the **Save entity connection settings in App.Config as:** checkbox is checked.</span></span> <span data-ttu-id="cf613-119">Scegliere quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cf613-119">Then click **Next**.</span></span>  
  
8.  <span data-ttu-id="cf613-120">Nel **Seleziona oggetti di Database** la finestra di dialogo, selezionare tutti i database di oggetti che si intende esporre nel servizio dati.</span><span class="sxs-lookup"><span data-stu-id="cf613-120">In the **Choose Your Database Objects** dialog box, select all of database objects that you plan to expose in the data service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cf613-121">Gli oggetti inclusi nel modello di dati non vengono esposti automaticamente dal servizio dati.</span><span class="sxs-lookup"><span data-stu-id="cf613-121">Objects included in the data model are not automatically exposed by the data service.</span></span> <span data-ttu-id="cf613-122">Devono essere esposti in modo esplicito mediante il servizio stesso.</span><span class="sxs-lookup"><span data-stu-id="cf613-122">They must be explicitly exposed by the service itself.</span></span> <span data-ttu-id="cf613-123">Per ulteriori informazioni, vedere [configurazione del servizio dati](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="cf613-123">For more information, see [Configuring the Data Service](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span></span>  
  
9. <span data-ttu-id="cf613-124">Fare clic su **fine** per completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="cf613-124">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="cf613-125">Verrà creato un modello di dati predefinito in base al database specifico.</span><span class="sxs-lookup"><span data-stu-id="cf613-125">This creates a default data model based on the specific database.</span></span> <span data-ttu-id="cf613-126">[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] consente di personalizzare il modello di dati.</span><span class="sxs-lookup"><span data-stu-id="cf613-126">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] enables to customize the data model.</span></span> <span data-ttu-id="cf613-127">Per altre informazioni, vedere [Tasks](http://msdn.microsoft.com/library/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb) (Attività).</span><span class="sxs-lookup"><span data-stu-id="cf613-127">For more information, see [Tasks](http://msdn.microsoft.com/library/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).</span></span>  
  
### <a name="to-create-the-data-service-by-using-the-new-data-model"></a><span data-ttu-id="cf613-128">Per creare il servizio dati usando il nuovo modello di dati</span><span class="sxs-lookup"><span data-stu-id="cf613-128">To create the data service by using the new data model</span></span>  
  
1.  <span data-ttu-id="cf613-129">In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] aprire il file con estensione edmx che rappresenta il modello di dati.</span><span class="sxs-lookup"><span data-stu-id="cf613-129">In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], open the .edmx file that represents the data model.</span></span>  
  
2.  <span data-ttu-id="cf613-130">Nel **Browser modello**, il modello di pulsante destro del mouse, fare clic su **proprietà**e prendere nota del nome del contenitore di entità.</span><span class="sxs-lookup"><span data-stu-id="cf613-130">In the **Model Browser**, right-click the model, click **Properties**, and then note the name of the entity container.</span></span>  
  
3.  <span data-ttu-id="cf613-131">In **Esplora**, fare doppio clic sul nome del [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] del progetto e quindi fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="cf613-131">In **Solution Explorer**, right-click the name of your [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item**.</span></span>  
  
4.  <span data-ttu-id="cf613-132">Nel **Aggiungi nuovo elemento** nella finestra di dialogo **servizio dati WCF**.</span><span class="sxs-lookup"><span data-stu-id="cf613-132">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>  
  
5.  <span data-ttu-id="cf613-133">Specificare un nome per il servizio e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf613-133">Supply a name for the service, and then click **OK**.</span></span>  
  
     <span data-ttu-id="cf613-134">In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] verranno creati i file del markup XML e del codice per il nuovo servizio.</span><span class="sxs-lookup"><span data-stu-id="cf613-134">[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="cf613-135">Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="cf613-135">By default, the code-editor window opens.</span></span>  
  
6.  <span data-ttu-id="cf613-136">Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo che eredita dalla classe <xref:System.Data.Objects.ObjectContext> e che rappresenta il contenitore di entità del modello di dati annotato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="cf613-136">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that inherits from the <xref:System.Data.Objects.ObjectContext> class and that is the entity container of the data model, which was noted in step 2.</span></span>  
  
7.  <span data-ttu-id="cf613-137">Nel codice per il servizio dati consentire ai client autorizzati di accedere ai set di entità esposti dal servizio dati.</span><span class="sxs-lookup"><span data-stu-id="cf613-137">In the code for the data service, enable authorized clients to access the entity sets that the data service exposes.</span></span> <span data-ttu-id="cf613-138">Per ulteriori informazioni, vedere [creazione del servizio dati](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="cf613-138">For more information, see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
8.  <span data-ttu-id="cf613-139">Per testare il servizio dati Northwind. svc tramite un Web browser, seguire le istruzioni nell'argomento [accesso al servizio da un Browser Web](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="cf613-139">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf613-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf613-140">See Also</span></span>  
 [<span data-ttu-id="cf613-141">Definizione di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="cf613-141">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [<span data-ttu-id="cf613-142">Provider di servizi dati</span><span class="sxs-lookup"><span data-stu-id="cf613-142">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [<span data-ttu-id="cf613-143">Procedura: creare un servizio dati tramite il provider di reflection</span><span class="sxs-lookup"><span data-stu-id="cf613-143">How to: Create a Data Service Using the Reflection Provider</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [<span data-ttu-id="cf613-144">Procedura: creare un servizio dati tramite un'origine dati LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="cf613-144">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)
