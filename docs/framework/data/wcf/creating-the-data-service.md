---
title: Creare un servizio dati WCF in Visual Studio
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: 361582866dabf51665e1dc94fdc49e8710d8ad3e
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2019
ms.locfileid: "56091825"
---
# <a name="create-the-data-service"></a><span data-ttu-id="2d04d-102">Creazione del servizio dati</span><span class="sxs-lookup"><span data-stu-id="2d04d-102">Create the data service</span></span>

<span data-ttu-id="2d04d-103">In questo argomento, si crea un servizio dati di esempio che utilizza WCF Data Services per esporre un [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed basato sul database Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="2d04d-103">In this topic, you create a sample data service that uses WCF Data Services to expose an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed that's based on the Northwind sample database.</span></span> <span data-ttu-id="2d04d-104">L'attività è costituita dai passaggi principali seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d04d-104">The task involves the following basic steps:</span></span>

1. <span data-ttu-id="2d04d-105">Creare un'applicazione Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="2d04d-105">Create an ASP.NET Web application.</span></span>

2. <span data-ttu-id="2d04d-106">Definizione del modello di dati tramite gli strumenti di Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="2d04d-106">Define the data model by using the Entity Data Model tools.</span></span>

3. <span data-ttu-id="2d04d-107">Aggiunta del servizio dati all'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="2d04d-107">Add the data service to the Web application.</span></span>

4. <span data-ttu-id="2d04d-108">Abilitazione dell'accesso al servizio dati.</span><span class="sxs-lookup"><span data-stu-id="2d04d-108">Enable access to the data service.</span></span>

## <a name="create-the-aspnet-web-app"></a><span data-ttu-id="2d04d-109">Creare l'app web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2d04d-109">Create the ASP.NET web app</span></span>

1. <span data-ttu-id="2d04d-110">In Visual Studio sul **File** dal menu **New** > **progetto**.</span><span class="sxs-lookup"><span data-stu-id="2d04d-110">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

1. <span data-ttu-id="2d04d-111">Nel **nuovo progetto** della finestra di dialogo in Visual Basic o Visual c#, selezionare la **Web** categoria e quindi selezionare **applicazione Web ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="2d04d-111">In the **New Project** dialog box, under either Visual Basic or Visual C# select the **Web** category, and then select **ASP.NET Web Application**.</span></span>

1. <span data-ttu-id="2d04d-112">Immettere `NorthwindService` come nome del progetto e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d04d-112">Enter `NorthwindService` as the name of the project and then select **OK**.</span></span>

1. <span data-ttu-id="2d04d-113">Nel **nuova applicazione Web ASP.NET** finestra di dialogo, seleziona **vuota** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d04d-113">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

1. <span data-ttu-id="2d04d-114">(Opzione facoltativa) Specificare un numero specifico di porta per l'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="2d04d-114">(Optional) Specify a specific port number for your Web application.</span></span> <span data-ttu-id="2d04d-115">Nota: il numero della porta `12345` viene usato in questa serie di argomenti della Guida rapida.</span><span class="sxs-lookup"><span data-stu-id="2d04d-115">Note: the port number `12345` is used in this series of quickstart topics.</span></span>

    1. <span data-ttu-id="2d04d-116">Nelle **Esplora soluzioni**destro del mouse sul progetto ASP.NET appena creato e quindi scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="2d04d-116">In **Solution Explorer**, right-click on the ASP.NET project that you just created, and then choose **Properties**.</span></span>

    2. <span data-ttu-id="2d04d-117">Selezionare il **Web** scheda e impostare il valore della **porta specifica** casella di testo `12345`.</span><span class="sxs-lookup"><span data-stu-id="2d04d-117">Select the **Web** tab, and set the value of the **Specific port** text box to `12345`.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="2d04d-118">Definizione del modello di dati</span><span class="sxs-lookup"><span data-stu-id="2d04d-118">Define the data model</span></span>

1. <span data-ttu-id="2d04d-119">Nelle **Esplora soluzioni**, fare doppio clic il nome del progetto ASP.NET e quindi fare clic su **Add** > **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2d04d-119">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="2d04d-120">Nel **Aggiungi nuovo elemento** finestra di dialogo, seleziona la **Data** categoria e quindi selezionare **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="2d04d-120">In the **Add New Item** dialog box, select the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="2d04d-121">Immettere il nome del modello di dati, `Northwind.edmx`.</span><span class="sxs-lookup"><span data-stu-id="2d04d-121">For the name of the data model, enter `Northwind.edmx`.</span></span>

4. <span data-ttu-id="2d04d-122">Nel **procedura guidata Entity Data Model**, selezionare **Entity Framework Designer da Database**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2d04d-122">In the **Entity Data Model Wizard**, select **EF Designer from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="2d04d-123">Connettere il modello di dati al database effettuando una delle operazioni seguenti e quindi fare clic su **successivo**:</span><span class="sxs-lookup"><span data-stu-id="2d04d-123">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    -   <span data-ttu-id="2d04d-124">Se non si dispone di una connessione al database già configurata, fare clic su **nuova connessione** e creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="2d04d-124">If you don't have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="2d04d-125">Per altre informazioni, vedere [Procedura: Creare connessioni a database di SQL Server](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="2d04d-125">For more information, see [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="2d04d-126">A questa istanza di SQL Server deve essere collegato il database Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="2d04d-126">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="2d04d-127">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="2d04d-127">\- or -</span></span>

    -   <span data-ttu-id="2d04d-128">Se si dispone di una connessione al database già configurata per connettersi al database Northwind, selezionarla dall'elenco delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="2d04d-128">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="2d04d-129">Nella pagina finale della procedura guidata, selezionare le caselle di controllo relative a tutte le tabelle nel database e deselezionare le caselle di controllo relative a visualizzazioni e stored procedure.</span><span class="sxs-lookup"><span data-stu-id="2d04d-129">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="2d04d-130">Fare clic su **fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="2d04d-130">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-wcf-data-service"></a><span data-ttu-id="2d04d-131">Creare il servizio dati WCF</span><span class="sxs-lookup"><span data-stu-id="2d04d-131">Create the WCF data service</span></span>

1. <span data-ttu-id="2d04d-132">Nelle **Esplora soluzioni**destro del mouse sul progetto ASP.NET e quindi scegliere **Add** > **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2d04d-132">In **Solution Explorer**, right-click on the ASP.NET project, and then choose **Add** > **New Item**.</span></span>

2. <span data-ttu-id="2d04d-133">Nel **Aggiungi nuovo elemento** finestra di dialogo, seleziona la **WCF Data Services** modello di elemento dal **Web** categoria.</span><span class="sxs-lookup"><span data-stu-id="2d04d-133">In the **Add New Item** dialog box, select the **WCF Data Service** item template from the **Web** category.</span></span>

   ![Modello di elemento di WCF Data Services in Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="2d04d-135">Il **di WCF Data Services** modello è disponibile in Visual Studio 2015, ma non in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="2d04d-135">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

3. <span data-ttu-id="2d04d-136">Per il nome del servizio, digitare `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="2d04d-136">For the name of the service, type `Northwind`.</span></span>

     <span data-ttu-id="2d04d-137">In Visual Studio verranno creati i file del markup XML e del codice per il nuovo servizio.</span><span class="sxs-lookup"><span data-stu-id="2d04d-137">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="2d04d-138">Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="2d04d-138">By default, the code-editor window opens.</span></span> <span data-ttu-id="2d04d-139">Nelle **Esplora soluzioni**, il servizio ha il denominato Northwind con estensione *. svc.cs* oppure *. svc*.</span><span class="sxs-lookup"><span data-stu-id="2d04d-139">In **Solution Explorer**, the service has the name Northwind with the extension *.svc.cs* or *.svc.vb*.</span></span>

4. <span data-ttu-id="2d04d-140">Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo del contenitore di entità del modello di dati, che in questo caso corrisponde a `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="2d04d-140">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="2d04d-141">La definizione di classe dovrà essere analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="2d04d-141">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a><span data-ttu-id="2d04d-142">Abilitare l'accesso alle risorse del servizio dati</span><span class="sxs-lookup"><span data-stu-id="2d04d-142">Enable access to data service resources</span></span>

1. <span data-ttu-id="2d04d-143">Nel codice per il servizio dati sostituire il codice segnaposto nella funzione `InitializeService` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2d04d-143">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]

     <span data-ttu-id="2d04d-144">In questo modo i client autorizzati saranno in grado di accedere in lettura e scrittura alle risorse per i set di entità specificati.</span><span class="sxs-lookup"><span data-stu-id="2d04d-144">This enables authorized clients to have read and write access to resources for the specified entity sets.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2d04d-145">I client che possono accedere all'applicazione ASP.NET saranno inoltre in grado di accedere alle risorse esposte dal servizio dati.</span><span class="sxs-lookup"><span data-stu-id="2d04d-145">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="2d04d-146">Per impedire l'accesso non autorizzato alle risorse in un servizio dati di produzione, è inoltre necessario proteggere l'applicazione stessa.</span><span class="sxs-lookup"><span data-stu-id="2d04d-146">In a production data service, to prevent unauthorized access to resources you should also secure the application itself.</span></span> <span data-ttu-id="2d04d-147">Per altre informazioni, vedere [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2d04d-147">For more information, see [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2d04d-148">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="2d04d-148">Next steps</span></span>

<span data-ttu-id="2d04d-149">Avere creato un nuovo servizio dati che espone un feed OData che è basato sul database di esempio Northwind ed è stato abilitato l'accesso al feed per i client che dispone delle autorizzazioni per l'applicazione Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="2d04d-149">You have successfully created a new data service that exposes an OData feed that is based on the Northwind sample database, and you have enabled access to the feed for clients that have permissions on the ASP.NET Web application.</span></span> <span data-ttu-id="2d04d-150">Quindi verrà avviare il servizio dati da Visual Studio e accedere ai feed inviando richieste GET HTTP attraverso un browser Web OData:</span><span class="sxs-lookup"><span data-stu-id="2d04d-150">Next, you'll start the data service from Visual Studio and access the OData feed by submitting HTTP GET requests through a Web browser:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="2d04d-151">Accedere al servizio da un web browser</span><span class="sxs-lookup"><span data-stu-id="2d04d-151">Access the service from a web browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="2d04d-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d04d-152">See also</span></span>

- <span data-ttu-id="2d04d-153">[Strumenti di ADO.NET Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2d04d-153">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>