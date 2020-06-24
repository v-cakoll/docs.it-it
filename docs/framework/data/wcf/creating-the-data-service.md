---
title: Creazione di un servizio dati WCF in Visual Studio
description: Informazioni su come creare un servizio dati di esempio che usa WCF Data Services per esporre un feed OData in base a un database di esempio.
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: 739cb6971209792724a2e939ca4f4821d5879c8c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247791"
---
# <a name="create-the-data-service"></a><span data-ttu-id="1c445-103">Creazione del servizio dati</span><span class="sxs-lookup"><span data-stu-id="1c445-103">Create the data service</span></span>

<span data-ttu-id="1c445-104">In questo argomento viene creato un servizio dati di esempio che usa WCF Data Services per esporre un feed di Open Data Protocol (OData) basato sul database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="1c445-104">In this topic, you create a sample data service that uses WCF Data Services to expose an Open Data Protocol (OData) feed that's based on the Northwind sample database.</span></span> <span data-ttu-id="1c445-105">L'attività è costituita dai passaggi principali seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c445-105">The task involves the following basic steps:</span></span>

1. <span data-ttu-id="1c445-106">Creare un'applicazione Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1c445-106">Create an ASP.NET Web application.</span></span>

2. <span data-ttu-id="1c445-107">Definizione del modello di dati tramite gli strumenti di Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="1c445-107">Define the data model by using the Entity Data Model tools.</span></span>

3. <span data-ttu-id="1c445-108">Aggiunta del servizio dati all'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="1c445-108">Add the data service to the Web application.</span></span>

4. <span data-ttu-id="1c445-109">Abilitazione dell'accesso al servizio dati.</span><span class="sxs-lookup"><span data-stu-id="1c445-109">Enable access to the data service.</span></span>

## <a name="create-the-aspnet-web-app"></a><span data-ttu-id="1c445-110">Creare l'app Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1c445-110">Create the ASP.NET web app</span></span>

1. <span data-ttu-id="1c445-111">Nel menu **File** in Visual Studio selezionare **Nuovo** > **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="1c445-111">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

1. <span data-ttu-id="1c445-112">Nella finestra di dialogo **nuovo progetto** , in Visual Basic o Visual C# selezionare la categoria **Web** e quindi selezionare **applicazione Web ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="1c445-112">In the **New Project** dialog box, under either Visual Basic or Visual C# select the **Web** category, and then select **ASP.NET Web Application**.</span></span>

1. <span data-ttu-id="1c445-113">Immettere `NorthwindService` come nome del progetto e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c445-113">Enter `NorthwindService` as the name of the project and then select **OK**.</span></span>

1. <span data-ttu-id="1c445-114">Nella finestra di dialogo **nuova applicazione Web ASP.NET** selezionare **vuoto** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c445-114">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

1. <span data-ttu-id="1c445-115">(Opzione facoltativa) Specificare un numero specifico di porta per l'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="1c445-115">(Optional) Specify a specific port number for your Web application.</span></span> <span data-ttu-id="1c445-116">Nota: `12345` in questa serie di argomenti della Guida introduttiva viene usato il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="1c445-116">Note: the port number `12345` is used in this series of quickstart topics.</span></span>

    1. <span data-ttu-id="1c445-117">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto ASP.NET appena creato, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1c445-117">In **Solution Explorer**, right-click on the ASP.NET project that you just created, and then choose **Properties**.</span></span>

    2. <span data-ttu-id="1c445-118">Selezionare la scheda **Web** e impostare il valore della casella di testo **porta specifica** su `12345` .</span><span class="sxs-lookup"><span data-stu-id="1c445-118">Select the **Web** tab, and set the value of the **Specific port** text box to `12345`.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="1c445-119">Definizione del modello di dati</span><span class="sxs-lookup"><span data-stu-id="1c445-119">Define the data model</span></span>

1. <span data-ttu-id="1c445-120">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nome del progetto ASP.NET, quindi scegliere **Aggiungi**  >  **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="1c445-120">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="1c445-121">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare la categoria di **dati** , quindi selezionare **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="1c445-121">In the **Add New Item** dialog box, select the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="1c445-122">Per il nome del modello di dati, immettere `Northwind.edmx` .</span><span class="sxs-lookup"><span data-stu-id="1c445-122">For the name of the data model, enter `Northwind.edmx`.</span></span>

4. <span data-ttu-id="1c445-123">Nella **procedura guidata di Entity Data Model**selezionare **EF Designer from database**e quindi fare clic su **Next**.</span><span class="sxs-lookup"><span data-stu-id="1c445-123">In the **Entity Data Model Wizard**, select **EF Designer from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="1c445-124">Connettere il modello di dati al database effettuando una delle operazioni seguenti, quindi fare clic su **Avanti**:</span><span class="sxs-lookup"><span data-stu-id="1c445-124">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    - <span data-ttu-id="1c445-125">Se non è già stata configurata una connessione di database, fare clic su **nuova connessione** e creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="1c445-125">If you don't have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="1c445-126">Per altre informazioni, vedere [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="1c445-126">For more information, see [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="1c445-127">A questa istanza di SQL Server deve essere collegato il database Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="1c445-127">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="1c445-128">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="1c445-128">\- or -</span></span>

    - <span data-ttu-id="1c445-129">Se si dispone di una connessione al database già configurata per connettersi al database Northwind, selezionarla dall'elenco delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="1c445-129">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="1c445-130">Nella pagina finale della procedura guidata, selezionare le caselle di controllo relative a tutte le tabelle nel database e deselezionare le caselle di controllo relative a visualizzazioni e stored procedure.</span><span class="sxs-lookup"><span data-stu-id="1c445-130">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="1c445-131">Fare clic su **Fine** per chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1c445-131">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-wcf-data-service"></a><span data-ttu-id="1c445-132">Creare il servizio dati WCF</span><span class="sxs-lookup"><span data-stu-id="1c445-132">Create the WCF data service</span></span>

1. <span data-ttu-id="1c445-133">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto ASP.NET, quindi scegliere **Aggiungi**  >  **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="1c445-133">In **Solution Explorer**, right-click on the ASP.NET project, and then choose **Add** > **New Item**.</span></span>

2. <span data-ttu-id="1c445-134">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare il modello di elemento **servizio dati WCF** dalla categoria **Web** .</span><span class="sxs-lookup"><span data-stu-id="1c445-134">In the **Add New Item** dialog box, select the **WCF Data Service** item template from the **Web** category.</span></span>

   ![Modello di elemento del servizio dati WCF in Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="1c445-136">Il modello di **servizio dati WCF** è disponibile in visual studio 2015, ma non in visual studio 2017 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="1c445-136">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

3. <span data-ttu-id="1c445-137">Per il nome del servizio, digitare `Northwind` .</span><span class="sxs-lookup"><span data-stu-id="1c445-137">For the name of the service, type `Northwind`.</span></span>

     <span data-ttu-id="1c445-138">In Visual Studio verranno creati i file del markup XML e del codice per il nuovo servizio.</span><span class="sxs-lookup"><span data-stu-id="1c445-138">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="1c445-139">Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="1c445-139">By default, the code-editor window opens.</span></span> <span data-ttu-id="1c445-140">In **Esplora soluzioni**il nome del servizio è Northwind con estensione *svc.cs* o *svc. vb*.</span><span class="sxs-lookup"><span data-stu-id="1c445-140">In **Solution Explorer**, the service has the name Northwind with the extension *.svc.cs* or *.svc.vb*.</span></span>

4. <span data-ttu-id="1c445-141">Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo del contenitore di entità del modello di dati, che in questo caso corrisponde a `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="1c445-141">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="1c445-142">La definizione di classe dovrà essere analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="1c445-142">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a><span data-ttu-id="1c445-143">Abilitare l'accesso alle risorse del servizio dati</span><span class="sxs-lookup"><span data-stu-id="1c445-143">Enable access to data service resources</span></span>

1. <span data-ttu-id="1c445-144">Nel codice per il servizio dati sostituire il codice segnaposto nella funzione `InitializeService` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="1c445-144">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]

     <span data-ttu-id="1c445-145">In questo modo i client autorizzati saranno in grado di accedere in lettura e scrittura alle risorse per i set di entità specificati.</span><span class="sxs-lookup"><span data-stu-id="1c445-145">This enables authorized clients to have read and write access to resources for the specified entity sets.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1c445-146">I client che possono accedere all'applicazione ASP.NET saranno inoltre in grado di accedere alle risorse esposte dal servizio dati.</span><span class="sxs-lookup"><span data-stu-id="1c445-146">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="1c445-147">Per impedire l'accesso non autorizzato alle risorse in un servizio dati di produzione, è inoltre necessario proteggere l'applicazione stessa.</span><span class="sxs-lookup"><span data-stu-id="1c445-147">In a production data service, to prevent unauthorized access to resources you should also secure the application itself.</span></span> <span data-ttu-id="1c445-148">Per altre informazioni, vedere [Securing WCF Data Services](securing-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1c445-148">For more information, see [Securing WCF Data Services](securing-wcf-data-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1c445-149">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="1c445-149">Next steps</span></span>

<span data-ttu-id="1c445-150">È stato creato un nuovo servizio dati che espone un feed OData basato sul database di esempio Northwind ed è stato abilitato l'accesso al feed per i client che dispongono delle autorizzazioni per l'applicazione Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1c445-150">You have successfully created a new data service that exposes an OData feed that is based on the Northwind sample database, and you have enabled access to the feed for clients that have permissions on the ASP.NET Web application.</span></span> <span data-ttu-id="1c445-151">Successivamente, si avvierà il servizio dati da Visual Studio e si accede al feed OData inviando richieste HTTP GET tramite un Web browser:</span><span class="sxs-lookup"><span data-stu-id="1c445-151">Next, you'll start the data service from Visual Studio and access the OData feed by submitting HTTP GET requests through a Web browser:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1c445-152">Accedere al servizio da un Web browser</span><span class="sxs-lookup"><span data-stu-id="1c445-152">Access the service from a web browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="1c445-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c445-153">See also</span></span>

- <span data-ttu-id="1c445-154">[Strumenti Entity Data Model ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1c445-154">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
