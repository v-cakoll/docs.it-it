---
title: 'Procedura: Aggiungere dettagli di riga a un controllo DataGrid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: d5b6539f3d379088528b9654861267988b6fc69b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911391"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a><span data-ttu-id="be203-102">Procedura: Aggiungere dettagli di riga a un controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="be203-102">How to: Add Row Details to a DataGrid Control</span></span>
<span data-ttu-id="be203-103">Quando si usa il <xref:System.Windows.Controls.DataGrid> (controllo), è possibile personalizzare la presentazione dei dati mediante l'aggiunta di una sezione di dettagli della riga.</span><span class="sxs-lookup"><span data-stu-id="be203-103">When using the <xref:System.Windows.Controls.DataGrid> control, you can customize the data presentation by adding a row details section.</span></span> <span data-ttu-id="be203-104">Aggiunta di una sezione di dettagli di riga consente di raggruppare i dati in un modello che è possibile rendere visibile o compressa.</span><span class="sxs-lookup"><span data-stu-id="be203-104">Adding a row details section enables you to group some data in a template that is optionally visible or collapsed.</span></span> <span data-ttu-id="be203-105">Ad esempio, è possibile aggiungere i dettagli delle righe per un <xref:System.Windows.Controls.DataGrid> che presenta solo un riepilogo dei dati per ogni riga nel <xref:System.Windows.Controls.DataGrid>, ma presenta più campi di dati quando l'utente seleziona una riga.</span><span class="sxs-lookup"><span data-stu-id="be203-105">For example, you can add row details to a <xref:System.Windows.Controls.DataGrid> that presents only a summary of the data for each row in the <xref:System.Windows.Controls.DataGrid>, but presents more data fields when the user selects a row.</span></span> <span data-ttu-id="be203-106">Viene definito il modello per la sezione dettagli della riga nel <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="be203-106">You define the template for the row details section in the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property.</span></span> <span data-ttu-id="be203-107">La figura seguente mostra un esempio di una sezione di dettagli della riga.</span><span class="sxs-lookup"><span data-stu-id="be203-107">The following illustration shows an example of a row details section.</span></span>  
  
 <span data-ttu-id="be203-108">![DataGrid con i dettagli della riga](./media/ndp-rowdetails.png "NDP_RowDetails")</span><span class="sxs-lookup"><span data-stu-id="be203-108">![DataGrid shown with row details](./media/ndp-rowdetails.png "NDP_RowDetails")</span></span>  
  
 <span data-ttu-id="be203-109">Il modello di dettagli della riga è definire come inline XAML o come una risorsa.</span><span class="sxs-lookup"><span data-stu-id="be203-109">You define the row details template as either inline XAML or as a resource.</span></span> <span data-ttu-id="be203-110">Entrambi gli approcci sono illustrati nelle procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="be203-110">Both approaches are shown in the following procedures.</span></span> <span data-ttu-id="be203-111">Un modello di dati che viene aggiunto come una risorsa può essere usata nel corso del progetto senza creare di nuovo il modello.</span><span class="sxs-lookup"><span data-stu-id="be203-111">A data template that is added as a resource can be used throughout the project without re-creating the template.</span></span> <span data-ttu-id="be203-112">Un modello di dati che viene aggiunto come inline XAML è accessibile solo dal controllo in cui è definito.</span><span class="sxs-lookup"><span data-stu-id="be203-112">A data template that is added as inline XAML is only accessible from the control where it is defined.</span></span>  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a><span data-ttu-id="be203-113">Per visualizzare i dettagli della riga con inline XAML</span><span class="sxs-lookup"><span data-stu-id="be203-113">To display row details by using inline XAML</span></span>  
  
1. <span data-ttu-id="be203-114">Creare un <xref:System.Windows.Controls.DataGrid> che visualizza i dati da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="be203-114">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="be203-115">Nell'elemento <xref:System.Windows.Controls.DataGrid> aggiungere un elemento <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="be203-115">In the <xref:System.Windows.Controls.DataGrid> element, add a <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> element.</span></span>  
  
3. <span data-ttu-id="be203-116">Creare un <xref:System.Windows.DataTemplate> che definisce l'aspetto della sezione di dettagli di riga.</span><span class="sxs-lookup"><span data-stu-id="be203-116">Create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="be203-117">Nell'esempio di XAML seguente viene illustrato il <xref:System.Windows.Controls.DataGrid> e come definire il <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline.</span><span class="sxs-lookup"><span data-stu-id="be203-117">The following XAML shows the <xref:System.Windows.Controls.DataGrid> and how to define the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline.</span></span> <span data-ttu-id="be203-118">Il <xref:System.Windows.Controls.DataGrid> consente di visualizzare tre valori in ogni riga e tre i valori più quando la riga è selezionata.</span><span class="sxs-lookup"><span data-stu-id="be203-118">The <xref:System.Windows.Controls.DataGrid> displays three values in each row and three more values when the row is selected.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     <span data-ttu-id="be203-119">Il codice seguente mostra la query che consente di selezionare i dati che viene visualizzati nei <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="be203-119">The following code shows the query that is used to select the data that is displayed in the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="be203-120">In questo esempio, la query Seleziona i dati da un'entità che contiene informazioni sul cliente.</span><span class="sxs-lookup"><span data-stu-id="be203-120">In this example, the query selects data from an entity that contains customer information.</span></span>  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a><span data-ttu-id="be203-121">Per visualizzare i dettagli della riga tramite una risorsa</span><span class="sxs-lookup"><span data-stu-id="be203-121">To display row details by using a resource</span></span>  
  
1. <span data-ttu-id="be203-122">Creare un <xref:System.Windows.Controls.DataGrid> che visualizza i dati da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="be203-122">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="be203-123">Aggiungere un <xref:System.Windows.FrameworkElement.Resources%2A> elemento e l'elemento radice, ad esempio un <xref:System.Windows.Window> controllo o una <xref:System.Windows.Controls.Page> controllare o aggiungere un <xref:System.Windows.Application.Resources%2A> elemento per il <xref:System.Windows.Application> classe nel file app. XAML (o Application. XAML).</span><span class="sxs-lookup"><span data-stu-id="be203-123">Add a <xref:System.Windows.FrameworkElement.Resources%2A> element to the root element, such as a <xref:System.Windows.Window> control or a <xref:System.Windows.Controls.Page> control, or add a <xref:System.Windows.Application.Resources%2A> element to the <xref:System.Windows.Application> class in the App.xaml (or Application.xaml) file.</span></span>  
  
3. <span data-ttu-id="be203-124">Nell'elemento resources, creare un <xref:System.Windows.DataTemplate> che definisce l'aspetto della sezione di dettagli di riga.</span><span class="sxs-lookup"><span data-stu-id="be203-124">In the resources element, create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="be203-125">XAML seguente il <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> definito nel <xref:System.Windows.Application> classe.</span><span class="sxs-lookup"><span data-stu-id="be203-125">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> defined in the <xref:System.Windows.Application> class.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. <span data-ttu-id="be203-126">Nel <xref:System.Windows.DataTemplate>, impostare il [direttiva X:Key](../../xaml-services/x-key-directive.md) su un valore che identifica in modo univoco il modello di dati.</span><span class="sxs-lookup"><span data-stu-id="be203-126">On the <xref:System.Windows.DataTemplate>, set the [x:Key Directive](../../xaml-services/x-key-directive.md) to a value that uniquely identifies the data template.</span></span>  
  
5. <span data-ttu-id="be203-127">Nel <xref:System.Windows.Controls.DataGrid> elemento, impostare il <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> proprietà per la risorsa definita nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="be203-127">In the <xref:System.Windows.Controls.DataGrid> element, set the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property to the resource defined in the previous steps.</span></span> <span data-ttu-id="be203-128">Assegnare la risorsa come una risorsa statica.</span><span class="sxs-lookup"><span data-stu-id="be203-128">Assign the resource as a static resource.</span></span>  
  
     <span data-ttu-id="be203-129">L'esempio di XAML seguente illustra il <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> proprietà è impostata per la risorsa dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="be203-129">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property set to the resource from the previous example.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a><span data-ttu-id="be203-130">Per impostare la visibilità e impedire lo scorrimento orizzontale per i dettagli della riga</span><span class="sxs-lookup"><span data-stu-id="be203-130">To set visibility and prevent horizontal scrolling for row details</span></span>  
  
1. <span data-ttu-id="be203-131">Se necessario, impostare il <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> proprietà su un <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> valore.</span><span class="sxs-lookup"><span data-stu-id="be203-131">If needed, set the <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> property to a <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> value.</span></span>  
  
     <span data-ttu-id="be203-132">Per impostazione predefinita, il valore è impostato su <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span><span class="sxs-lookup"><span data-stu-id="be203-132">By default, the value is set to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span></span> <span data-ttu-id="be203-133">È possibile impostarla su <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> per visualizzare i dettagli per tutte le righe o <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> per nascondere i dettagli per tutte le righe.</span><span class="sxs-lookup"><span data-stu-id="be203-133">You can set it to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> to show the details for all of the rows or <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> to hide the details for all rows.</span></span>  
  
2. <span data-ttu-id="be203-134">Se necessario, impostare il <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> proprietà `true` sezione effettuato uno scorrimento orizzontale per impedire la riga dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="be203-134">If needed, set the <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> property to `true` to prevent the row details section from scrolling horizontally.</span></span>
