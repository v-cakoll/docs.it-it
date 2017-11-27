---
title: Creazione del servizio dati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 37d32d938f49d0767594e0f141d5a463ad5fc95f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="creating-the-data-service"></a><span data-ttu-id="c1144-102">Creazione del servizio dati</span><span class="sxs-lookup"><span data-stu-id="c1144-102">Creating the Data Service</span></span>
<span data-ttu-id="c1144-103">In questa attività si creerà un servizio dati di esempio che utilizza [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] per esporre un [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed basato sul database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="c1144-103">In this task, you will create a sample data service that uses [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] to expose an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed that is based on the Northwind sample database.</span></span> <span data-ttu-id="c1144-104">L'attività è costituita dai passaggi principali seguenti:</span><span class="sxs-lookup"><span data-stu-id="c1144-104">The task involves the following basic steps:</span></span>  
  
1.  <span data-ttu-id="c1144-105">Creazione di un'applicazione Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1144-105">Create an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application.</span></span>  
  
2.  <span data-ttu-id="c1144-106">Definizione del modello di dati tramite gli strumenti di [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1144-106">Define the data model by using the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] tools.</span></span>  
  
3.  <span data-ttu-id="c1144-107">Aggiunta del servizio dati all'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="c1144-107">Add the data service to the Web application.</span></span>  
  
4.  <span data-ttu-id="c1144-108">Abilitazione dell'accesso al servizio dati.</span><span class="sxs-lookup"><span data-stu-id="c1144-108">Enable access to the data service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1144-109">L'applicazione Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] creata al completamento di questa attività viene eseguita sul server di sviluppo di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] disponibile in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1144-109">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application that you create when you complete this task runs on the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server provided by [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="c1144-110">Il server di sviluppo di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] supporta solo l'accesso dal computer locale.</span><span class="sxs-lookup"><span data-stu-id="c1144-110">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server only supports access from the local computer.</span></span> <span data-ttu-id="c1144-111">Per semplificare inoltre il test del servizio dati e la risoluzione dei problemi relativi durante lo sviluppo, eseguire l'applicazione che ospita il servizio dati tramite Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="c1144-111">To also make it easier to test and troubleshoot the data service during development, consider running the application that hosts the data service by using Internet Information Services (IIS).</span></span> <span data-ttu-id="c1144-112">Per altre informazioni, vedere [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).</span><span class="sxs-lookup"><span data-stu-id="c1144-112">For more information, see [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).</span></span>  
  
### <a name="to-create-the-aspnet-web-application"></a><span data-ttu-id="c1144-113">Per creare l'applicazione Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c1144-113">To create the ASP.NET Web application</span></span>  
  
1.  <span data-ttu-id="c1144-114">In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]via il **File** dal menu **nuovo**, quindi selezionare **progetto**.</span><span class="sxs-lookup"><span data-stu-id="c1144-114">In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], on the **File** menu, select **New**, and then select **Project**.</span></span>  
  
2.  <span data-ttu-id="c1144-115">Nel **nuovo progetto** in presenza di una finestra di dialogo [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] selezionare il **Web** modello e quindi selezionare **applicazione Web ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="c1144-115">In the **New Project** dialog box, under either [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] select the **Web** template, and then select **ASP.NET Web Application**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c1144-116">Se si usa [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web Developer, sarà necessario creare un nuovo sito Web anziché una nuova applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="c1144-116">If you use [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web Developer, you must create a new Web site instead of a new Web application.</span></span>  
  
3.  <span data-ttu-id="c1144-117">Tipo `NorthwindService` come il nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="c1144-117">Type `NorthwindService` as the name of the project.</span></span>  
  
4.  <span data-ttu-id="c1144-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1144-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="c1144-119">(Opzione facoltativa) Specificare un numero specifico di porta per l'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="c1144-119">(Optional) Specify a specific port number for your Web application.</span></span> <span data-ttu-id="c1144-120">Nota: nella parte restante della guida rapida viene usato il numero di porta `12345`.</span><span class="sxs-lookup"><span data-stu-id="c1144-120">Note: the port number `12345` is used in the rest of the quickstart.</span></span>  
  
    1.  <span data-ttu-id="c1144-121">In **Esplora soluzioni**, il nome del mouse il [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] progetto appena creato e quindi fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c1144-121">In **Solution Explorer**, right-click the name of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project that you just created, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="c1144-122">Selezionare il **Web** scheda e impostare il valore della **porta specifica** casella di testo `12345`.</span><span class="sxs-lookup"><span data-stu-id="c1144-122">Select the **Web** tab, and set the value of the **Specific port** text box to `12345`.</span></span>  
  
### <a name="to-define-the-data-model"></a><span data-ttu-id="c1144-123">Per definire il modello di dati</span><span class="sxs-lookup"><span data-stu-id="c1144-123">To define the data model</span></span>  
  
1.  <span data-ttu-id="c1144-124">In **Esplora**, fare doppio clic sul nome del [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] del progetto e quindi fare clic su **Aggiungi nuovo elemento.**</span><span class="sxs-lookup"><span data-stu-id="c1144-124">In **Solution Explorer**, right-click the name of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item.**</span></span>  
  
2.  <span data-ttu-id="c1144-125">Nel **Aggiungi nuovo elemento** la finestra di dialogo, fare clic su di **dati** modello e quindi selezionare **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="c1144-125">In the **Add New Item** dialog box, click the **Data** template and then select **ADO.NET Entity Data Model**.</span></span>  
  
3.  <span data-ttu-id="c1144-126">Per il nome del modello di dati, digitare `Northwind.edmx`.</span><span class="sxs-lookup"><span data-stu-id="c1144-126">For the name of the data model, type `Northwind.edmx`.</span></span>  
  
4.  <span data-ttu-id="c1144-127">Nel [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] guidata, selezionare **genera da Database**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c1144-127">In the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] Wizard, select **Generate from Database**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="c1144-128">Connettere il modello di dati per il database eseguendo una delle operazioni seguenti e quindi fare clic su **Avanti**:</span><span class="sxs-lookup"><span data-stu-id="c1144-128">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>  
  
    -   <span data-ttu-id="c1144-129">Se non si dispone di una connessione al database già configurata, fare clic su **nuova connessione** e creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="c1144-129">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="c1144-130">Per ulteriori informazioni, vedere [procedura: creare connessioni ai database di SQL Server](http://go.microsoft.com/fwlink/?LinkId=123631).</span><span class="sxs-lookup"><span data-stu-id="c1144-130">For more information, see [How to: Create Connections to SQL Server Databases](http://go.microsoft.com/fwlink/?LinkId=123631).</span></span> <span data-ttu-id="c1144-131">A questa istanza di [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] deve essere collegato il database Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="c1144-131">This [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] instance must have the Northwind sample database attached.</span></span>  
  
         <span data-ttu-id="c1144-132">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="c1144-132">\- or -</span></span>  
  
    -   <span data-ttu-id="c1144-133">Se si dispone di una connessione al database già configurata per connettersi al database Northwind, selezionarla dall'elenco delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="c1144-133">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>  
  
6.  <span data-ttu-id="c1144-134">Nella pagina finale della procedura guidata, selezionare le caselle di controllo relative a tutte le tabelle nel database e deselezionare le caselle di controllo relative a visualizzazioni e stored procedure.</span><span class="sxs-lookup"><span data-stu-id="c1144-134">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>  
  
7.  <span data-ttu-id="c1144-135">Fare clic su **fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="c1144-135">Click **Finish** to close the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c1144-136">Questo modello di dati generato espone le proprietà della chiave esterna sui tipi di entità.</span><span class="sxs-lookup"><span data-stu-id="c1144-136">This generated data model exposes foreign key properties on entity types.</span></span> <span data-ttu-id="c1144-137">Poiché i modelli di dati creati usando [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 non includono tali proprietà,</span><span class="sxs-lookup"><span data-stu-id="c1144-137">Data models created using [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 do not include these foreign key properties.</span></span> <span data-ttu-id="c1144-138">è necessario aggiornare le classi del servizio dati client di qualsiasi applicazione client creata per accedere al servizio dati Northwind creato usando [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 prima di tentare di accedere alla versione corrente del servizio dati Northwind.</span><span class="sxs-lookup"><span data-stu-id="c1144-138">Because of this, you must update the client data service classes of any client applications that were created to access the Northwind data service that was created using [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 before attempting to access this version of the Northwind data service.</span></span>  
  
### <a name="to-create-the-data-service"></a><span data-ttu-id="c1144-139">Per creare il servizio dati</span><span class="sxs-lookup"><span data-stu-id="c1144-139">To create the data service</span></span>  
  
1.  <span data-ttu-id="c1144-140">In **Esplora**, fare doppio clic sul nome del [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] del progetto e quindi fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="c1144-140">In **Solution Explorer**, right-click the name of your [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="c1144-141">Nel **Aggiungi nuovo elemento** nella finestra di dialogo **servizio dati WCF**.</span><span class="sxs-lookup"><span data-stu-id="c1144-141">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>  
  
3.  <span data-ttu-id="c1144-142">Per il nome del servizio, digitare `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="c1144-142">For the name of the service, type `Northwind`.</span></span>  
  
     <span data-ttu-id="c1144-143">In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]Visual Studio verranno creati i file del markup XML e del codice per il nuovo servizio.</span><span class="sxs-lookup"><span data-stu-id="c1144-143">[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="c1144-144">Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="c1144-144">By default, the code-editor window opens.</span></span> <span data-ttu-id="c1144-145">In **Esplora**, il servizio risulterà denominato Northwind con estensione. svc.cs o. svc.</span><span class="sxs-lookup"><span data-stu-id="c1144-145">In **Solution Explorer**, the service will have the name, Northwind, with the extension .svc.cs or .svc.vb.</span></span>  
  
4.  <span data-ttu-id="c1144-146">Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo del contenitore di entità del modello di dati, che in questo caso corrisponde a `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="c1144-146">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="c1144-147">La definizione di classe dovrà essere analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="c1144-147">The class definition should look this the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
### <a name="to-enable-access-to-data-service-resources"></a><span data-ttu-id="c1144-148">Per abilitare l'accesso alle risorse del servizio dati</span><span class="sxs-lookup"><span data-stu-id="c1144-148">To enable access to data service resources</span></span>  
  
1.  <span data-ttu-id="c1144-149">Nel codice per il servizio dati sostituire il codice segnaposto nella funzione `InitializeService` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c1144-149">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     <span data-ttu-id="c1144-150">In questo modo i client autorizzati saranno in grado di accedere in lettura e scrittura alle risorse per i set di entità specificati.</span><span class="sxs-lookup"><span data-stu-id="c1144-150">This enables authorized clients to have read and write access to resources for the specified entity sets.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c1144-151">I client che possono accedere all'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] saranno inoltre in grado di accedere alle risorse esposte dal servizio dati.</span><span class="sxs-lookup"><span data-stu-id="c1144-151">Any client that can access the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="c1144-152">Per impedire l'accesso non autorizzato alle risorse in un servizio dati di produzione, è inoltre necessario proteggere l'applicazione stessa.</span><span class="sxs-lookup"><span data-stu-id="c1144-152">In a production data service, to prevent unauthorized access to resources you should also secure the application itself.</span></span> <span data-ttu-id="c1144-153">Per altre informazioni, vedere [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c1144-153">For more information, see [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c1144-154">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c1144-154">Next Steps</span></span>  
 <span data-ttu-id="c1144-155">Creato un nuovo servizio dati che espone un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed basato sul database di esempio Northwind ed è stato abilitato l'accesso al feed per i client che dispone delle autorizzazioni per il [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="c1144-155">You have successfully created a new data service that exposes an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed that is based on the Northwind sample database, and you have enabled access to the feed for clients that have permissions on the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application.</span></span> <span data-ttu-id="c1144-156">Successivamente, si avvia il servizio dati da [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] e si accederà il [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed inviando richieste GET HTTP attraverso un Web browser:</span><span class="sxs-lookup"><span data-stu-id="c1144-156">Next, you will start the data service from [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] and you will access the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by submitting HTTP GET requests through a Web browser:</span></span>  
  
 [<span data-ttu-id="c1144-157">Accesso al servizio da un Web Browser</span><span class="sxs-lookup"><span data-stu-id="c1144-157">Accessing the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a><span data-ttu-id="c1144-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1144-158">See Also</span></span>  
 [<span data-ttu-id="c1144-159">Strumenti di ADO.NET Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="c1144-159">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)
