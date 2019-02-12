---
title: "Procedura: Creare un servizio dati tramite un'origine dati di ADO.NET Entity Framework (WCF Data Services)"
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
ms.openlocfilehash: b2adf4fe0d510f65db5bded715f084a4d7e016b6
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2019
ms.locfileid: "56093099"
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a><span data-ttu-id="b25a2-102">Procedura: Creare un servizio dati tramite un'origine dati di ADO.NET Entity Framework (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="b25a2-102">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source (WCF Data Services)</span></span>

<span data-ttu-id="b25a2-103">WCF Data Services espone i dati di entità come un servizio dati.</span><span class="sxs-lookup"><span data-stu-id="b25a2-103">WCF Data Services exposes entity data as a data service.</span></span> <span data-ttu-id="b25a2-104">Tali dati vengono forniti da [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)][!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] quando l'origine dati è un database relazionale.</span><span class="sxs-lookup"><span data-stu-id="b25a2-104">This entity data is provided by the [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)][!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] when the data source is a relational database.</span></span> <span data-ttu-id="b25a2-105">In questo argomento viene illustrato come creare un [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-basato sul modello di dati in un'applicazione Web di Visual Studio che si basa su un database esistente e Usa questo modello di dati per creare un nuovo servizio dati.</span><span class="sxs-lookup"><span data-stu-id="b25a2-105">This topic shows you how to create an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-based data model in a Visual Studio Web application that is based on an existing database and use this data model to create a new data service.</span></span>

<span data-ttu-id="b25a2-106">Il [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] fornisce anche uno strumento da riga di comando che può generare un [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] modello all'esterno di un progetto di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b25a2-106">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] also provides a command line tool that can generate an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] model outside of a Visual Studio project.</span></span> <span data-ttu-id="b25a2-107">Per altre informazioni, vedere [Procedura: Consente di generare il modello e i file di Mapping EdmGen.exe](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="b25a2-107">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>

## <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a><span data-ttu-id="b25a2-108">Per aggiungere un modello di Entity Framework basato su un database esistente a un'applicazione Web esistente</span><span class="sxs-lookup"><span data-stu-id="b25a2-108">To add an Entity Framework model that is based on an existing database to an existing Web application</span></span>

1. <span data-ttu-id="b25a2-109">Nel **Project** menu, fare clic su **Add** > **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="b25a2-109">On the **Project** menu, click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="b25a2-110">Nel **modelli** riquadro, fare clic sul **Data** categoria e quindi selezionare **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="b25a2-110">In the **Templates** pane, click the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="b25a2-111">Immettere il nome del modello e quindi fare clic su **Add**.</span><span class="sxs-lookup"><span data-stu-id="b25a2-111">Enter the model name and then click **Add**.</span></span>

     <span data-ttu-id="b25a2-112">Verrà visualizzata la prima pagina della Procedura guidata [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b25a2-112">The first page of the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] Wizard is displayed.</span></span>

4. <span data-ttu-id="b25a2-113">Nel **Scegli contenuto Model** finestra di dialogo **genera da database**.</span><span class="sxs-lookup"><span data-stu-id="b25a2-113">In the **Choose Model Contents** dialog box, select **Generate from database**.</span></span> <span data-ttu-id="b25a2-114">Scegliere quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b25a2-114">Then click **Next**.</span></span>

5. <span data-ttu-id="b25a2-115">Scegliere il **nuova connessione** pulsante.</span><span class="sxs-lookup"><span data-stu-id="b25a2-115">Click the **New Connection** button.</span></span>

6. <span data-ttu-id="b25a2-116">Nel **proprietà connessione** della finestra di dialogo digitare il nome del server, selezionare il metodo di autenticazione, digitare il nome del database e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b25a2-116">In the **Connection Properties** dialog box, type your server name, select the authentication method, type the database name, and then click **OK**.</span></span>

     <span data-ttu-id="b25a2-117">Il **Seleziona connessione dati** nella finestra di dialogo viene aggiornata con le impostazioni di connessione di database.</span><span class="sxs-lookup"><span data-stu-id="b25a2-117">The **Choose Your Data Connection** dialog box is updated with your database connection settings.</span></span>

7. <span data-ttu-id="b25a2-118">Verificare che il **Salva impostazioni di connessione entity in App. config come:** casella di controllo è selezionata.</span><span class="sxs-lookup"><span data-stu-id="b25a2-118">Ensure that the **Save entity connection settings in App.Config as:** checkbox is checked.</span></span> <span data-ttu-id="b25a2-119">Scegliere quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b25a2-119">Then click **Next**.</span></span>

8. <span data-ttu-id="b25a2-120">Nel **Scegli oggetti di Database** nella finestra di dialogo database selezionare tutti gli oggetti che si intende esporre nel servizio dati.</span><span class="sxs-lookup"><span data-stu-id="b25a2-120">In the **Choose Your Database Objects** dialog box, select all of database objects that you plan to expose in the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b25a2-121">Gli oggetti inclusi nel modello di dati non vengono esposti automaticamente dal servizio dati.</span><span class="sxs-lookup"><span data-stu-id="b25a2-121">Objects included in the data model are not automatically exposed by the data service.</span></span> <span data-ttu-id="b25a2-122">Devono essere esposti in modo esplicito mediante il servizio stesso.</span><span class="sxs-lookup"><span data-stu-id="b25a2-122">They must be explicitly exposed by the service itself.</span></span> <span data-ttu-id="b25a2-123">Per altre informazioni, vedere [configurazione del servizio dati](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b25a2-123">For more information, see [Configuring the Data Service](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span></span>

9. <span data-ttu-id="b25a2-124">Fare clic su **fine** per completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="b25a2-124">Click **Finish** to complete the wizard.</span></span>

     <span data-ttu-id="b25a2-125">Verrà creato un modello di dati predefinito in base al database specifico.</span><span class="sxs-lookup"><span data-stu-id="b25a2-125">This creates a default data model based on the specific database.</span></span> <span data-ttu-id="b25a2-126">
  [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] consente di personalizzare il modello di dati.</span><span class="sxs-lookup"><span data-stu-id="b25a2-126">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] enables to customize the data model.</span></span> <span data-ttu-id="b25a2-127">Per altre informazioni, vedere [Entity Data Model Tools Tasks](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b25a2-127">For more information, see [Entity Data Model Tools Tasks](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).</span></span>

## <a name="to-create-the-data-service-by-using-the-new-data-model"></a><span data-ttu-id="b25a2-128">Per creare il servizio dati usando il nuovo modello di dati</span><span class="sxs-lookup"><span data-stu-id="b25a2-128">To create the data service by using the new data model</span></span>

1. <span data-ttu-id="b25a2-129">In Visual Studio aprire il file con estensione edmx che rappresenta il modello di dati.</span><span class="sxs-lookup"><span data-stu-id="b25a2-129">In Visual Studio, open the .edmx file that represents the data model.</span></span>

2. <span data-ttu-id="b25a2-130">Nel **Visualizzatore modelli**, fare clic sul modello, fare clic su **proprietà**e quindi prendere nota del nome del contenitore di entità.</span><span class="sxs-lookup"><span data-stu-id="b25a2-130">In the **Model Browser**, right-click the model, click **Properties**, and then note the name of the entity container.</span></span>

3. <span data-ttu-id="b25a2-131">Nella **Esplora soluzioni**, fare doppio clic il nome delle [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] del progetto e quindi fare clic su **Add** > **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="b25a2-131">In **Solution Explorer**, right-click the name of your [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add** > **New Item**.</span></span>

4. <span data-ttu-id="b25a2-132">Nel **Aggiungi nuovo elemento** finestra di dialogo, seleziona la **WCF Data Services** modello nel **Web** categoria.</span><span class="sxs-lookup"><span data-stu-id="b25a2-132">In the **Add New Item** dialog box, select the **WCF Data Service** template in the **Web** category.</span></span>

   ![Modello di elemento di WCF Data Services in Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="b25a2-134">Il **di WCF Data Services** modello è disponibile in Visual Studio 2015, ma non in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="b25a2-134">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

5. <span data-ttu-id="b25a2-135">Specificare un nome per il servizio e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b25a2-135">Supply a name for the service, and then click **OK**.</span></span>

     <span data-ttu-id="b25a2-136">In Visual Studio verranno creati i file del markup XML e del codice per il nuovo servizio.</span><span class="sxs-lookup"><span data-stu-id="b25a2-136">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="b25a2-137">Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="b25a2-137">By default, the code-editor window opens.</span></span>

6. <span data-ttu-id="b25a2-138">Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo che eredita dalla classe <xref:System.Data.Objects.ObjectContext> e che rappresenta il contenitore di entità del modello di dati annotato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="b25a2-138">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that inherits from the <xref:System.Data.Objects.ObjectContext> class and that is the entity container of the data model, which was noted in step 2.</span></span>

7. <span data-ttu-id="b25a2-139">Nel codice per il servizio dati consentire ai client autorizzati di accedere ai set di entità esposti dal servizio dati.</span><span class="sxs-lookup"><span data-stu-id="b25a2-139">In the code for the data service, enable authorized clients to access the entity sets that the data service exposes.</span></span> <span data-ttu-id="b25a2-140">Per altre informazioni, vedere [creazione del servizio dati](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="b25a2-140">For more information, see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>

8. <span data-ttu-id="b25a2-141">Per testare il servizio dati Northwind. svc tramite un Web browser, seguire le istruzioni nell'argomento [accesso al servizio da un Web Browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="b25a2-141">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b25a2-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b25a2-142">See also</span></span>

- [<span data-ttu-id="b25a2-143">Definizione di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="b25a2-143">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
- [<span data-ttu-id="b25a2-144">Provider di servizi dati</span><span class="sxs-lookup"><span data-stu-id="b25a2-144">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="b25a2-145">Procedura: Creare un servizio dati tramite il Provider di Reflection</span><span class="sxs-lookup"><span data-stu-id="b25a2-145">How to: Create a Data Service Using the Reflection Provider</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)
- [<span data-ttu-id="b25a2-146">Procedura: Creare un servizio dati usando un LINQ all'origine dati SQL</span><span class="sxs-lookup"><span data-stu-id="b25a2-146">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)