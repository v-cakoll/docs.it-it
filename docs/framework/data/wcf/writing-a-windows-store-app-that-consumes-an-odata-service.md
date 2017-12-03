---
title: Scrittura di un'app di Windows Store che utilizza un servizio OData
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: csharp
ms.assetid: 9917a0e9-ec93-49e5-a366-fd39b892eb8b
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eeee9dcf27d63f5bc40dfdfce1ff7d8104060b6a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="writing-a-windows-store-app-that-consumes-an-odata-service"></a><span data-ttu-id="b0ac8-102">Scrittura di un'app di Windows Store che utilizza un servizio OData</span><span class="sxs-lookup"><span data-stu-id="b0ac8-102">Writing a Windows Store App that consumes an OData Service</span></span>
<span data-ttu-id="b0ac8-103">Windows 8 è stato introdotto un nuovo tipo di applicazione: l'applicazione Windows Store.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-103">Windows 8 introduces a new type of application: the Windows Store app.</span></span> <span data-ttu-id="b0ac8-104">Le app Windows Store hanno un aspetto nuovissimo, vengono eseguite su vari dispositivi e vengono rese disponibili in Windows Store.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-104">Windows Store apps have a brand new look and feel, run on a variety of devices, and are made available on the Windows Store.</span></span> <span data-ttu-id="b0ac8-105">In questo argomento viene descritto come scrivere un'app Windows Store che usa un servizio OData, in particolare il servizio NetFlix Catalog OData.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-105">This topic describes how to write a Windows Store app that consumes an OData service, specifically the NetFlix Catalog OData service.</span></span> <span data-ttu-id="b0ac8-106">Per ulteriori informazioni sulle app di Windows Store, leggere [Introduzione alle app di Windows Store](http://msdn.microsoft.com/library/windows/apps/br211386.aspx).</span><span class="sxs-lookup"><span data-stu-id="b0ac8-106">For more information about Windows Store Apps, please read [Getting Started with Windows Store apps](http://msdn.microsoft.com/library/windows/apps/br211386.aspx).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b0ac8-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b0ac8-107">Prerequisites</span></span>  
  
1.  [<span data-ttu-id="b0ac8-108">Microsoft Windows 8</span><span class="sxs-lookup"><span data-stu-id="b0ac8-108">Microsoft Windows 8</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=266654)  
  
2.  [<span data-ttu-id="b0ac8-109">Microsoft Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="b0ac8-109">Microsoft Visual Studio 2012</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=266655)  
  
3.  [<span data-ttu-id="b0ac8-110">WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="b0ac8-110">WCF Data Services</span></span>](http://msdn.microsoft.com/data/bb931106)  
  
#### <a name="creating-the-default-windows-store-grid-application"></a><span data-ttu-id="b0ac8-111">Creazione della applicazione della griglia di Windows Store predefinita</span><span class="sxs-lookup"><span data-stu-id="b0ac8-111">Creating the default Windows Store Grid Application</span></span>  
  
1.  <span data-ttu-id="b0ac8-112">Creare una nuova applicazione della griglia di Windows Store mediante C# e XAML.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-112">Create a new Windows Store Grid Application using C# and XAML.</span></span> <span data-ttu-id="b0ac8-113">Denominare l'applicazione OData.WindowsStore.NetflixDemo:</span><span class="sxs-lookup"><span data-stu-id="b0ac8-113">Name the application OData.WindowsStore.NetflixDemo:</span></span>  
  
     <span data-ttu-id="b0ac8-114">![Finestra di dialogo Nuovo progetto](../../../../docs/framework/data/wcf/media/win8clientcreatenewproject.png "Win8ClientCreateNewProject")</span><span class="sxs-lookup"><span data-stu-id="b0ac8-114">![New Project Dialog](../../../../docs/framework/data/wcf/media/win8clientcreatenewproject.png "Win8ClientCreateNewProject")</span></span>  
  
2.  <span data-ttu-id="b0ac8-115">Aprire il file Package.appxmanifest e immettere un nome descrittivo nella casella di testo Nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-115">Open the Package.appxmanifest and enter a friendly name in the Display name text box.</span></span> <span data-ttu-id="b0ac8-116">Questo specifica il nome dell'applicazione usato con la funzionalità di ricerca di Windows 8.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-116">This specifies the application name used with the Windows 8 search functionality.</span></span>  
  
     <span data-ttu-id="b0ac8-117">![File manifesto dell'applicazione](../../../../docs/framework/data/wcf/media/appxmanifest.png "appxmanifest")</span><span class="sxs-lookup"><span data-stu-id="b0ac8-117">![Application manifest file](../../../../docs/framework/data/wcf/media/appxmanifest.png "appxmanifest")</span></span>  
  
3.  <span data-ttu-id="b0ac8-118">Immettere un nome descrittivo nel \<AppName > elemento nel file app. Xaml.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-118">Enter a friendly name in the \<AppName> element in the App.xaml file.</span></span> <span data-ttu-id="b0ac8-119">Questo imposta il nome dell'applicazione visualizzato al primo avvio dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="b0ac8-119">This sets the application name that is displayed when the application is launched:</span></span>  
  
     <span data-ttu-id="b0ac8-120">![File app. XAML](../../../../docs/framework/data/wcf/media/appxaml.png "appxaml")</span><span class="sxs-lookup"><span data-stu-id="b0ac8-120">![App.xaml file](../../../../docs/framework/data/wcf/media/appxaml.png "appxaml")</span></span>  
  
4.  <span data-ttu-id="b0ac8-121">Compilare e avviare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-121">Build and launch the application.</span></span> <span data-ttu-id="b0ac8-122">Viene visualizzata la schermata iniziale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-122">You first see the application’s splash screen.</span></span> <span data-ttu-id="b0ac8-123">Nella schermata riportata di seguito viene visualizzata la schermata iniziale predefinita.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-123">The screenshot below displays the default splash screen.</span></span> <span data-ttu-id="b0ac8-124">L'immagine usata viene archiviata nella cartella Assets del progetto.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-124">The image used is stored in the project’s Assets folder.</span></span>  
  
     <span data-ttu-id="b0ac8-125">![Nella schermata iniziale predefinita app](../../../../docs/framework/data/wcf/media/defualtappsplash.png "defualtAppSplash")</span><span class="sxs-lookup"><span data-stu-id="b0ac8-125">![The default app splash screen](../../../../docs/framework/data/wcf/media/defualtappsplash.png "defualtAppSplash")</span></span>  
  
     <span data-ttu-id="b0ac8-126">Successivamente verrà visualizzata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-126">Then the application will be displayed.</span></span>  
  
     <span data-ttu-id="b0ac8-127">![L'applicazione predefinita](../../../../docs/framework/data/wcf/media/defaultapplication.png "DefaultApplication")</span><span class="sxs-lookup"><span data-stu-id="b0ac8-127">![The default application](../../../../docs/framework/data/wcf/media/defaultapplication.png "DefaultApplication")</span></span>  
  
     <span data-ttu-id="b0ac8-128">L'applicazione predefinita definisce un set di classi in SampleDataSource.cs: SampleDataGroup e SampleDataItem, i quali entrambi derivano da SampleDataCommon, che a sua volta deriva da BindableBase.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-128">The default application defines a set of classes in SampleDataSource.cs: SampleDataGroup and SampleDataItem, both of which are derived from SampleDataCommon, which itself is derived from BindableBase.</span></span> <span data-ttu-id="b0ac8-129">SampleDataGroup e SampleDataItem sono associati all'oggetto GridView predefinito.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-129">SampleDataGroup and SampleDataItem are bound to the default GridView.</span></span> <span data-ttu-id="b0ac8-130">SampleDataSource.cs si trova nella cartella DataModel nel progetto NetflixDemo.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-130">SampleDataSource.cs is located in the DataModel folder within the NetflixDemo project.</span></span> <span data-ttu-id="b0ac8-131">Nell'applicazione viene visualizzata una raccolta raggruppata.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-131">The application displays a grouped collection.</span></span> <span data-ttu-id="b0ac8-132">Ogni gruppo contiene un numero qualsiasi di elementi, rappresentati rispettivamente da SampleDataGroup e da SampleDataItem.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-132">Each group contains any number of items, represented by SampleDataGroup and SampleDataItem, respectively.</span></span> <span data-ttu-id="b0ac8-133">Nella schermata precedente è possibile visualizzare un gruppo denominato Titolo gruppo 1 e tutti gli elementi nel gruppo visualizzati insieme.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-133">In the previous screen shot you can see a group called Group Title 1 and all of the items in the group displayed together.</span></span>  
  
     <span data-ttu-id="b0ac8-134">La pagina principale dell'applicazione è GroupedItemsPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-134">The main page of the application is GroupedItemsPage.xaml.</span></span> <span data-ttu-id="b0ac8-135">Contiene GridView che visualizza i dati di esempio creati dalla classe SampleDataSource.cs.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-135">It contains a GridView that displays the sample data created by the SampleDataSource.cs class.</span></span> <span data-ttu-id="b0ac8-136">L'oggetto GroupedItemsPage viene caricato da App.xaml.cs in una chiamata a rootFrame.Navigate:</span><span class="sxs-lookup"><span data-stu-id="b0ac8-136">The GroupedItemsPage is loaded by the App.xaml.cs in a call to rootFrame.Navigate:</span></span>  
  
    ```csharp  
    if (!rootFrame.Navigate(typeof(GroupedItemsPage), "AllGroups"))  
    {  
        throw new Exception("Failed to create initial page");  
    }  
    ```  
  
     <span data-ttu-id="b0ac8-137">In questo modo viene creata un'istanza di GroupedItemsPage e viene chiamato il relativo metodo LoadState.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-137">This causes the GroupedItemsPage to be instantiated and it’s LoadState method is called.</span></span> <span data-ttu-id="b0ac8-138">LoadState determina la creazione dell'istanza di SampleDataSource statica, che crea una raccolta di oggetti SampleDataGroup.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-138">LoadState causes the static SampleDataSource instance to be created, which creates a collection of SampleDataGroup objects.</span></span> <span data-ttu-id="b0ac8-139">Ciascun oggetto SampleDataGroup contiene una raccolta di oggetti SampleDataItem.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-139">Each SampleDataGroup object contains a collection of SampleDataItem objects.</span></span> <span data-ttu-id="b0ac8-140">LoadState archivia la raccolta di oggetti SampleDataGroup in DefaultViewModel:</span><span class="sxs-lookup"><span data-stu-id="b0ac8-140">LoadState stores the collection of SampleDataGroup objects in the DefaultViewModel:</span></span>  
  
    ```csharp  
    protected override void LoadState(Object navigationParameter, Dictionary<String, Object> pageState)  
    {  
        var sampleDataGroups = SampleDataSource.GetGroups((String)navigationParameter);  
        this.DefaultViewModel["Groups"] = sampleDataGroups;  
    }  
    ```  
  
     <span data-ttu-id="b0ac8-141">L'oggetto DefaultViewModel viene quindi associato a GridView.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-141">The DefaultViewModel is then bound to the GridView.</span></span> <span data-ttu-id="b0ac8-142">A questo oggetto fa riferimento il file GroupedItemsPage.xaml quando si configura l'associazione dati.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-142">This is referenced in the GroupedItemsPage.xaml file when configuring the data binding.</span></span>  
  
    ```xaml
    <CollectionViewSource  
                x:Name="groupedItemsViewSource"  
                Source="{Binding Groups}"  
                IsSourceGrouped="true"  
                ItemsPath="TopItems"  
                d:Source="{Binding AllGroups, Source={d:DesignInstance Type=data:SampleDataSource, IsDesignTimeCreatable=True}}"/>  
    ```  
  
     <span data-ttu-id="b0ac8-143">L'oggetto CollectionViewSource viene usato come proxy per gestire le raccolte raggruppate.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-143">The CollectionViewSource is used as a proxy for handling grouped collections.</span></span> <span data-ttu-id="b0ac8-144">Quando si verifica l'associazione, scorre la raccolta di oggetti SampleDataGroup per popolare GridView.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-144">When binding occurs, it iterates through the collection of SampleDataGroup objects to populate the GridView.</span></span>  <span data-ttu-id="b0ac8-145">L'attributo di ItemsPath indica a CollectionViewSource la proprietà di ogni oggetto SampleDataGroup da usare per trovare l'oggetto SampleDataItems che contiene.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-145">The ItemsPath attribute tells the CollectionViewSource what property on each SampleDataGroup object to use to find the SampleDataItems it contains.</span></span> <span data-ttu-id="b0ac8-146">In questo caso ciascun oggetto SampleDataGroup contiene una raccolta TopItems di oggetti SampleDataItem.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-146">In this case each SampleDataGroup object contains a TopItems collection of SampleDataItem objects.</span></span>  
  
     <span data-ttu-id="b0ac8-147">Per l'applicazione Netflix, i film vengono raggruppati in base al genere.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-147">For the Netflix application, movies are grouped by genre.</span></span> <span data-ttu-id="b0ac8-148">Pertanto nell'applicazione viene visualizzato un numero di generi e un elenco di film appartenenti a tale genere.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-148">So the application displays a number of genres and a list of movies within that genre.</span></span>  
  
#### <a name="add-a-service-reference-to-the-netflix-odata-service"></a><span data-ttu-id="b0ac8-149">Aggiungere un riferimento al servizio Netflix OData</span><span class="sxs-lookup"><span data-stu-id="b0ac8-149">Add a Service Reference to the Netflix OData Service</span></span>  
  
1.  <span data-ttu-id="b0ac8-150">Prima di poter eseguire tutte le chiamate al servizio Netflix OData, è necessario aggiungere un riferimento al servizio.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-150">Before we can make any calls to the Netflix OData service we need to add a service reference.</span></span> <span data-ttu-id="b0ac8-151">Fare clic con il pulsante destro del mouse sul progetto in Esplora soluzioni e scegliere Aggiungi riferimento al servizio.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-151">Right-click the project in the Solution Explorer and select Add Service Reference…</span></span>  
  
     <span data-ttu-id="b0ac8-152">![Finestra di dialogo riferimento servizio Aggiungi](../../../../docs/framework/data/wcf/media/addservicereferenceodata.png "AddServiceReferenceOData")</span><span class="sxs-lookup"><span data-stu-id="b0ac8-152">![Add Service Reference Dialog](../../../../docs/framework/data/wcf/media/addservicereferenceodata.png "AddServiceReferenceOData")</span></span>  
  
2.  <span data-ttu-id="b0ac8-153">Immettere l'URL per il servizio Netflix OData nella barra degli indirizzi e fare clic su Vai.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-153">Enter the URL for the Netflix OData service in the Address bar and click Go.</span></span> <span data-ttu-id="b0ac8-154">Impostare lo spazio dei nomi di riferimento al servizio su Netflix e fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-154">Set the Namespace of the service reference to Netflix and click OK.</span></span>  
  
     <span data-ttu-id="b0ac8-155">![Errore di riferimento del servizio aggiungere](../../../../docs/framework/data/wcf/media/addservicereferenceerror.png "AddServiceReferenceError")</span><span class="sxs-lookup"><span data-stu-id="b0ac8-155">![Add Service Reference Error](../../../../docs/framework/data/wcf/media/addservicereferenceerror.png "AddServiceReferenceError")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b0ac8-156">Se non è ancora installato [WCF Data Services strumenti per App di Windows Store](http://go.microsoft.com/fwlink/p/?LinkId=266652), verrà visualizzato un messaggio simile a quello precedente.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-156">If you have not yet installed [WCF Data Services Tools for Windows Store Apps](http://go.microsoft.com/fwlink/p/?LinkId=266652), you will be prompted with a message such as the one above.</span></span> <span data-ttu-id="b0ac8-157">Sarà necessario scaricare e installare gli strumenti indicati nel collegamento per continuare.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-157">You will need to download and install the tools referenced in the link to continue.</span></span>  
  
 <span data-ttu-id="b0ac8-158">L'aggiunta del riferimento al servizio genera classi fortemente tipizzate che verranno usate da WCF Data Services per analizzare l'oggetto OData restituito dal servizio Netflix OData.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-158">Adding a service reference generates strongly typed classes that WCF Data Services will use to parse the OData returned by the Netflix OData service.</span></span> <span data-ttu-id="b0ac8-159">Le classi definite in SampleDataSource.cs possono essere associate a GridView. Pertanto è necessario trasferire i dati dalle classi di client OData generate nelle classi collegabili definite in SampleDataSource.cs.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-159">The classes defined in SampleDataSource.cs can be bound to the GridView so we need to transfer the data from the generated OData client classes into the bindable classes defined in SampleDataSource.cs.</span></span>  <span data-ttu-id="b0ac8-160">A questo scopo, è necessario apportare alcune modifiche al modello di dati definito in SampleDataSource.cs.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-160">In order to do this, we need to make some changes to the data model defined in SampleDataSource.cs.</span></span>  
  
#### <a name="update-the-data-model-for-the-application"></a><span data-ttu-id="b0ac8-161">Aggiornare il modello di dati per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="b0ac8-161">Update the data model for the application</span></span>  
  
1.  <span data-ttu-id="b0ac8-162">Sostituire il codice esistente in SampleDataSource.cs con il codice di [questo concetto](https://gist.github.com/3419288).</span><span class="sxs-lookup"><span data-stu-id="b0ac8-162">Replace the existing code in SampleDataSource.cs with the code from [this gist](https://gist.github.com/3419288).</span></span> <span data-ttu-id="b0ac8-163">Il codice aggiornato aggiunge un metodo LoadMovies (alla classe SampleDataSource) che esegue una query sul servizio Netflix OData e popola un elenco di generi (allGroups) e in ogni genere un elenco di film.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-163">The updated code adds a LoadMovies method (to the SampleDataSource class)  that performs a query against the Netflix OData service and populates a list of genres (allGroups) and within each genre a list of movies.</span></span> <span data-ttu-id="b0ac8-164">La classe SampleDataGroup viene usata per rappresentare un genere e la classe SampleDataItem viene usata per rappresentare un film.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-164">The SampleDataGroup class is used to represent a genre and the SampleDataItem class is used to represent a movie.</span></span>  
  
    ```csharp  
    public static async void LoadMovies()  
    {  
        IEnumerable<Title> titles = await ((DataServiceQuery<Title>)Context.Titles  
            .Expand("Genres,AudioFormats,AudioFormats/Language,Awards,Cast")  
            .Where(t => t.Rating == "PG")  
            .OrderByDescending(t => t.ReleaseYear)  
            .Take(300)).ExecuteAsync();  
  
        foreach (Title title in titles)  
        {  
            foreach (Genre netflixGenre in title.Genres)  
            {  
                SampleDataGroup genre = GetGroup(netflixGenre.Name);  
                if (genre == null)  
                {  
                    genre = new SampleDataGroup(netflixGenre.Name, netflixGenre.Name, String.Empty, title.BoxArt.LargeUrl, String.Empty);  
                    Instance.AllGroups.Add(genre);  
                }  
                var content = new StringBuilder();  
                // Write additional things to content here if you want them to display in the item detail.  
                genre.Items.Add(new SampleDataItem(title.Id, title.Name, String.Format("{0}rnrn{1} ({2})", title.Synopsis, title.Rating, title.ReleaseYear), title.BoxArt.HighDefinitionUrl ?? title.BoxArt.LargeUrl, "Description", content.ToString()));  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="b0ac8-165">Il [modello asincrono basato su attività](http://go.microsoft.com/fwlink/p/?LinkId=266651) (TAP) viene usato per ottenere in modo asincrono 300 film (Take) recenti (OrderByDescending) con classificazione PG (Where) da Netflix.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-165">The [Task-based Asynchronous Pattern](http://go.microsoft.com/fwlink/p/?LinkId=266651) (TAP) is used to asynchronously get 300 (Take) recent (OrderByDescending) PG-rated (Where) movies back from Netflix.</span></span> <span data-ttu-id="b0ac8-166">Il resto del codice compone SimpleDataItems e SimpleDataGroups dalle entità che sono state restituite nel feed OData.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-166">The rest of the code constructs SimpleDataItems and SimpleDataGroups from the entities that were returned in the OData feed.</span></span>  
  
     <span data-ttu-id="b0ac8-167">La classe SampleDataSource implementa inoltre un metodo di ricerca semplice.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-167">The SampleDataSource class also implements a simple search method.</span></span> <span data-ttu-id="b0ac8-168">In questo caso, esegue una ricerca in memoria semplice dei filmati caricati.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-168">In this case, it does a simple in-memory search of the loaded movies.</span></span>  
  
    ```csharp  
    public static IEnumerable<SampleDataItem> Search(string searchString)  
    {  
            var regex = new Regex(searchString, RegexOptions.CultureInvariant | RegexOptions.IgnoreCase | RegexOptions.IgnorePatternWhitespace);  
            return Instance.AllGroups  
                .SelectMany(g => g.Items)  
                .Where(m => regex.IsMatch(m.Title) || regex.IsMatch(m.Subtitle))  
                    .Distinct(new SampleDataItemComparer());  
    }  
    ```  
  
     <span data-ttu-id="b0ac8-169">Inoltre, in SampleDataSource.cs viene definita una classe denominata ExtensionMethods.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-169">Also in SampleDataSource.cs a class called ExtensionMethods is defined.</span></span> <span data-ttu-id="b0ac8-170">Ognuno di questi metodi di estensione usa il modello TAP per consentire a SampleDataSource di eseguire una query OData senza bloccare l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-170">Each of these extension methods uses the TAP pattern to allow the SampleDataSource to execute an OData query without blocking the UI.</span></span> <span data-ttu-id="b0ac8-171">Ad esempio, il seguente codice usa il metodo Task.Factory.FromAsync per implementare TAP.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-171">For example, the following code uses the Task.Factory.FromAsync method to implement TAP.</span></span>  
  
    ```csharp  
    public static async Task<IEnumerable<T>> ExecuteAsync<T>(this DataServiceQuery<T> query)  
    {  
        return await Task.Factory.FromAsync<IEnumerable<T>>(query.BeginExecute(null, null), query.EndExecute);  
    }  
    ```  
  
     <span data-ttu-id="b0ac8-172">Come nell'applicazione predefinita, la pagina principale dell'applicazione è GroupedItemsPage.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-172">As in the default application, the main page of the application is GroupedItemsPage.</span></span> <span data-ttu-id="b0ac8-173">Questa volta, tuttavia, visualizza i film recuperati da Netflix raggruppati per genere.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-173">This time, however, it displays the movies retrieved from Netflix grouped by genre.</span></span>  <span data-ttu-id="b0ac8-174">Quando viene creata un'istanza di GroupedItemsPage, viene chiamato il relativo metodo LoadState.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-174">When the GroupedItemsPage is instantiated, its LoadState method is called.</span></span> <span data-ttu-id="b0ac8-175">LoadState determina la creazione dell'istanza di SampleDataSource statica, eseguendo una chiamata al servizio Netflix OData come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-175">LoadState causes the static SampleDataSource instance to be created, making a call to the Netflix OData service as discussed previously.</span></span> <span data-ttu-id="b0ac8-176">LoadState archivia la raccolta di genere (oggetti SampleDataGroup) in DefaultViewModel:</span><span class="sxs-lookup"><span data-stu-id="b0ac8-176">LoadState stores the collection of genres (SampleDataGroup objects) in the DefaultViewModel:</span></span>  
  
    ```csharp  
    protected override void LoadState(Object navigationParameter, Dictionary<String, Object> pageState)  
    {  
  
        var sampleDataGroups = SampleDataSource.GetGroups((String)navigationParameter);  
        this.DefaultViewModel["Groups"] = sampleDataGroups;  
    }  
    ```  
  
     <span data-ttu-id="b0ac8-177">Come descritto in precedenza, l'oggetto DefaultViewModel viene quindi usato per associare i dati a GridView.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-177">As described previously, the DefaultViewModel is then used to bind the data to the GridView.</span></span>  
  
#### <a name="add-a-search-contract-to-allow-the-application-to-participate-in-windows-search"></a><span data-ttu-id="b0ac8-178">Aggiungere un contratto di ricerca per consentire all'applicazione di partecipare alla ricerca di Windows</span><span class="sxs-lookup"><span data-stu-id="b0ac8-178">Add a search contract to allow the application to participate in Windows search</span></span>  
  
1.  <span data-ttu-id="b0ac8-179">Aggiungere un contratto di ricerca all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-179">Add a search contract to the application.</span></span> <span data-ttu-id="b0ac8-180">Ciò consente all'applicazione di integrarsi con l'esperienza di ricerca di Windows 8.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-180">This allows the application to integrate with the Windows 8 search experience.</span></span> <span data-ttu-id="b0ac8-181">Denominare il contratto di ricerca SearchResultsPage.xaml</span><span class="sxs-lookup"><span data-stu-id="b0ac8-181">Name the search contract SearchResultsPage.xaml</span></span>  
  
     <span data-ttu-id="b0ac8-182">![Aggiungere un contratto ricerca](../../../../docs/framework/data/wcf/media/addsearchcontract.png "AddSearchContract")</span><span class="sxs-lookup"><span data-stu-id="b0ac8-182">![Add a search contract](../../../../docs/framework/data/wcf/media/addsearchcontract.png "AddSearchContract")</span></span>  
  
2.  <span data-ttu-id="b0ac8-183">Modificare la riga 58 di SearchResultsPage.xaml.cs rimuovendo le virgolette incorporate in queryText.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-183">Modify line 58 of SearchResultsPage.xaml.cs by removing the embedded quotes around queryText.</span></span>  
  
    ```csharp  
    // Communicate results through the view model  
    this.DefaultViewModel["QueryText"] = queryText;  
    this.DefaultViewModel["Filters"] = filterList;  
    this.DefaultViewModel["ShowFilters"] = filterList.Count > 1;  
    ```  
  
3.  <span data-ttu-id="b0ac8-184">Inserire le due righe di codice seguenti nella riga 81 in SearchResultsPage.xaml.cs per recuperare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-184">Insert the following two lines of code at line 81 in SearchResultsPage.xaml.cs to retrieve the search results.</span></span>  
  
    ```csharp  
    // TODO: Respond to the change in active filter by setting this.DefaultViewModel["Results"]  
                    //       to a collection of items with bindable Image, Title, Subtitle, and Description properties  
                    var searchValue = (string)this.DefaultViewModel["QueryText"];  
                    this.DefaultViewModel["Results"] = new List<SampleDataItem>(SampleDataSource.Search(searchValue));  
    ```  
  
 <span data-ttu-id="b0ac8-185">Quando un utente richiama la ricerca di Windows, digita un termine di ricerca e tocca l'icona dell'applicazione Netflix Demo nella barra di ricerca, viene eseguito il metodo LoadState di SearchResultsPage.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-185">When a user invokes Windows search, types in a search term and then touches the Netflix Demo app icon in the search bar, the LoadState method of the SearchResultsPage is executed.</span></span> <span data-ttu-id="b0ac8-186">Il parametro di navigazione inviato a LoadState contiene il testo della query.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-186">The navigation parameter sent to LoadState contains the query text.</span></span> <span data-ttu-id="b0ac8-187">Successivamente viene chiamato il metodo Filter_SelectionChanged che a sua volta chiama il metodo Search nella classe SampleDataSource.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-187">Next the Filter_SelectionChanged method is called which then calls the Search method on the SampleDataSource class.</span></span> <span data-ttu-id="b0ac8-188">I risultati vengono restituiti e visualizzati nella pagina SearchResultsPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-188">The results are returned and displayed in the SearchResultsPage.xaml page.</span></span>  
  
```csharp  
/// <summary>  
        /// Invoked when a filter is selected using the ComboBox in snapped view state.  
        /// </summary>  
        /// <param name="sender">The ComboBox instance.</param>  
        /// <param name="e">Event data describing how the selected filter was changed.</param>  
        void Filter_SelectionChanged(object sender, SelectionChangedEventArgs e)  
        {  
            // Determine what filter was selected  
            var selectedFilter = e.AddedItems.FirstOrDefault() as Filter;  
            if (selectedFilter != null)  
            {  
                // Mirror the results into the corresponding Filter object to allow the  
                // RadioButton representation used when not snapped to reflect the change  
                selectedFilter.Active = true;  
  
                // TODO: Respond to the change in active filter by setting this.DefaultViewModel["Results"]  
                //       to a collection of items with bindable Image, Title, Subtitle, and Description properties  
                var searchValue = (string)this.DefaultViewModel["QueryText"];  
                this.DefaultViewModel["Results"] = new List<SampleDataItem>(SampleDataSource.Search(searchValue));  
  
                // Ensure results are found  
                object results;  
                ICollection resultsCollection;  
                if (this.DefaultViewModel.TryGetValue("Results", out results) &&  
                    (resultsCollection = results as ICollection) != null &&  
                    resultsCollection.Count != 0)  
                {  
                    VisualStateManager.GoToState(this, "ResultsFound", true);  
                    return;  
                }  
            }  
  
            // Display informational text when there are no search results.  
            VisualStateManager.GoToState(this, "NoResultsFound", true);  
        }  
```  
  
 <span data-ttu-id="b0ac8-189">Per ulteriori informazioni sull'integrazione della ricerca in un'applicazione, vedere [ricerca: integrare l'esperienza di ricerca di Windows 8](http://go.microsoft.com/fwlink/p/?LinkId=266650).</span><span class="sxs-lookup"><span data-stu-id="b0ac8-189">For more information on integrating search into an application see, [Search: integrating into the Windows 8 search experience](http://go.microsoft.com/fwlink/p/?LinkId=266650).</span></span>  
  
## <a name="run-the-application"></a><span data-ttu-id="b0ac8-190">Esecuzione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="b0ac8-190">Run the application</span></span>  
 <span data-ttu-id="b0ac8-191">Avviare l'applicazione premendo F5.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-191">Launch the application by pressing F5.</span></span> <span data-ttu-id="b0ac8-192">Si noti che verranno richiesti alcuni secondi per caricare le immagini all'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-192">Note that it will take a few seconds to load the images upon application launch.</span></span> <span data-ttu-id="b0ac8-193">Inoltre, il primo tentativo di ricerca potrebbe non restituire alcun risultato.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-193">Also, your first search attempt may not return any results.</span></span> <span data-ttu-id="b0ac8-194">In un'applicazione reale, è consigliabile risolvere entrambi questi problemi.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-194">In a real-world application, you would want to deal with both of these issues.</span></span>  
  
 <span data-ttu-id="b0ac8-195">L'applicazione chiama il servizio Netflix OData, riceve i dati delle di classi OData generate e li trasferisce a classi di dati collegabili (SampleDataSource, SampleDataGroup e SampleDataItem).</span><span class="sxs-lookup"><span data-stu-id="b0ac8-195">The application calls the Netflix OData service, receives the data in the generated OData client classes and then transfers that data to bindable data classes (SampleDataSource, SampleDataGroup, and SampleDataItem).</span></span> <span data-ttu-id="b0ac8-196">Usa queste classi collegabili per associare i dati a GridView.</span><span class="sxs-lookup"><span data-stu-id="b0ac8-196">It uses these bindable classes to bind the data to the GridView.</span></span> <span data-ttu-id="b0ac8-197">Se non si ha familiarità con il funzionamento dell'associazione dati XAML, vedere [come raggruppare elementi in un elenco o una griglia (app di Windows Store scritte in c# /Visual Basic/C++ e XAML)](http://msdn.microsoft.com/library/windows/apps/xaml/hh780627).</span><span class="sxs-lookup"><span data-stu-id="b0ac8-197">If you are unfamiliar with how XAML databinding works see [How to group items in a list or grid (Windows Store apps using C#/VB/C++ and XAML)](http://msdn.microsoft.com/library/windows/apps/xaml/hh780627).</span></span>
