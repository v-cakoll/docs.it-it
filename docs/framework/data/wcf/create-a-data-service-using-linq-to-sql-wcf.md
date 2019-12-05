---
title: "Procedura: creare un servizio dati tramite un'origine dati LINQ to SQL (WCF Data Services)"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ to SQL
- WCF Data Services, providers
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
ms.openlocfilehash: cde5b9903a1fd164ce106a6a408ac4bb79976642
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802288"
---
# <a name="how-to-create-a-data-service-using-a-linq-to-sql-data-source-wcf-data-services"></a><span data-ttu-id="bcc9c-102">Procedura: creare un servizio dati tramite un'origine dati LINQ to SQL (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="bcc9c-102">How to: Create a Data Service Using a LINQ to SQL Data Source (WCF Data Services)</span></span>

<span data-ttu-id="bcc9c-103">WCF Data Services espone i dati di entità come servizio dati.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-103">WCF Data Services exposes entity data as a data service.</span></span> <span data-ttu-id="bcc9c-104">Il provider di reflection consente di definire un modello di dati basato su qualsiasi classe che espone i membri che restituiscono un'implementazione di <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-104">The reflection provider enables you to define a data model that is based on any class that exposes members that return an <xref:System.Linq.IQueryable%601> implementation.</span></span> <span data-ttu-id="bcc9c-105">Per essere in grado di apportare aggiornamenti ai dati nell'origine dati, queste classi devono inoltre implementare l'interfaccia <xref:System.Data.Services.IUpdatable>.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-105">To be able to make updates to data in the data source, these classes must also implement the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="bcc9c-106">Per ulteriori informazioni, vedere [provider di servizi dati](data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bcc9c-106">For more information, see [Data Services Providers](data-services-providers-wcf-data-services.md).</span></span> <span data-ttu-id="bcc9c-107">In questo argomento viene illustrato come creare classi LINQ to SQL per l'accesso al database Northwind di esempio tramite il provider di reflection, nonché come creare il servizio dati basato su queste classi di dati.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-107">This topic shows you how to create LINQ to SQL classes that access the Northwind sample database by using the reflection provider, as well as how to create the data service that is based on these data classes.</span></span>

## <a name="to-add-linq-to-sql-classes-to-a-project"></a><span data-ttu-id="bcc9c-108">Per aggiungere classi LINQ to SQL a un progetto</span><span class="sxs-lookup"><span data-stu-id="bcc9c-108">To add LINQ to SQL classes to a project</span></span>

1. <span data-ttu-id="bcc9c-109">Dall'interno di un Visual Basic C# o di un'applicazione scegliere **Aggiungi** > **nuovo elemento**dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="bcc9c-109">From within a Visual Basic or C# application, on the **Project** menu, click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="bcc9c-110">Fare clic sul modello **classi LINQ to SQL** .</span><span class="sxs-lookup"><span data-stu-id="bcc9c-110">Click the **LINQ to SQL Classes** template.</span></span>

3. <span data-ttu-id="bcc9c-111">Modificare il nome in **Northwind. dbml**.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-111">Change the name to **Northwind.dbml**.</span></span>

4. <span data-ttu-id="bcc9c-112">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-112">Click **Add**.</span></span>

     <span data-ttu-id="bcc9c-113">Il file Northwind.dbml verrà aggiunto al progetto e verrà visualizzato Progettazione relazionale oggetti.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-113">The Northwind.dbml file is added to the project and the Object Relational Designer (O/R Designer) opens.</span></span>

5. <span data-ttu-id="bcc9c-114">In **Server**/**Esplora database**, in Northwind, espandere **tabelle** e trascinare la tabella `Customers` nel Object Relational Designer (O/R Designer).</span><span class="sxs-lookup"><span data-stu-id="bcc9c-114">In **Server**/**Database Explorer**, under Northwind, expand **Tables** and drag the `Customers` table onto the Object Relational Designer (O/R Designer).</span></span>

     <span data-ttu-id="bcc9c-115">Verrà creata una classe di entità `Customer` che verrà visualizzata nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-115">A `Customer` entity class is created and appears on the design surface.</span></span>

6. <span data-ttu-id="bcc9c-116">Ripetere il passaggio 6 per le tabelle `Orders`, `Order_Details` e `Products`.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-116">Repeat step 6 for the `Orders`, `Order_Details`, and `Products` tables.</span></span>

7. <span data-ttu-id="bcc9c-117">Fare clic con il pulsante destro del mouse sul nuovo file con estensione dbml che rappresenta le classi LINQ to SQL e scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-117">Right-click the new .dbml file that represents the LINQ to SQL classes and click **View Code**.</span></span>

     <span data-ttu-id="bcc9c-118">Verrà creata una nuova pagina code-behind denominata Northwind.cs contenente una definizione di classe parziale per la classe che eredita dalla classe <xref:System.Data.Linq.DataContext>, che in questo caso corrisponde a `NorthwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-118">This creates a new code-behind page named Northwind.cs that contains a partial class definition for the class that inherits from the <xref:System.Data.Linq.DataContext> class, which in this case is `NorthwindDataContext`.</span></span>

8. <span data-ttu-id="bcc9c-119">Sostituire il contenuto del file di codice Northwind.cs con il codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-119">Replace the contents of the Northwind.cs code file with the following code.</span></span> <span data-ttu-id="bcc9c-120">Questo codice implementa il provider di reflection mediante l'estensione di <xref:System.Data.Linq.DataContext> e delle classi di dati generate da LINQ to SQL:</span><span class="sxs-lookup"><span data-stu-id="bcc9c-120">This code implements the reflection provider by extending the <xref:System.Data.Linq.DataContext> and data classes generated by LINQ to SQL:</span></span>

     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_linq_provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_linq_provider/vb/northwind.vb#linq2sqlprovider)]

### <a name="to-create-a-data-service-by-using-a-linq-to-sql-based-data-model"></a><span data-ttu-id="bcc9c-121">Per creare un servizio dati tramite un modello di dati basato su LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="bcc9c-121">To create a data service by using a LINQ to SQL-based data model</span></span>

1. <span data-ttu-id="bcc9c-122">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nome del progetto ASP.NET, quindi scegliere **Aggiungi** > **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-122">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="bcc9c-123">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare il modello di **servizio dati WCF** dalla categoria **Web** .</span><span class="sxs-lookup"><span data-stu-id="bcc9c-123">In the **Add New Item** dialog box, select the **WCF Data Service** template from the **Web** category.</span></span>

   ![Modello di elemento del servizio dati WCF in Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="bcc9c-125">Il modello di **servizio dati WCF** è disponibile in visual studio 2015, ma non in visual studio 2017 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-125">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

3. <span data-ttu-id="bcc9c-126">Specificare un nome per il servizio, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-126">Supply a name for the service, and then click **OK**.</span></span>

     <span data-ttu-id="bcc9c-127">In Visual Studio verranno creati i file del markup XML e del codice per il nuovo servizio.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-127">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="bcc9c-128">Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-128">By default, the code-editor window opens.</span></span>

4. <span data-ttu-id="bcc9c-129">Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo del contenitore di entità del modello di dati, che in questo caso corrisponde a `NorthwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-129">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindDataContext`.</span></span>

5. <span data-ttu-id="bcc9c-130">Nel codice per il servizio dati sostituire il codice segnaposto nella funzione `InitializeService` con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="bcc9c-130">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>

     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_linq_provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_linq_provider/vb/northwind.svc.vb#enableaccess)]

     <span data-ttu-id="bcc9c-131">In questo modo i client autorizzati saranno in grado di accedere alle risorse per i tre set di entità specificati.</span><span class="sxs-lookup"><span data-stu-id="bcc9c-131">This enables authorized clients to access resources for the three specified entity sets.</span></span>

6. <span data-ttu-id="bcc9c-132">Per testare il servizio dati Northwind. svc utilizzando una Web browser, seguire le istruzioni riportate nell'argomento [accesso al servizio da un Web browser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="bcc9c-132">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bcc9c-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcc9c-133">See also</span></span>

- [<span data-ttu-id="bcc9c-134">Procedura: creare un servizio dati tramite un'origine dati ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="bcc9c-134">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source</span></span>](create-a-data-service-using-an-adonet-ef-data-wcf.md)
- [<span data-ttu-id="bcc9c-135">Procedura: creare un servizio dati tramite il provider di reflection</span><span class="sxs-lookup"><span data-stu-id="bcc9c-135">How to: Create a Data Service Using the Reflection Provider</span></span>](create-a-data-service-using-rp-wcf-data-services.md)
- [<span data-ttu-id="bcc9c-136">Provider di servizi dati</span><span class="sxs-lookup"><span data-stu-id="bcc9c-136">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)
