---
title: Codice sorgente di L2DBForm.xaml
ms.date: 10/22/2019
ms.topic: sample
ms.openlocfilehash: 290b00e136f0c49e1b27d4fa1bca7321eebe936e
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920944"
---
# <a name="l2dbformxaml-source-code"></a><span data-ttu-id="24916-102">Codice sorgente di L2DBForm.xaml</span><span class="sxs-lookup"><span data-stu-id="24916-102">L2DBForm.xaml source code</span></span>

<span data-ttu-id="24916-103">Questa pagina contiene e descrive il file di origine XAML per [WPF Data Binding usando LINQ to XML esempio](linq-to-xml-data-binding-sample.md).</span><span class="sxs-lookup"><span data-stu-id="24916-103">This page contains and describes the XAML source file for the [WPF data binding using LINQ to XML example](linq-to-xml-data-binding-sample.md).</span></span>

## <a name="overall-ui-structure"></a><span data-ttu-id="24916-104">Struttura complessiva dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="24916-104">Overall UI structure</span></span>

<span data-ttu-id="24916-105">Come è tipico per un progetto WPF, questo file contiene un elemento padre, un <xref:System.Windows.Window> elemento XML associato alla classe derivata `L2XDBFrom` nello spazio dei nomi `LinqToXmlDataBinding`.</span><span class="sxs-lookup"><span data-stu-id="24916-105">As is typical for a WPF project, this file contains one parent element, a <xref:System.Windows.Window> XML element that's associated with the derived class `L2XDBFrom` in the `LinqToXmlDataBinding` namespace.</span></span>

<span data-ttu-id="24916-106">L'area client è contenuta all'interno di una <xref:System.Windows.Controls.StackPanel> a cui è stato assegnato uno sfondo blu chiaro.</span><span class="sxs-lookup"><span data-stu-id="24916-106">The client area is contained within a <xref:System.Windows.Controls.StackPanel> that's given a light blue background.</span></span> <span data-ttu-id="24916-107">Il pannello contiene quattro sezioni dell'interfaccia utente <xref:System.Windows.Controls.DockPanel> separate da barre <xref:System.Windows.Controls.Separator> .</span><span class="sxs-lookup"><span data-stu-id="24916-107">This panel contains four <xref:System.Windows.Controls.DockPanel> UI sections separated by <xref:System.Windows.Controls.Separator> bars.</span></span> <span data-ttu-id="24916-108">Lo scopo di queste sezioni è descritto di [seguito](linq-to-xml-data-binding-sample.md#overview).</span><span class="sxs-lookup"><span data-stu-id="24916-108">The purpose of these sections is described [here](linq-to-xml-data-binding-sample.md#overview).</span></span>

<span data-ttu-id="24916-109">Ogni sezione contiene un'etichetta che la identifica.</span><span class="sxs-lookup"><span data-stu-id="24916-109">Each section contains a label that identifies it.</span></span> <span data-ttu-id="24916-110">Nelle prime due sezioni questa etichetta viene ruotata di 90 gradi tramite l'uso di un oggetto <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.</span><span class="sxs-lookup"><span data-stu-id="24916-110">In the first two sections, this label is rotated 90 degrees through the use of a <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.</span></span> <span data-ttu-id="24916-111">Il resto della sezione contiene gli elementi dell'interfaccia utente appropriati allo scopo di tale sezione, ad esempio blocchi di testo, caselle di testo e pulsanti.</span><span class="sxs-lookup"><span data-stu-id="24916-111">The rest of the section contains UI elements appropriate to the purpose of that section, for example, text blocks, text boxes, and buttons.</span></span> <span data-ttu-id="24916-112">A volte viene usato un elemento figlio <xref:System.Windows.Controls.StackPanel> per allineare questi controlli figlio.</span><span class="sxs-lookup"><span data-stu-id="24916-112">Sometimes a child <xref:System.Windows.Controls.StackPanel> is used to align these child controls.</span></span>

## <a name="window-resource-section"></a><span data-ttu-id="24916-113">Sezione delle risorse della finestra</span><span class="sxs-lookup"><span data-stu-id="24916-113">Window resource section</span></span>

<span data-ttu-id="24916-114">Il tag di apertura di `<Window.Resources>` alla riga 9 indica l'inizio della sezione relativa alle risorse della finestra,</span><span class="sxs-lookup"><span data-stu-id="24916-114">The opening `<Window.Resources>` tag on line 9 indicates the start of the window resource section.</span></span> <span data-ttu-id="24916-115">che termina con il tag di chiusura alla riga 35.</span><span class="sxs-lookup"><span data-stu-id="24916-115">It ends with the closing tag on line 35.</span></span>

<span data-ttu-id="24916-116">Il tag `<ObjectDataProvider>` , che si estende dalla riga 11 alla riga 25, dichiara un oggetto <xref:System.Windows.Data.ObjectDataProvider>, denominato `LoadedBooks`, che usa <xref:System.Xml.Linq.XElement> come origine.</span><span class="sxs-lookup"><span data-stu-id="24916-116">The `<ObjectDataProvider>` tag, which spans lines 11 through 25, declares a <xref:System.Windows.Data.ObjectDataProvider>, named `LoadedBooks`, that uses an <xref:System.Xml.Linq.XElement> as the source.</span></span> <span data-ttu-id="24916-117"><xref:System.Xml.Linq.XElement> viene inizializzato tramite l'analisi di un documento XML incorporato (elemento `CDATA`).</span><span class="sxs-lookup"><span data-stu-id="24916-117">The <xref:System.Xml.Linq.XElement> is initialized by parsing an embedded XML document (a `CDATA` element).</span></span> <span data-ttu-id="24916-118">Si noti che lo spazio vuoto viene mantenuto quando si dichiara il documento XML incorporato e anche quando viene analizzato.</span><span class="sxs-lookup"><span data-stu-id="24916-118">Notice that white space is preserved when declaring the embedded XML document and also when it's parsed.</span></span> <span data-ttu-id="24916-119">in quanto il controllo <xref:System.Windows.Controls.TextBlock>, usato per visualizzare l'XML non elaborato, non include funzionalità speciali di formattazione XML.</span><span class="sxs-lookup"><span data-stu-id="24916-119">White space is preserved because the <xref:System.Windows.Controls.TextBlock> control, which is used to display the raw XML, has no special XML formatting capabilities.</span></span>

<span data-ttu-id="24916-120">Infine, viene definito un oggetto <xref:System.Windows.DataTemplate> denominato `BookTemplate` dalla riga 28 alla riga 34.</span><span class="sxs-lookup"><span data-stu-id="24916-120">Lastly, a <xref:System.Windows.DataTemplate> named `BookTemplate` is defined on lines 28 through 34.</span></span> <span data-ttu-id="24916-121">Questo modello viene usato per visualizzare le voci nella sezione dell'interfaccia utente **Book List**.</span><span class="sxs-lookup"><span data-stu-id="24916-121">This template is used to display the entries in the **Book List** UI section.</span></span> <span data-ttu-id="24916-122">Vengono usate l'associazione dati e le proprietà dinamiche di LINQ to XML per recuperare l'ID e il nome libro tramite le seguenti assegnazioni:</span><span class="sxs-lookup"><span data-stu-id="24916-122">It uses data binding and LINQ to XML dynamic properties to retrieve the book ID and book name through the following assignments:</span></span>

```xaml
Text="{Binding Path=Attribute[id].Value}"Text="{Binding Path=Value}"
```

## <a name="data-binding-code"></a><span data-ttu-id="24916-123">Codice di associazione dati</span><span class="sxs-lookup"><span data-stu-id="24916-123">Data binding code</span></span>

<span data-ttu-id="24916-124">Oltre che nell'elemento <xref:System.Windows.DataTemplate> , l'associazione dati viene usata in diverse altre sezioni del file.</span><span class="sxs-lookup"><span data-stu-id="24916-124">In addition to the <xref:System.Windows.DataTemplate> element, data binding is used in a number of other places in this file.</span></span>

<span data-ttu-id="24916-125">Nel tag di apertura di `<StackPanel>` , alla riga 38, la proprietà <xref:System.Windows.FrameworkElement.DataContext%2A> di questo pannello è impostata sul provider di dati `LoadedBooks` .</span><span class="sxs-lookup"><span data-stu-id="24916-125">In the opening `<StackPanel>` tag on line 38, the <xref:System.Windows.FrameworkElement.DataContext%2A> property of this panel is set to the `LoadedBooks` data provider.</span></span>

```xaml
DataContext="{Binding Source={StaticResource LoadedBooks}}
```

<span data-ttu-id="24916-126">L'impostazione del contesto di dati consente (alla riga 46) all'oggetto <xref:System.Windows.Controls.TextBlock> denominato `tbRawXml` di visualizzare l'XML non elaborato tramite l'associazione alla proprietà `Xml` di questo provider di dati:</span><span class="sxs-lookup"><span data-stu-id="24916-126">Setting the data context makes it possible (on line 46) for the <xref:System.Windows.Controls.TextBlock> named `tbRawXml` to display the raw XML by binding to this data provider's `Xml` property:</span></span>

```xaml
Text="{Binding Path=Xml}"
```

<span data-ttu-id="24916-127">L'oggetto <xref:System.Windows.Controls.ListBox> nella sezione dell'interfaccia utente **Book List** , dalla riga 58 alla riga 62, imposta il modello per i relativi elementi visualizzati sull'oggetto `BookTemplate` definito nella sezione delle risorse della finestra:</span><span class="sxs-lookup"><span data-stu-id="24916-127">The <xref:System.Windows.Controls.ListBox> in the **Book List** UI section, on lines 58 through 62, sets the template for its display items to the `BookTemplate` defined in the window resource section:</span></span>

```xaml
ItemTemplate ="{StaticResource BookTemplate}"
```

<span data-ttu-id="24916-128">Quindi, dalla riga 59 alla riga 62, i valori effettivi dei libri vengono associati a questa casella di riepilogo:</span><span class="sxs-lookup"><span data-stu-id="24916-128">Then, on lines 59 through 62, the actual values of the books are bound to this list box:</span></span>

```xaml
<ListBox.ItemsSource>
    <Binding Path="Elements[{http://www.mybooks.com}book]"/>
</ListBox.ItemsSource>
```

<span data-ttu-id="24916-129">La terza sezione dell'interfaccia utente, **Edit Selected Book**, associa l'oggetto <xref:System.Windows.FrameworkElement.DataContext%2A> dell'oggetto <xref:System.Windows.Controls.StackPanel> padre all'elemento attualmente selezionato della sezione dell'interfaccia utente **Book List** (riga 82):</span><span class="sxs-lookup"><span data-stu-id="24916-129">The third UI section, **Edit Selected Book**, first binds the <xref:System.Windows.FrameworkElement.DataContext%2A> of the parent <xref:System.Windows.Controls.StackPanel> to the currently selected item in from the **Book List** UI section (line 82):</span></span>

```xaml
DataContext="{Binding ElementName=lbBooks, Path=SelectedItem}"
```

<span data-ttu-id="24916-130">Usa quindi l'associazione dati bidirezionale, in modo che i valori correnti degli elementi libro vengano visualizzati e aggiornati dalle due caselle di testo di questo pannello.</span><span class="sxs-lookup"><span data-stu-id="24916-130">It then uses two-way data binding, so that the current values of the book elements are displayed to, and updated from, the two text boxes in this panel.</span></span> <span data-ttu-id="24916-131">L'associazione dati a proprietà dinamiche è simile a quella usata nel modello di dati `BookTemplate`:</span><span class="sxs-lookup"><span data-stu-id="24916-131">Data binding to dynamic properties is similar to the data binding used in the `BookTemplate` data template:</span></span>

```xaml
Text="{Binding Path=Attribute[id].Value}"...Text="{Binding Path=Value}"
```

<span data-ttu-id="24916-132">L'ultima sezione dell'interfaccia utente, **Add New Book**, non usa l'associazione dati nel codice XAML,</span><span class="sxs-lookup"><span data-stu-id="24916-132">The last UI section, **Add New Book**, doesn't use data binding in its XAML code.</span></span> <span data-ttu-id="24916-133">ma l'associazione dati è invece disponibile nel codice di gestione degli eventi nel file *L2DBForm.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="24916-133">Instead, data binding is in its event handling code in the file *L2DBForm.xaml.cs*.</span></span>

## <a name="example"></a><span data-ttu-id="24916-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="24916-134">Example</span></span>

### <a name="description"></a><span data-ttu-id="24916-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24916-135">Description</span></span>

> [!NOTE]
> <span data-ttu-id="24916-136">Si consiglia di copiare il codice seguente in un editor di codice, ad esempio l'editor di codice sorgente C# in Visual Studio, in modo che sia più facile tenere traccia dei numeri di riga.</span><span class="sxs-lookup"><span data-stu-id="24916-136">We recommend that you copy the following code below into a code editor, such as the C# source code editor in Visual Studio, so that line numbers will be easier to track.</span></span>

### <a name="code"></a><span data-ttu-id="24916-137">Codice</span><span class="sxs-lookup"><span data-stu-id="24916-137">Code</span></span>

```xml
<Window x:Class="LinqToXmlDataBinding.L2XDBForm"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:system="clr-namespace:System;assembly=mscorlib"
    xmlns:xlinq="clr-namespace:System.Xml.Linq;assembly=System.Xml.Linq"
    xmlns:local="clr-namespace:LinqToXmlDataBinding"
    Title="WPF Data Binding using LINQ-to-XML" Height="665" Width="500" ResizeMode="NoResize">

    <Window.Resources>
        <!-- Books provider and inline data -->
        <ObjectDataProvider x:Key="LoadedBooks" ObjectType="{x:Type xlinq:XElement}" MethodName="Parse">
            <ObjectDataProvider.MethodParameters>
                <system:String xml:space="preserve">
<![CDATA[
<books xmlns="http://www.mybooks.com">
  <book id="0">book zero</book>
  <book id="1">book one</book>
  <book id="2">book two</book>
  <book id="3">book three</book>
</books>
]]>
                </system:String>
                <xlinq:LoadOptions>PreserveWhitespace</xlinq:LoadOptions>
            </ObjectDataProvider.MethodParameters>
        </ObjectDataProvider>

        <!-- Template for use in Books List listbox. -->
        <DataTemplate x:Key="BookTemplate">
            <StackPanel Orientation="Horizontal">
                <TextBlock Margin="3" Text="{Binding Path=Attribute[id].Value}"/>
                <TextBlock Margin="3" Text="-"/>
                <TextBlock Margin="3" Text="{Binding Path=Value}"/>
            </StackPanel>
        </DataTemplate>
    </Window.Resources>

    <!-- Main visual content container -->
    <StackPanel Background="lightblue" DataContext="{Binding Source={StaticResource LoadedBooks}}">
        <!-- Raw XML display section -->
        <DockPanel Margin="5">
            <Label  Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" FontWeight="Bold">XML
            <Label.LayoutTransform>
                <RotateTransform Angle="90"/>
            </Label.LayoutTransform>
            </Label>
            <TextBlock Name="tbRawXml" Height="200" Background="LightGray" Text="{Binding Path=Xml}" TextTrimming="CharacterEllipsis" />
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- List box to display all books section -->
        <DockPanel Margin="5">
            <Label  Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" FontWeight="Bold">Book List
                <Label.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </Label.LayoutTransform>
            </Label>
            <ListBox Name="lbBooks" Height="200" Width="415" ItemTemplate ="{StaticResource BookTemplate}">
                <ListBox.ItemsSource>
                    <Binding Path="Elements[{http://www.mybooks.com}book]"/>
                </ListBox.ItemsSource>
            </ListBox>
            <Button Margin="5" DockPanel.Dock="Right" Height="30" Width ="130" Content="Remove Selected Book" Click="OnRemoveBook">
            <Button.LayoutTransform>
                <RotateTransform Angle="90"/>
            </Button.LayoutTransform>
            </Button>
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- Edit current selection section -->
        <DockPanel Margin="5">
            <TextBlock Margin="5" Height="30" Width="65" DockPanel.Dock="Right" Background="LightGray" TextWrapping="Wrap" TextAlignment="Center">
                    Changes are live!
                <TextBlock.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </TextBlock.LayoutTransform>
            </TextBlock>
            <StackPanel>
                <Label Width="450" Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" FontWeight="Bold">Edit Selected Book</Label>
                <StackPanel Margin="1" DataContext="{Binding ElementName=lbBooks, Path=SelectedItem}">
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">ID:</Label>
                        <TextBox Name="editAttributeTextBox" Width="410" Text="{Binding Path=Attribute[id].Value}">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Edit the selected book ID and see it changed.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">Value:</Label>
                        <TextBox Name="editValueTextBox" Width="410" Text="{Binding Path=Value}" Height="25">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Edit the selected book Value and see it changed.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                </StackPanel>
            </StackPanel>
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- Add new book section -->
        <DockPanel Margin="5">
            <Button Margin="5" Height="30" DockPanel.Dock="Right" Click ="OnAddBook">Add Book
                <Button.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </Button.LayoutTransform>
            </Button>
            <StackPanel>
                <Label Width="450" Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" FontWeight="Bold">Add New Book</Label>
                <StackPanel Margin="1">
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">ID:</Label>
                        <TextBox Name="tbAddID" Width="410">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Enter a book ID and Value pair, then click Add Book.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">Value:</Label>
                        <TextBox Name="tbAddValue" Width="410" Height="25">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="UltraBold" TextAlignment="Center">
                                    <Label>Enter a book ID and Value pair, then click Add Book.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                </StackPanel>
            </StackPanel>
        </DockPanel>
    </StackPanel>
</Window>
```

### <a name="comments"></a><span data-ttu-id="24916-138">Comments</span><span class="sxs-lookup"><span data-stu-id="24916-138">Comments</span></span>

<span data-ttu-id="24916-139">Per il codice sorgente C# relativo ai gestori eventi associati agli elementi dell'interfaccia utente WPF, vedere [L2DBForm.xaml.cs Source Code](l2dbform-xaml-cs-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="24916-139">For the C# source code for the event handlers associated with the WPF UI elements, see [L2DBForm.xaml.cs source code](l2dbform-xaml-cs-source-code.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="24916-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24916-140">See also</span></span>

- [<span data-ttu-id="24916-141">Procedura dettagliata: Esempio LinqToXmlDataBinding</span><span class="sxs-lookup"><span data-stu-id="24916-141">Walkthrough: LinqToXmlDataBinding example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="24916-142">Codice sorgente di L2DBForm.xaml.cs</span><span class="sxs-lookup"><span data-stu-id="24916-142">L2DBForm.xaml.cs source code</span></span>](l2dbform-xaml-cs-source-code.md)
