---
title: 'Procedura: aggiungere dettagli di riga un controllo DataGrid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: 4db414e1907d42071f7251c390077d4020fa577c
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559677"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a><span data-ttu-id="6fef6-102">Procedura: aggiungere dettagli di riga un controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="6fef6-102">How to: Add Row Details to a DataGrid Control</span></span>
<span data-ttu-id="6fef6-103">Quando si usa il controllo <xref:System.Windows.Controls.DataGrid>, è possibile personalizzare la presentazione dei dati aggiungendo una sezione dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="6fef6-103">When using the <xref:System.Windows.Controls.DataGrid> control, you can customize the data presentation by adding a row details section.</span></span> <span data-ttu-id="6fef6-104">L'aggiunta di una sezione dettagli riga consente di raggruppare alcuni dati in un modello che è facoltativamente visibile o compresso.</span><span class="sxs-lookup"><span data-stu-id="6fef6-104">Adding a row details section enables you to group some data in a template that is optionally visible or collapsed.</span></span> <span data-ttu-id="6fef6-105">È ad esempio possibile aggiungere dettagli di riga a una <xref:System.Windows.Controls.DataGrid> che presenta solo un riepilogo dei dati per ogni riga del <xref:System.Windows.Controls.DataGrid>, ma presenta più campi dati quando l'utente seleziona una riga.</span><span class="sxs-lookup"><span data-stu-id="6fef6-105">For example, you can add row details to a <xref:System.Windows.Controls.DataGrid> that presents only a summary of the data for each row in the <xref:System.Windows.Controls.DataGrid>, but presents more data fields when the user selects a row.</span></span> <span data-ttu-id="6fef6-106">Definire il modello per la sezione dettagli riga nella proprietà <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="6fef6-106">You define the template for the row details section in the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property.</span></span> <span data-ttu-id="6fef6-107">Nella figura seguente viene illustrato un esempio di sezione dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="6fef6-107">The following illustration shows an example of a row details section.</span></span>  
  
 <span data-ttu-id="6fef6-108">![DataGrid visualizzato con dettagli riga](./media/ndp-rowdetails.png "NDP_RowDetails")</span><span class="sxs-lookup"><span data-stu-id="6fef6-108">![DataGrid shown with row details](./media/ndp-rowdetails.png "NDP_RowDetails")</span></span>  
  
 <span data-ttu-id="6fef6-109">Il modello di dettagli della riga viene definito come XAML inline o come risorsa.</span><span class="sxs-lookup"><span data-stu-id="6fef6-109">You define the row details template as either inline XAML or as a resource.</span></span> <span data-ttu-id="6fef6-110">Entrambi gli approcci sono illustrati nelle procedure riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="6fef6-110">Both approaches are shown in the following procedures.</span></span> <span data-ttu-id="6fef6-111">Un modello di dati aggiunto come risorsa può essere usato in tutto il progetto senza dover ricreare il modello.</span><span class="sxs-lookup"><span data-stu-id="6fef6-111">A data template that is added as a resource can be used throughout the project without re-creating the template.</span></span> <span data-ttu-id="6fef6-112">Un modello di dati aggiunto come XAML inline è accessibile solo dal controllo in cui è definito.</span><span class="sxs-lookup"><span data-stu-id="6fef6-112">A data template that is added as inline XAML is only accessible from the control where it is defined.</span></span>  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a><span data-ttu-id="6fef6-113">Per visualizzare i dettagli delle righe utilizzando XAML inline</span><span class="sxs-lookup"><span data-stu-id="6fef6-113">To display row details by using inline XAML</span></span>  
  
1. <span data-ttu-id="6fef6-114">Creare una <xref:System.Windows.Controls.DataGrid> che visualizzi i dati di un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="6fef6-114">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="6fef6-115">Nell'elemento <xref:System.Windows.Controls.DataGrid> aggiungere un elemento <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="6fef6-115">In the <xref:System.Windows.Controls.DataGrid> element, add a <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> element.</span></span>  
  
3. <span data-ttu-id="6fef6-116">Creare una <xref:System.Windows.DataTemplate> che definisce l'aspetto della sezione dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="6fef6-116">Create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="6fef6-117">Il codice XAML seguente illustra il <xref:System.Windows.Controls.DataGrid> e come definire il <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline.</span><span class="sxs-lookup"><span data-stu-id="6fef6-117">The following XAML shows the <xref:System.Windows.Controls.DataGrid> and how to define the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline.</span></span> <span data-ttu-id="6fef6-118">Il <xref:System.Windows.Controls.DataGrid> Visualizza tre valori in ogni riga e altri tre valori quando la riga è selezionata.</span><span class="sxs-lookup"><span data-stu-id="6fef6-118">The <xref:System.Windows.Controls.DataGrid> displays three values in each row and three more values when the row is selected.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     <span data-ttu-id="6fef6-119">Nel codice seguente viene illustrata la query utilizzata per selezionare i dati visualizzati nel <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="6fef6-119">The following code shows the query that is used to select the data that is displayed in the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="6fef6-120">In questo esempio la query seleziona i dati da un'entità che contiene informazioni sul cliente.</span><span class="sxs-lookup"><span data-stu-id="6fef6-120">In this example, the query selects data from an entity that contains customer information.</span></span>  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a><span data-ttu-id="6fef6-121">Per visualizzare i dettagli delle righe utilizzando una risorsa</span><span class="sxs-lookup"><span data-stu-id="6fef6-121">To display row details by using a resource</span></span>  
  
1. <span data-ttu-id="6fef6-122">Creare una <xref:System.Windows.Controls.DataGrid> che visualizzi i dati di un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="6fef6-122">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="6fef6-123">Aggiungere un elemento <xref:System.Windows.FrameworkElement.Resources%2A> all'elemento radice, ad esempio un controllo <xref:System.Windows.Window> o un controllo <xref:System.Windows.Controls.Page>, oppure aggiungere un elemento <xref:System.Windows.Application.Resources%2A> alla classe <xref:System.Windows.Application> nel file app. XAML (o Application. Xaml).</span><span class="sxs-lookup"><span data-stu-id="6fef6-123">Add a <xref:System.Windows.FrameworkElement.Resources%2A> element to the root element, such as a <xref:System.Windows.Window> control or a <xref:System.Windows.Controls.Page> control, or add a <xref:System.Windows.Application.Resources%2A> element to the <xref:System.Windows.Application> class in the App.xaml (or Application.xaml) file.</span></span>  
  
3. <span data-ttu-id="6fef6-124">Nell'elemento resources creare un <xref:System.Windows.DataTemplate> che definisce l'aspetto della sezione dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="6fef6-124">In the resources element, create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="6fef6-125">Il codice XAML seguente illustra il <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> definito nella classe <xref:System.Windows.Application>.</span><span class="sxs-lookup"><span data-stu-id="6fef6-125">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> defined in the <xref:System.Windows.Application> class.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. <span data-ttu-id="6fef6-126">Nella <xref:System.Windows.DataTemplate>impostare la [direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) su un valore che identifica in modo univoco il modello di dati.</span><span class="sxs-lookup"><span data-stu-id="6fef6-126">On the <xref:System.Windows.DataTemplate>, set the [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md) to a value that uniquely identifies the data template.</span></span>  
  
5. <span data-ttu-id="6fef6-127">Nell'elemento <xref:System.Windows.Controls.DataGrid> impostare la proprietà <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> sulla risorsa definita nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="6fef6-127">In the <xref:System.Windows.Controls.DataGrid> element, set the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property to the resource defined in the previous steps.</span></span> <span data-ttu-id="6fef6-128">Assegnare la risorsa come risorsa statica.</span><span class="sxs-lookup"><span data-stu-id="6fef6-128">Assign the resource as a static resource.</span></span>  
  
     <span data-ttu-id="6fef6-129">Il codice XAML seguente mostra la proprietà <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> impostata sulla risorsa dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="6fef6-129">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property set to the resource from the previous example.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a><span data-ttu-id="6fef6-130">Per impostare la visibilità ed evitare lo scorrimento orizzontale per i dettagli delle righe</span><span class="sxs-lookup"><span data-stu-id="6fef6-130">To set visibility and prevent horizontal scrolling for row details</span></span>  
  
1. <span data-ttu-id="6fef6-131">Se necessario, impostare la proprietà <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> su un valore <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode>.</span><span class="sxs-lookup"><span data-stu-id="6fef6-131">If needed, set the <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> property to a <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> value.</span></span>  
  
     <span data-ttu-id="6fef6-132">Per impostazione predefinita, il valore è impostato su <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span><span class="sxs-lookup"><span data-stu-id="6fef6-132">By default, the value is set to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span></span> <span data-ttu-id="6fef6-133">È possibile impostarlo su <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> per visualizzare i dettagli di tutte le righe o <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> per nascondere i dettagli di tutte le righe.</span><span class="sxs-lookup"><span data-stu-id="6fef6-133">You can set it to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> to show the details for all of the rows or <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> to hide the details for all rows.</span></span>  
  
2. <span data-ttu-id="6fef6-134">Se necessario, impostare la proprietà <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> su `true` per impedire lo scorrimento orizzontale della sezione dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="6fef6-134">If needed, set the <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> property to `true` to prevent the row details section from scrolling horizontally.</span></span>
