---
title: 'Procedura: Aggiungere dettagli di riga a un controllo DataGrid'
description: Informazioni su come personalizzare la presentazione dei dati quando si usa il controllo DataGrid Windows Presentation Foundation aggiungendo una sezione dettagli riga.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: 8fd6b07f454681a0eed70d7a6208cfcc426dc920
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164946"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a><span data-ttu-id="a4126-103">Procedura: Aggiungere dettagli di riga a un controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="a4126-103">How to: Add Row Details to a DataGrid Control</span></span>
<span data-ttu-id="a4126-104">Quando si usa il <xref:System.Windows.Controls.DataGrid> controllo, è possibile personalizzare la presentazione dei dati aggiungendo una sezione dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="a4126-104">When using the <xref:System.Windows.Controls.DataGrid> control, you can customize the data presentation by adding a row details section.</span></span> <span data-ttu-id="a4126-105">L'aggiunta di una sezione dettagli riga consente di raggruppare alcuni dati in un modello che è facoltativamente visibile o compresso.</span><span class="sxs-lookup"><span data-stu-id="a4126-105">Adding a row details section enables you to group some data in a template that is optionally visible or collapsed.</span></span> <span data-ttu-id="a4126-106">Ad esempio, è possibile aggiungere dettagli di riga a un oggetto <xref:System.Windows.Controls.DataGrid> che presenta solo un riepilogo dei dati per ogni riga in <xref:System.Windows.Controls.DataGrid> , ma presenta più campi dati quando l'utente seleziona una riga.</span><span class="sxs-lookup"><span data-stu-id="a4126-106">For example, you can add row details to a <xref:System.Windows.Controls.DataGrid> that presents only a summary of the data for each row in the <xref:System.Windows.Controls.DataGrid>, but presents more data fields when the user selects a row.</span></span> <span data-ttu-id="a4126-107">Definire il modello per la sezione dettagli riga della <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="a4126-107">You define the template for the row details section in the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property.</span></span> <span data-ttu-id="a4126-108">Nella figura seguente viene illustrato un esempio di sezione dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="a4126-108">The following illustration shows an example of a row details section.</span></span>  
  
 <span data-ttu-id="a4126-109">![DataGrid con i dettagli della riga](./media/ndp-rowdetails.png "NDP_RowDetails")</span><span class="sxs-lookup"><span data-stu-id="a4126-109">![DataGrid shown with row details](./media/ndp-rowdetails.png "NDP_RowDetails")</span></span>  
  
 <span data-ttu-id="a4126-110">Il modello di dettagli della riga viene definito come XAML inline o come risorsa.</span><span class="sxs-lookup"><span data-stu-id="a4126-110">You define the row details template as either inline XAML or as a resource.</span></span> <span data-ttu-id="a4126-111">Entrambi gli approcci sono illustrati nelle procedure riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="a4126-111">Both approaches are shown in the following procedures.</span></span> <span data-ttu-id="a4126-112">Un modello di dati aggiunto come risorsa può essere usato in tutto il progetto senza dover ricreare il modello.</span><span class="sxs-lookup"><span data-stu-id="a4126-112">A data template that is added as a resource can be used throughout the project without re-creating the template.</span></span> <span data-ttu-id="a4126-113">Un modello di dati aggiunto come XAML inline è accessibile solo dal controllo in cui è definito.</span><span class="sxs-lookup"><span data-stu-id="a4126-113">A data template that is added as inline XAML is only accessible from the control where it is defined.</span></span>  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a><span data-ttu-id="a4126-114">Per visualizzare i dettagli delle righe utilizzando XAML inline</span><span class="sxs-lookup"><span data-stu-id="a4126-114">To display row details by using inline XAML</span></span>  
  
1. <span data-ttu-id="a4126-115">Creare un oggetto <xref:System.Windows.Controls.DataGrid> che Visualizza i dati da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="a4126-115">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="a4126-116">Nell'elemento <xref:System.Windows.Controls.DataGrid> aggiungere un elemento <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="a4126-116">In the <xref:System.Windows.Controls.DataGrid> element, add a <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> element.</span></span>  
  
3. <span data-ttu-id="a4126-117">Creare un oggetto <xref:System.Windows.DataTemplate> che definisce l'aspetto della sezione dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="a4126-117">Create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="a4126-118">Nel codice XAML riportato di seguito vengono illustrati <xref:System.Windows.Controls.DataGrid> e come definire l'oggetto <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline.</span><span class="sxs-lookup"><span data-stu-id="a4126-118">The following XAML shows the <xref:System.Windows.Controls.DataGrid> and how to define the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline.</span></span> <span data-ttu-id="a4126-119">Il <xref:System.Windows.Controls.DataGrid> Visualizza tre valori in ogni riga e altri tre valori quando la riga è selezionata.</span><span class="sxs-lookup"><span data-stu-id="a4126-119">The <xref:System.Windows.Controls.DataGrid> displays three values in each row and three more values when the row is selected.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     <span data-ttu-id="a4126-120">Nel codice seguente viene illustrata la query utilizzata per selezionare i dati visualizzati in <xref:System.Windows.Controls.DataGrid> .</span><span class="sxs-lookup"><span data-stu-id="a4126-120">The following code shows the query that is used to select the data that is displayed in the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="a4126-121">In questo esempio la query seleziona i dati da un'entità che contiene informazioni sul cliente.</span><span class="sxs-lookup"><span data-stu-id="a4126-121">In this example, the query selects data from an entity that contains customer information.</span></span>  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a><span data-ttu-id="a4126-122">Per visualizzare i dettagli delle righe utilizzando una risorsa</span><span class="sxs-lookup"><span data-stu-id="a4126-122">To display row details by using a resource</span></span>  
  
1. <span data-ttu-id="a4126-123">Creare un oggetto <xref:System.Windows.Controls.DataGrid> che Visualizza i dati da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="a4126-123">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="a4126-124">Aggiungere un <xref:System.Windows.FrameworkElement.Resources%2A> elemento all'elemento radice, ad esempio un <xref:System.Windows.Window> controllo o un <xref:System.Windows.Controls.Page> controllo, o aggiungere un <xref:System.Windows.Application.Resources%2A> elemento alla <xref:System.Windows.Application> classe nel file app. XAML (o Application. Xaml).</span><span class="sxs-lookup"><span data-stu-id="a4126-124">Add a <xref:System.Windows.FrameworkElement.Resources%2A> element to the root element, such as a <xref:System.Windows.Window> control or a <xref:System.Windows.Controls.Page> control, or add a <xref:System.Windows.Application.Resources%2A> element to the <xref:System.Windows.Application> class in the App.xaml (or Application.xaml) file.</span></span>  
  
3. <span data-ttu-id="a4126-125">Nell'elemento resources creare un oggetto <xref:System.Windows.DataTemplate> che definisce l'aspetto della sezione dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="a4126-125">In the resources element, create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="a4126-126">Nel codice XAML seguente viene illustrato il <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> definito nella <xref:System.Windows.Application> classe.</span><span class="sxs-lookup"><span data-stu-id="a4126-126">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> defined in the <xref:System.Windows.Application> class.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. <span data-ttu-id="a4126-127">In <xref:System.Windows.DataTemplate> impostare la [direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) su un valore che identifichi in modo univoco il modello di dati.</span><span class="sxs-lookup"><span data-stu-id="a4126-127">On the <xref:System.Windows.DataTemplate>, set the [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md) to a value that uniquely identifies the data template.</span></span>  
  
5. <span data-ttu-id="a4126-128">Nell' <xref:System.Windows.Controls.DataGrid> elemento impostare la proprietà sulla <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> risorsa definita nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="a4126-128">In the <xref:System.Windows.Controls.DataGrid> element, set the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property to the resource defined in the previous steps.</span></span> <span data-ttu-id="a4126-129">Assegnare la risorsa come risorsa statica.</span><span class="sxs-lookup"><span data-stu-id="a4126-129">Assign the resource as a static resource.</span></span>  
  
     <span data-ttu-id="a4126-130">Il codice XAML seguente mostra la <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> proprietà impostata sulla risorsa dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="a4126-130">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property set to the resource from the previous example.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a><span data-ttu-id="a4126-131">Per impostare la visibilità ed evitare lo scorrimento orizzontale per i dettagli delle righe</span><span class="sxs-lookup"><span data-stu-id="a4126-131">To set visibility and prevent horizontal scrolling for row details</span></span>  
  
1. <span data-ttu-id="a4126-132">Se necessario, impostare la <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> proprietà su un <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> valore.</span><span class="sxs-lookup"><span data-stu-id="a4126-132">If needed, set the <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> property to a <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> value.</span></span>  
  
     <span data-ttu-id="a4126-133">Per impostazione predefinita, il valore è impostato su <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span><span class="sxs-lookup"><span data-stu-id="a4126-133">By default, the value is set to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span></span> <span data-ttu-id="a4126-134">È possibile impostarlo su <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> per visualizzare i dettagli di tutte le righe o <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> per nascondere i dettagli di tutte le righe.</span><span class="sxs-lookup"><span data-stu-id="a4126-134">You can set it to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> to show the details for all of the rows or <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> to hide the details for all rows.</span></span>  
  
2. <span data-ttu-id="a4126-135">Se necessario, impostare la <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> proprietà su `true` per impedire lo scorrimento orizzontale della sezione dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="a4126-135">If needed, set the <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> property to `true` to prevent the row details section from scrolling horizontally.</span></span>
