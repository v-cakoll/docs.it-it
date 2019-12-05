---
title: "Procedura: creare un servizio dati tramite un'origine dati ADO.NET Entity Framework (WCF Data Services)"
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
ms.openlocfilehash: 0aea4c21b5ea34cb0e8d944d37c879e918d6b27e
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74800594"
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a><span data-ttu-id="39cd3-102">Procedura: creare un servizio dati tramite un'origine dati ADO.NET Entity Framework (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="39cd3-102">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source (WCF Data Services)</span></span>

<span data-ttu-id="39cd3-103">WCF Data Services espone i dati di entità come servizio dati.</span><span class="sxs-lookup"><span data-stu-id="39cd3-103">WCF Data Services exposes entity data as a data service.</span></span> <span data-ttu-id="39cd3-104">Questi dati dell'entità vengono forniti dal framework ADO. NETEntity quando l'origine dati è un database relazionale.</span><span class="sxs-lookup"><span data-stu-id="39cd3-104">This entity data is provided by the ADO.NETEntity Framework when the data source is a relational database.</span></span> <span data-ttu-id="39cd3-105">In questo argomento viene illustrato come creare un modello di dati basato su Entity Framework in un'applicazione Web di Visual Studio basata su un database esistente e come utilizzare questo modello di dati per creare un nuovo servizio dati.</span><span class="sxs-lookup"><span data-stu-id="39cd3-105">This topic shows you how to create an Entity Framework-based data model in a Visual Studio Web application that is based on an existing database and use this data model to create a new data service.</span></span>

<span data-ttu-id="39cd3-106">Entity Framework fornisce inoltre un strumento da riga di comando che può generare un modello di Entity Framework all'esterno di un progetto di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="39cd3-106">The Entity Framework also provides a command line tool that can generate an Entity Framework model outside of a Visual Studio project.</span></span> <span data-ttu-id="39cd3-107">Per altre informazioni, vedere [procedura: usare EdmGen. exe per generare i file di modello e di mapping](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="39cd3-107">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>

## <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a><span data-ttu-id="39cd3-108">Per aggiungere un modello di Entity Framework basato su un database esistente a un'applicazione Web esistente</span><span class="sxs-lookup"><span data-stu-id="39cd3-108">To add an Entity Framework model that is based on an existing database to an existing Web application</span></span>

1. <span data-ttu-id="39cd3-109">Scegliere **aggiungi** > **nuovo elemento**dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="39cd3-109">On the **Project** menu, click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="39cd3-110">Nel riquadro **modelli** fare clic sulla categoria di **dati** , quindi selezionare **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="39cd3-110">In the **Templates** pane, click the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="39cd3-111">Immettere il nome del modello e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="39cd3-111">Enter the model name and then click **Add**.</span></span>

     <span data-ttu-id="39cd3-112">Verrà visualizzata la prima pagina della procedura guidata Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="39cd3-112">The first page of the Entity Data Model Wizard is displayed.</span></span>

4. <span data-ttu-id="39cd3-113">Nella finestra di dialogo **Scegli contenuto Model** selezionare **genera da database**.</span><span class="sxs-lookup"><span data-stu-id="39cd3-113">In the **Choose Model Contents** dialog box, select **Generate from database**.</span></span> <span data-ttu-id="39cd3-114">Fare quindi clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="39cd3-114">Then click **Next**.</span></span>

5. <span data-ttu-id="39cd3-115">Fare clic sul pulsante **nuova connessione** .</span><span class="sxs-lookup"><span data-stu-id="39cd3-115">Click the **New Connection** button.</span></span>

6. <span data-ttu-id="39cd3-116">Nella finestra di dialogo **Proprietà connessione** Digitare il nome del server, selezionare il metodo di autenticazione, digitare il nome del database, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="39cd3-116">In the **Connection Properties** dialog box, type your server name, select the authentication method, type the database name, and then click **OK**.</span></span>

     <span data-ttu-id="39cd3-117">La finestra di dialogo **scegliere la connessione dati** viene aggiornata con le impostazioni di connessione del database.</span><span class="sxs-lookup"><span data-stu-id="39cd3-117">The **Choose Your Data Connection** dialog box is updated with your database connection settings.</span></span>

7. <span data-ttu-id="39cd3-118">Verificare che la casella **di controllo Salva le impostazioni di connessione dell'entità in app. config come:** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="39cd3-118">Ensure that the **Save entity connection settings in App.Config as:** checkbox is checked.</span></span> <span data-ttu-id="39cd3-119">Fare quindi clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="39cd3-119">Then click **Next**.</span></span>

8. <span data-ttu-id="39cd3-120">Nella finestra di dialogo **Scegli oggetti di database** selezionare tutti gli oggetti di database che si intende esporre nel servizio dati.</span><span class="sxs-lookup"><span data-stu-id="39cd3-120">In the **Choose Your Database Objects** dialog box, select all of database objects that you plan to expose in the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="39cd3-121">Gli oggetti inclusi nel modello di dati non vengono esposti automaticamente dal servizio dati.</span><span class="sxs-lookup"><span data-stu-id="39cd3-121">Objects included in the data model are not automatically exposed by the data service.</span></span> <span data-ttu-id="39cd3-122">Devono essere esposti in modo esplicito mediante il servizio stesso.</span><span class="sxs-lookup"><span data-stu-id="39cd3-122">They must be explicitly exposed by the service itself.</span></span> <span data-ttu-id="39cd3-123">Per ulteriori informazioni, vedere [configurazione del servizio dati](configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="39cd3-123">For more information, see [Configuring the Data Service](configuring-the-data-service-wcf-data-services.md).</span></span>

9. <span data-ttu-id="39cd3-124">Fare clic su **Fine** per completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="39cd3-124">Click **Finish** to complete the wizard.</span></span>

     <span data-ttu-id="39cd3-125">Verrà creato un modello di dati predefinito in base al database specifico.</span><span class="sxs-lookup"><span data-stu-id="39cd3-125">This creates a default data model based on the specific database.</span></span> <span data-ttu-id="39cd3-126">Entity Framework consente di personalizzare il modello di dati.</span><span class="sxs-lookup"><span data-stu-id="39cd3-126">The Entity Framework enables to customize the data model.</span></span> <span data-ttu-id="39cd3-127">Per ulteriori informazioni, vedere [attività di Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="39cd3-127">For more information, see [Entity Data Model Tools Tasks](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).</span></span>

## <a name="to-create-the-data-service-by-using-the-new-data-model"></a><span data-ttu-id="39cd3-128">Per creare il servizio dati usando il nuovo modello di dati</span><span class="sxs-lookup"><span data-stu-id="39cd3-128">To create the data service by using the new data model</span></span>

1. <span data-ttu-id="39cd3-129">In Visual Studio aprire il file con estensione edmx che rappresenta il modello di dati.</span><span class="sxs-lookup"><span data-stu-id="39cd3-129">In Visual Studio, open the .edmx file that represents the data model.</span></span>

2. <span data-ttu-id="39cd3-130">In **browser modello**fare clic con il pulsante destro del mouse sul modello, scegliere **Proprietà**, quindi prendere nota del nome del contenitore di entità.</span><span class="sxs-lookup"><span data-stu-id="39cd3-130">In the **Model Browser**, right-click the model, click **Properties**, and then note the name of the entity container.</span></span>

3. <span data-ttu-id="39cd3-131">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nome del progetto ASP.NET, quindi scegliere **Aggiungi** > **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="39cd3-131">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

4. <span data-ttu-id="39cd3-132">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare il modello **WCF Data Services** nella categoria **Web** .</span><span class="sxs-lookup"><span data-stu-id="39cd3-132">In the **Add New Item** dialog box, select the **WCF Data Service** template in the **Web** category.</span></span>

   ![Modello di elemento del servizio dati WCF in Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="39cd3-134">Il modello di **servizio dati WCF** è disponibile in visual studio 2015, ma non in visual studio 2017 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="39cd3-134">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

5. <span data-ttu-id="39cd3-135">Specificare un nome per il servizio, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="39cd3-135">Supply a name for the service, and then click **OK**.</span></span>

     <span data-ttu-id="39cd3-136">In Visual Studio verranno creati i file del markup XML e del codice per il nuovo servizio.</span><span class="sxs-lookup"><span data-stu-id="39cd3-136">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="39cd3-137">Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="39cd3-137">By default, the code-editor window opens.</span></span>

6. <span data-ttu-id="39cd3-138">Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo che eredita dalla classe <xref:System.Data.Objects.ObjectContext> e che rappresenta il contenitore di entità del modello di dati annotato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="39cd3-138">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that inherits from the <xref:System.Data.Objects.ObjectContext> class and that is the entity container of the data model, which was noted in step 2.</span></span>

7. <span data-ttu-id="39cd3-139">Nel codice per il servizio dati consentire ai client autorizzati di accedere ai set di entità esposti dal servizio dati.</span><span class="sxs-lookup"><span data-stu-id="39cd3-139">In the code for the data service, enable authorized clients to access the entity sets that the data service exposes.</span></span> <span data-ttu-id="39cd3-140">Per ulteriori informazioni, vedere [creazione del servizio dati](creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="39cd3-140">For more information, see [Creating the Data Service](creating-the-data-service.md).</span></span>

8. <span data-ttu-id="39cd3-141">Per testare il servizio dati Northwind. svc utilizzando una Web browser, seguire le istruzioni riportate nell'argomento [accesso al servizio da un Web browser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="39cd3-141">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="39cd3-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39cd3-142">See also</span></span>

- [<span data-ttu-id="39cd3-143">Definizione di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="39cd3-143">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
- [<span data-ttu-id="39cd3-144">Provider di servizi dati</span><span class="sxs-lookup"><span data-stu-id="39cd3-144">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="39cd3-145">Procedura: creare un servizio dati tramite il provider di reflection</span><span class="sxs-lookup"><span data-stu-id="39cd3-145">How to: Create a Data Service Using the Reflection Provider</span></span>](create-a-data-service-using-rp-wcf-data-services.md)
- [<span data-ttu-id="39cd3-146">Procedura: creare un servizio dati tramite un'origine dati LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="39cd3-146">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](create-a-data-service-using-linq-to-sql-wcf.md)
