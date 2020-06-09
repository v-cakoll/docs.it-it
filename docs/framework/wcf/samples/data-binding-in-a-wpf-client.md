---
title: Associazione dati in un client Windows Presentation Foundation
ms.date: 03/30/2017
ms.assetid: bb8c8293-5973-4aef-9b07-afeff5d3293c
ms.openlocfilehash: fe7b1934fa2abfa8d2f812caca2363c1cc603d1a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602609"
---
# <a name="data-binding-in-a-windows-presentation-foundation-client"></a><span data-ttu-id="400ff-102">Associazione dati in un client Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="400ff-102">Data Binding in a Windows Presentation Foundation Client</span></span>
<span data-ttu-id="400ff-103">In questo esempio viene illustrato come usare un'associazione dati in un client Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="400ff-103">This sample demonstrates the use of data binding in a Windows Presentation Foundation (WPF) client.</span></span> <span data-ttu-id="400ff-104">Nell'esempio viene utilizzato un servizio Windows Communication Foundation (WCF) che genera in modo casuale una matrice di album da restituire al client.</span><span class="sxs-lookup"><span data-stu-id="400ff-104">The sample uses a Windows Communication Foundation (WCF) service that randomly generates an array of albums to return to the client.</span></span> <span data-ttu-id="400ff-105">Ogni album è dotato di un nome, di un prezzo e di un elenco di tracce.</span><span class="sxs-lookup"><span data-stu-id="400ff-105">Each album has a name, a price, and a list of album tracks.</span></span> <span data-ttu-id="400ff-106">Le tracce dell'album sono dotate di un nome e di una durata.</span><span class="sxs-lookup"><span data-stu-id="400ff-106">The album tracks have a name and duration.</span></span> <span data-ttu-id="400ff-107">Le informazioni restituite dal servizio vengono associate automaticamente all'interfaccia utente (UI) fornita dal client Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="400ff-107">The information that is returned by the service is automatically bound to the user interface (UI) provided by the Windows Presentation Foundation (WPF) client.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="400ff-108">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="400ff-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="400ff-109">L'associazione dati fa sì che un'origine dati venga associata automaticamente a un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="400ff-109">Data binding allows a data source to be automatically bound to a UI.</span></span> <span data-ttu-id="400ff-110">Questa operazione semplifica il modello di programmazione, perché non richiede che ogni elemento dell'interfaccia utente venga aggiornato a livello di programmazione con i dati da un oggetto dati o da una matrice di oggetti dati.</span><span class="sxs-lookup"><span data-stu-id="400ff-110">This simplifies the programming model because it does not require that you programmatically update each UI element with the data from a data object or an array of data objects.</span></span> <span data-ttu-id="400ff-111">È possibile associare un oggetto a un singolo elemento dell'interfaccia utente oppure una matrice a un controllo che accetta più input, ad esempio un oggetto `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="400ff-111">You can bind an object to a single UI element or an array to a control that takes multiple inputs, such as a `ListBox`.</span></span> <span data-ttu-id="400ff-112">Nell'esempio di codice seguente viene illustrato come associare i dati al `DataContext` di un elemento dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="400ff-112">The following code shows how to bind data to the `DataContext` of a UI element.</span></span>  
  
```csharp  
// Event handler executed when call is complete  
void client_GetAlbumListCompleted(object sender, GetAlbumListCompletedEventArgs e)  
{  
    // This is on the UI thread, myPanel can be accessed directly  
    myPanel.DataContext = e.Result;
}  
```  
  
 <span data-ttu-id="400ff-113">Nell'esempio precedente, il `DataContext` per l'elemento del layout `grid` denominato `myPanel` viene impostato sui dati restituiti dal metodo `GetAlbumList`.</span><span class="sxs-lookup"><span data-stu-id="400ff-113">In the previous sample, the `DataContext` for the `grid` layout element named `myPanel` is set to the data returned by the `GetAlbumList` method.</span></span> <span data-ttu-id="400ff-114">Il `DataContext` consente agli elementi di ereditare informazioni dagli elementi padre sull'origine dati usata per l'associazione e su altre caratteristiche dell'associazione, ad esempio il percorso.</span><span class="sxs-lookup"><span data-stu-id="400ff-114">The `DataContext` allows elements to inherit information from their parent elements about the data source that is used for binding, as well as other characteristics of the binding such as the path.</span></span> <span data-ttu-id="400ff-115">La riga di codice deve essere eseguita ogni volta che i dati nel server vengono aggiornati.</span><span class="sxs-lookup"><span data-stu-id="400ff-115">The line of code must be executed every time the data on the server is updated.</span></span> <span data-ttu-id="400ff-116">Ad esempio, viene eseguita quando viene avviata la finestra e quando viene aggiunto un nuovo album.</span><span class="sxs-lookup"><span data-stu-id="400ff-116">For example, it is executed when the window is initialized and when a new album is added.</span></span>  
  
 <span data-ttu-id="400ff-117">Nell'esempio di codice XAML seguente, il `ListBox` specifica `ItemsSource="{Binding }"`.</span><span class="sxs-lookup"><span data-stu-id="400ff-117">In the following sample XAML code, the `ListBox` specifies `ItemsSource="{Binding }"`.</span></span>  
  
```xml  
<ListBox
          ItemTemplate="{StaticResource AlbumStyle}"  
          ItemsSource="{Binding }"
          IsSynchronizedWithCurrentItem="true" />  
```  
  
 <span data-ttu-id="400ff-118">In questo modo specifica che i dati associati all'elemento dell'interfaccia utente di livello superiore venga associato anche a questo controllo (ovvero, la matrice di album).</span><span class="sxs-lookup"><span data-stu-id="400ff-118">This specifies that the data bound to the top-level UI element is also bound to this control (that is, the array of Albums).</span></span> <span data-ttu-id="400ff-119">`ItemTemplate="{StaticResource AlbumStyle}"`Specifica inoltre il modello di dati da utilizzare per ogni elemento in `ListBox` .</span><span class="sxs-lookup"><span data-stu-id="400ff-119">In addition, `ItemTemplate="{StaticResource AlbumStyle}"` specifies the data template to be used for each item in the `ListBox`.</span></span> <span data-ttu-id="400ff-120">È inoltre possibile definire modelli di dati per specificare come formattare i dati.</span><span class="sxs-lookup"><span data-stu-id="400ff-120">You can also define data templates to specify how the data should be formatted.</span></span> <span data-ttu-id="400ff-121">Questi modelli di dati possono essere riusati per altri elementi dell'interfaccia utente dell'applicazione. Il vantaggio è che il modello di dati viene definito e gestito in un solo posto.</span><span class="sxs-lookup"><span data-stu-id="400ff-121">These data templates can be reused for other UI elements in the application, the advantage is that the data template is defined and maintained in one place.</span></span>  
  
 <span data-ttu-id="400ff-122">Il modello di dati `AlbumStyle` crea una griglia con due `TextBlock`, uno accanto all'altro.</span><span class="sxs-lookup"><span data-stu-id="400ff-122">The `AlbumStyle` data template lays out a grid with two `TextBlock`s side by side.</span></span> <span data-ttu-id="400ff-123">Uno specifica il nome dell'album e l'altro il numero di tracce contenute nell'album.</span><span class="sxs-lookup"><span data-stu-id="400ff-123">One specifies the name of the Album and the other the number of Tracks in the album.</span></span>  
  
```xaml  
<DataTemplate x:Key="AlbumStyle">  
    <Grid>  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition Width="260" />  
            <ColumnDefinition Width="60" />  
        </Grid.ColumnDefinitions>  
        <TextBlock Grid.Column="0" TextContent="{Binding Path=Title}" />  
        <TextBlock Grid.Column="1" TextContent="{Binding Path=Tracks#.Count}" HorizontalAlignment="Right" />  
    </Grid>  
</DataTemplate>  
```  
  
 <span data-ttu-id="400ff-124">Il codice XAML seguente crea un secondo `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="400ff-124">The following XAML code creates a second `ListBox`.</span></span>  
  
```xaml  
<ListBox Grid.Row="2"
            Grid.ColumnSpan="2"
            ItemTemplate="{StaticResource TrackStyle}"  
            ItemsSource="{Binding Path=Tracks}" />  
```  
  
 <span data-ttu-id="400ff-125">Il codice specifica un percorso per `ItemsSource`.</span><span class="sxs-lookup"><span data-stu-id="400ff-125">The code specifies a path for the `ItemsSource`.</span></span> <span data-ttu-id="400ff-126">Questo indica che i dati associati a questo controllo non sono i dati di livello superiore, ma una proprietà dei dati di livello superiore denominata `Tracks`.</span><span class="sxs-lookup"><span data-stu-id="400ff-126">This indicates that the data bound to this control is not the top-level data but a property of the top-level data named `Tracks`.</span></span> <span data-ttu-id="400ff-127">Questa proprietà rappresenta la matrice di tracce contenute all'interno dell'album.</span><span class="sxs-lookup"><span data-stu-id="400ff-127">This property represents the array of tracks contained within the album.</span></span> <span data-ttu-id="400ff-128">Viene inoltre specificato un `DataTemplate` diverso, denominato `TrackStyle`.</span><span class="sxs-lookup"><span data-stu-id="400ff-128">In addition, a different `DataTemplate` named `TrackStyle` is specified.</span></span> <span data-ttu-id="400ff-129">Il layout del modello `TrackStyle` è simile a quello del modello `AlbumStyle`, ma i `TextBlock` sono associati a proprietà diverse.</span><span class="sxs-lookup"><span data-stu-id="400ff-129">The layout of the `TrackStyle` template is similar to that of the `AlbumStyle` template, but the `TextBlock`s are bound to different properties.</span></span> <span data-ttu-id="400ff-130">Questo succede perché i due modelli vengono usati con oggetti dati diversi.</span><span class="sxs-lookup"><span data-stu-id="400ff-130">This is because the two templates are used with different data objects.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="400ff-131">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="400ff-131">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="400ff-132">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="400ff-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="400ff-133">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="400ff-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="400ff-134">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="400ff-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="400ff-135">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="400ff-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="400ff-136">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="400ff-136">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="400ff-137">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="400ff-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="400ff-138">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="400ff-138">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WPFDataBinding`  
