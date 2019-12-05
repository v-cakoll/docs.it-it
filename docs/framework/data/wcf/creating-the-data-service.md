---
title: Creazione di un servizio dati WCF in Visual Studio
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: 72e3b35465968674a20aa48262d3425a2190ff74
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802273"
---
# <a name="create-the-data-service"></a><span data-ttu-id="8b58f-102">Creazione del servizio dati</span><span class="sxs-lookup"><span data-stu-id="8b58f-102">Create the data service</span></span>

<span data-ttu-id="8b58f-103">In questo argomento viene creato un servizio dati di esempio che usa WCF Data Services per esporre un feed di Open Data Protocol (OData) basato sul database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="8b58f-103">In this topic, you create a sample data service that uses WCF Data Services to expose an Open Data Protocol (OData) feed that's based on the Northwind sample database.</span></span> <span data-ttu-id="8b58f-104">L'attività è costituita dai passaggi principali seguenti:</span><span class="sxs-lookup"><span data-stu-id="8b58f-104">The task involves the following basic steps:</span></span>

1. <span data-ttu-id="8b58f-105">Creare un'applicazione Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="8b58f-105">Create an ASP.NET Web application.</span></span>

2. <span data-ttu-id="8b58f-106">Definizione del modello di dati tramite gli strumenti di Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="8b58f-106">Define the data model by using the Entity Data Model tools.</span></span>

3. <span data-ttu-id="8b58f-107">Aggiunta del servizio dati all'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="8b58f-107">Add the data service to the Web application.</span></span>

4. <span data-ttu-id="8b58f-108">Abilitazione dell'accesso al servizio dati.</span><span class="sxs-lookup"><span data-stu-id="8b58f-108">Enable access to the data service.</span></span>

## <a name="create-the-aspnet-web-app"></a><span data-ttu-id="8b58f-109">Creare l'app Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8b58f-109">Create the ASP.NET web app</span></span>

1. <span data-ttu-id="8b58f-110">Nel menu **File** in Visual Studio selezionare **Nuovo** > **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="8b58f-110">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

1. <span data-ttu-id="8b58f-111">Nella finestra di dialogo **nuovo progetto** , in Visual Basic o Visual C# selezionare la categoria **Web** , quindi selezionare **applicazione Web ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="8b58f-111">In the **New Project** dialog box, under either Visual Basic or Visual C# select the **Web** category, and then select **ASP.NET Web Application**.</span></span>

1. <span data-ttu-id="8b58f-112">Immettere `NorthwindService` come nome del progetto e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b58f-112">Enter `NorthwindService` as the name of the project and then select **OK**.</span></span>

1. <span data-ttu-id="8b58f-113">Nella finestra di dialogo **nuova applicazione Web ASP.NET** selezionare **vuoto** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b58f-113">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

1. <span data-ttu-id="8b58f-114">(Opzione facoltativa) Specificare un numero specifico di porta per l'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="8b58f-114">(Optional) Specify a specific port number for your Web application.</span></span> <span data-ttu-id="8b58f-115">Nota: il numero di porta `12345` viene usato in questa serie di argomenti della Guida introduttiva.</span><span class="sxs-lookup"><span data-stu-id="8b58f-115">Note: the port number `12345` is used in this series of quickstart topics.</span></span>

    1. <span data-ttu-id="8b58f-116">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto ASP.NET appena creato, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8b58f-116">In **Solution Explorer**, right-click on the ASP.NET project that you just created, and then choose **Properties**.</span></span>

    2. <span data-ttu-id="8b58f-117">Selezionare la scheda **Web** e impostare il valore della casella di testo **porta specifica** su `12345`.</span><span class="sxs-lookup"><span data-stu-id="8b58f-117">Select the **Web** tab, and set the value of the **Specific port** text box to `12345`.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="8b58f-118">Definizione del modello di dati</span><span class="sxs-lookup"><span data-stu-id="8b58f-118">Define the data model</span></span>

1. <span data-ttu-id="8b58f-119">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nome del progetto ASP.NET, quindi scegliere **Aggiungi** > **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="8b58f-119">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="8b58f-120">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare la categoria di **dati** , quindi selezionare **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="8b58f-120">In the **Add New Item** dialog box, select the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="8b58f-121">Per il nome del modello di dati, immettere `Northwind.edmx`.</span><span class="sxs-lookup"><span data-stu-id="8b58f-121">For the name of the data model, enter `Northwind.edmx`.</span></span>

4. <span data-ttu-id="8b58f-122">Nella **procedura guidata di Entity Data Model**selezionare **EF Designer from database**e quindi fare clic su **Next**.</span><span class="sxs-lookup"><span data-stu-id="8b58f-122">In the **Entity Data Model Wizard**, select **EF Designer from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="8b58f-123">Connettere il modello di dati al database effettuando una delle operazioni seguenti, quindi fare clic su **Avanti**:</span><span class="sxs-lookup"><span data-stu-id="8b58f-123">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    - <span data-ttu-id="8b58f-124">Se non è già stata configurata una connessione di database, fare clic su **nuova connessione** e creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="8b58f-124">If you don't have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="8b58f-125">Per altre informazioni, vedere [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="8b58f-125">For more information, see [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="8b58f-126">A questa istanza di SQL Server deve essere collegato il database Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="8b58f-126">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="8b58f-127">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="8b58f-127">\- or -</span></span>

    - <span data-ttu-id="8b58f-128">Se si dispone di una connessione al database già configurata per connettersi al database Northwind, selezionarla dall'elenco delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="8b58f-128">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="8b58f-129">Nella pagina finale della procedura guidata, selezionare le caselle di controllo relative a tutte le tabelle nel database e deselezionare le caselle di controllo relative a visualizzazioni e stored procedure.</span><span class="sxs-lookup"><span data-stu-id="8b58f-129">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="8b58f-130">Fare clic su **Fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="8b58f-130">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-wcf-data-service"></a><span data-ttu-id="8b58f-131">Creare il servizio dati WCF</span><span class="sxs-lookup"><span data-stu-id="8b58f-131">Create the WCF data service</span></span>

1. <span data-ttu-id="8b58f-132">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto ASP.NET, quindi scegliere **Aggiungi** > **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="8b58f-132">In **Solution Explorer**, right-click on the ASP.NET project, and then choose **Add** > **New Item**.</span></span>

2. <span data-ttu-id="8b58f-133">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare il modello di elemento **servizio dati WCF** dalla categoria **Web** .</span><span class="sxs-lookup"><span data-stu-id="8b58f-133">In the **Add New Item** dialog box, select the **WCF Data Service** item template from the **Web** category.</span></span>

   ![Modello di elemento del servizio dati WCF in Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="8b58f-135">Il modello di **servizio dati WCF** è disponibile in visual studio 2015, ma non in visual studio 2017 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="8b58f-135">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

3. <span data-ttu-id="8b58f-136">Per il nome del servizio, digitare `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="8b58f-136">For the name of the service, type `Northwind`.</span></span>

     <span data-ttu-id="8b58f-137">In Visual Studio verranno creati i file del markup XML e del codice per il nuovo servizio.</span><span class="sxs-lookup"><span data-stu-id="8b58f-137">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="8b58f-138">Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="8b58f-138">By default, the code-editor window opens.</span></span> <span data-ttu-id="8b58f-139">In **Esplora soluzioni**il nome del servizio è Northwind con estensione *svc.cs* o *svc. vb*.</span><span class="sxs-lookup"><span data-stu-id="8b58f-139">In **Solution Explorer**, the service has the name Northwind with the extension *.svc.cs* or *.svc.vb*.</span></span>

4. <span data-ttu-id="8b58f-140">Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo del contenitore di entità del modello di dati, che in questo caso corrisponde a `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="8b58f-140">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="8b58f-141">La definizione di classe dovrà essere analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="8b58f-141">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a><span data-ttu-id="8b58f-142">Abilitare l'accesso alle risorse del servizio dati</span><span class="sxs-lookup"><span data-stu-id="8b58f-142">Enable access to data service resources</span></span>

1. <span data-ttu-id="8b58f-143">Nel codice per il servizio dati sostituire il codice segnaposto nella funzione `InitializeService` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8b58f-143">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]

     <span data-ttu-id="8b58f-144">In questo modo i client autorizzati saranno in grado di accedere in lettura e scrittura alle risorse per i set di entità specificati.</span><span class="sxs-lookup"><span data-stu-id="8b58f-144">This enables authorized clients to have read and write access to resources for the specified entity sets.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8b58f-145">I client che possono accedere all'applicazione ASP.NET saranno inoltre in grado di accedere alle risorse esposte dal servizio dati.</span><span class="sxs-lookup"><span data-stu-id="8b58f-145">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="8b58f-146">Per impedire l'accesso non autorizzato alle risorse in un servizio dati di produzione, è inoltre necessario proteggere l'applicazione stessa.</span><span class="sxs-lookup"><span data-stu-id="8b58f-146">In a production data service, to prevent unauthorized access to resources you should also secure the application itself.</span></span> <span data-ttu-id="8b58f-147">Per altre informazioni, vedere [Securing WCF Data Services](securing-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8b58f-147">For more information, see [Securing WCF Data Services](securing-wcf-data-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8b58f-148">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8b58f-148">Next steps</span></span>

<span data-ttu-id="8b58f-149">È stato creato un nuovo servizio dati che espone un feed OData basato sul database di esempio Northwind ed è stato abilitato l'accesso al feed per i client che dispongono delle autorizzazioni per l'applicazione Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="8b58f-149">You have successfully created a new data service that exposes an OData feed that is based on the Northwind sample database, and you have enabled access to the feed for clients that have permissions on the ASP.NET Web application.</span></span> <span data-ttu-id="8b58f-150">Successivamente, si avvierà il servizio dati da Visual Studio e si accede al feed OData inviando richieste HTTP GET tramite un Web browser:</span><span class="sxs-lookup"><span data-stu-id="8b58f-150">Next, you'll start the data service from Visual Studio and access the OData feed by submitting HTTP GET requests through a Web browser:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8b58f-151">Accedere al servizio da un Web browser</span><span class="sxs-lookup"><span data-stu-id="8b58f-151">Access the service from a web browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="8b58f-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b58f-152">See also</span></span>

- <span data-ttu-id="8b58f-153">[Strumenti Entity Data Model ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8b58f-153">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
