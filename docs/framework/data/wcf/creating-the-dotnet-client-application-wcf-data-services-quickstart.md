---
title: Creazione dell'applicazione client .NET Framework (Guida rapida di WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: 9995a509bf997298d991a1f66cfdf3cae6cd0395
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790957"
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a><span data-ttu-id="ea013-102">Creazione dell'applicazione client .NET Framework (Guida rapida di WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="ea013-102">Creating the .NET Framework Client Application (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="ea013-103">Questa è l'attività finale della Guida introduttiva WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="ea013-103">This is the final task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="ea013-104">In questa attività si aggiungerà un'applicazione console alla soluzione, si aggiungerà un riferimento al [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed in questa nuova applicazione client e si accederà al feed OData dall'applicazione client utilizzando le classi del servizio dati client e le librerie client generate. .</span><span class="sxs-lookup"><span data-stu-id="ea013-104">In this task, you will add a console application to the solution, add a reference to the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed into this new client application, and access the OData feed from the client application by using the generated client data service classes and client libraries.</span></span>

> [!NOTE]
> <span data-ttu-id="ea013-105">Per accedere a un feed di dati non è necessario disporre di un'applicazione client basata su .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ea013-105">A .NET Framework-based client application is not required to access a data feed.</span></span> <span data-ttu-id="ea013-106">Il servizio dati può accedere a qualsiasi componente dell'applicazione che utilizza un feed OData.</span><span class="sxs-lookup"><span data-stu-id="ea013-106">The data service can be accessed by any application component that consumes an OData feed.</span></span> <span data-ttu-id="ea013-107">Per ulteriori informazioni, vedere [utilizzo di un servizio dati in un'applicazione client](using-a-data-service-in-a-client-application-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ea013-107">For more information, see [Using a Data Service in a Client Application](using-a-data-service-in-a-client-application-wcf-data-services.md).</span></span>

## <a name="to-create-the-client-application-by-using-visual-studio"></a><span data-ttu-id="ea013-108">Per creare l'applicazione client tramite Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ea013-108">To create the client application by using Visual Studio</span></span>

1. <span data-ttu-id="ea013-109">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sulla soluzione, scegliere **Aggiungi**, quindi fare clic su **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="ea013-109">In **Solution Explorer**, right-click the solution, click **Add**, and then click **New Project**.</span></span>

2. <span data-ttu-id="ea013-110">Nel riquadro sinistro selezionare **installato** > [ **C# Visual** o **Visual Basic**] > Desktop di **Windows**, quindi selezionare il modello **applicazione WPF** .</span><span class="sxs-lookup"><span data-stu-id="ea013-110">In the left pane, select **Installed** > [**Visual C#** or **Visual Basic**] > **Windows Desktop**, and then select the **WPF App** template.</span></span>

3. <span data-ttu-id="ea013-111">Immettere `NorthwindClient` per il nome del progetto, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea013-111">Enter `NorthwindClient` for the project name, and then click **OK**.</span></span>

4. <span data-ttu-id="ea013-112">Aprire il file MainWindow.xaml e sostituire il codice XAML con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ea013-112">Open the file MainWindow.xaml and replace the XAML code with the following code:</span></span>

     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml#window1xaml)]

## <a name="to-add-a-data-service-reference-to-the-project"></a><span data-ttu-id="ea013-113">Per aggiungere un riferimento al servizio dati nel progetto</span><span class="sxs-lookup"><span data-stu-id="ea013-113">To add a data service reference to the project</span></span>

1. <span data-ttu-id="ea013-114">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto NorthwindClient, scegliere **Aggiungi** > **riferimento al servizio**, quindi fare clic su **individua**.</span><span class="sxs-lookup"><span data-stu-id="ea013-114">In **Solution Explorer**, right-click the NorthwindClient project, click **Add** > **Service Reference**, and then click **Discover**.</span></span>

     <span data-ttu-id="ea013-115">Verrà visualizzato il servizio dati Northwind creato nella prima attività.</span><span class="sxs-lookup"><span data-stu-id="ea013-115">This displays the Northwind data service that you created in the first task.</span></span>

2. <span data-ttu-id="ea013-116">Nella casella di testo **spazio dei nomi** Digitare `Northwind`, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea013-116">In the **Namespace** text box, type `Northwind`, and then click **OK**.</span></span>

     <span data-ttu-id="ea013-117">Verrà aggiunto un nuovo file di codice al progetto, che contiene le classi di dati usate per accedere e interagire con le risorse del servizio dati come oggetti.</span><span class="sxs-lookup"><span data-stu-id="ea013-117">This adds a new code file to the project, which contains the data classes that are used to access and interact with data service resources as objects.</span></span> <span data-ttu-id="ea013-118">Le classi di dati vengono create nello spazio dei nomi `NorthwindClient.Northwind`.</span><span class="sxs-lookup"><span data-stu-id="ea013-118">The data classes are created in the namespace `NorthwindClient.Northwind`.</span></span>

## <a name="to-access-data-service-data-in-the-wpf-application"></a><span data-ttu-id="ea013-119">Per accedere ai dati del servizio dati nell'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="ea013-119">To access data service data in the WPF application</span></span>

1. <span data-ttu-id="ea013-120">In **Esplora soluzioni** in **NorthwindClient**fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="ea013-120">In **Solution Explorer** under **NorthwindClient**, right-click the project and click **Add Reference**.</span></span>

2. <span data-ttu-id="ea013-121">Nella finestra di dialogo **Aggiungi riferimento** fare clic sulla scheda **.NET** , selezionare l'assembly System. Data. Services. client. dll, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea013-121">In the **Add Reference** dialog box, click the **.NET** tab, select the System.Data.Services.Client.dll assembly, and then click **OK**.</span></span>

3. <span data-ttu-id="ea013-122">In **Esplora soluzioni** in **NorthwindClient**aprire la tabella codici per il file MainWindow. XAML e aggiungere l'istruzione seguente `using` (`Imports` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="ea013-122">In **Solution Explorer** under **NorthwindClient**, open the code page for the MainWindow.xaml file, and add the following `using` statement (`Imports` in Visual Basic).</span></span>

    [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#using)]
    [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#using)]

4. <span data-ttu-id="ea013-123">Inserire il codice seguente che consente di eseguire una query sul servizio dati e di associare il risultato a un oggetto <xref:System.Data.Services.Client.DataServiceCollection%601> nella classe `MainWindow`:</span><span class="sxs-lookup"><span data-stu-id="ea013-123">Insert the following code that queries that data service and binds the result to a <xref:System.Data.Services.Client.DataServiceCollection%601> into the `MainWindow` class:</span></span>

    > [!NOTE]
    > <span data-ttu-id="ea013-124">È necessario sostituire il nome host `localhost:12345` con il server e la porta di hosting dell'istanza del servizio dati Northwind.</span><span class="sxs-lookup"><span data-stu-id="ea013-124">You must replace the host name `localhost:12345` with the server and port that is hosting your instance of the Northwind data service.</span></span>

     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#querycode)]

5. <span data-ttu-id="ea013-125">Inserire il codice seguente che consente di salvare le modifiche nella classe `MainWindow`:</span><span class="sxs-lookup"><span data-stu-id="ea013-125">Insert the following code that saves changes into the `MainWindow` class:</span></span>

     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#savechanges)]

## <a name="to-build-and-run-the-northwindclient-application"></a><span data-ttu-id="ea013-126">Per compilare ed eseguire l'applicazione NorthwindClient</span><span class="sxs-lookup"><span data-stu-id="ea013-126">To build and run the NorthwindClient application</span></span>

1. <span data-ttu-id="ea013-127">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto NorthwindClient e selezionare **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="ea013-127">In **Solution Explorer**, right-click the NorthwindClient project and select **Set as startup project**.</span></span>

2. <span data-ttu-id="ea013-128">Premere **F5** per avviare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ea013-128">Press **F5** to start the application.</span></span>

     <span data-ttu-id="ea013-129">La soluzione viene compilata e l'applicazione client viene avviata.</span><span class="sxs-lookup"><span data-stu-id="ea013-129">This builds the solution and starts the client application.</span></span> <span data-ttu-id="ea013-130">I dati vengono richiesti dal servizio e visualizzati nella console.</span><span class="sxs-lookup"><span data-stu-id="ea013-130">Data is requested from the service and displayed in the console.</span></span>

3. <span data-ttu-id="ea013-131">Modificare un valore nella colonna **Quantity** della griglia dei dati, quindi fare clic su **Save**.</span><span class="sxs-lookup"><span data-stu-id="ea013-131">Edit a value in the **Quantity** column of the data grid, and then click **Save**.</span></span>

     <span data-ttu-id="ea013-132">Le modifiche vengono salvate nel servizio dati.</span><span class="sxs-lookup"><span data-stu-id="ea013-132">Changes are saved to the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ea013-133">Questa versione dell'applicazione NorthwindClient non supporta l'aggiunta e l'eliminazione di entità.</span><span class="sxs-lookup"><span data-stu-id="ea013-133">This version of the NorthwindClient application does not support adding and deleting of entities.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ea013-134">Fasi successive</span><span class="sxs-lookup"><span data-stu-id="ea013-134">Next Steps</span></span>

<span data-ttu-id="ea013-135">È stata creata correttamente l'applicazione client che accede al feed OData di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="ea013-135">You have successfully created the client application that accesses the sample Northwind OData feed.</span></span> <span data-ttu-id="ea013-136">È stata anche completata la Guida introduttiva WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="ea013-136">You've also completed the WCF Data Services quickstart!</span></span>

<span data-ttu-id="ea013-137">Per ulteriori informazioni sull'accesso a un feed OData da un'applicazione .NET Framework, vedere la pagina relativa alla [libreria Client WCF Data Services](wcf-data-services-client-library.md).</span><span class="sxs-lookup"><span data-stu-id="ea013-137">For more information about accessing an OData feed from a .NET Framework application, see [WCF Data Services Client Library](wcf-data-services-client-library.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ea013-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea013-138">See also</span></span>

- [<span data-ttu-id="ea013-139">Introduzione</span><span class="sxs-lookup"><span data-stu-id="ea013-139">Getting Started</span></span>](getting-started-with-wcf-data-services.md)
- [<span data-ttu-id="ea013-140">Risorse</span><span class="sxs-lookup"><span data-stu-id="ea013-140">Resources</span></span>](wcf-data-services-resources.md)
