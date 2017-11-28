---
title: 'Procedura: modificare l''allineamento orizzontale di una colonna in ListView'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3ed163de9a5b01a3ddab8ef42d21f38d35f48519
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a><span data-ttu-id="79a23-102">Procedura: modificare l'allineamento orizzontale di una colonna in ListView</span><span class="sxs-lookup"><span data-stu-id="79a23-102">How to: Change the Horizontal Alignment of a Column in a ListView</span></span>
<span data-ttu-id="79a23-103">Per impostazione predefinita, il contenuto di ogni colonna in un <xref:System.Windows.Controls.ListViewItem> allineato a sinistra.</span><span class="sxs-lookup"><span data-stu-id="79a23-103">By default, the content of each column in a <xref:System.Windows.Controls.ListViewItem> is left-aligned.</span></span> <span data-ttu-id="79a23-104">È possibile modificare l'allineamento di ogni colonna, fornendo un <xref:System.Windows.DataTemplate> e impostando il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà dell'elemento all'interno di <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="79a23-104">You can change the alignment of each column by providing a <xref:System.Windows.DataTemplate> and setting the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property on the element within the <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="79a23-105">Questo argomento viene illustrato come un <xref:System.Windows.Controls.ListView> allineato il contenuto per impostazione predefinita e come modificare l'allineamento di una colonna in un <xref:System.Windows.Controls.ListView>.</span><span class="sxs-lookup"><span data-stu-id="79a23-105">This topic shows how a <xref:System.Windows.Controls.ListView> aligns its content by default and how to change the alignment of one column in a <xref:System.Windows.Controls.ListView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79a23-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="79a23-106">Example</span></span>  
 <span data-ttu-id="79a23-107">Nell'esempio seguente, i dati di `Title` e `ISBN` colonne è allineato a sinistra.</span><span class="sxs-lookup"><span data-stu-id="79a23-107">In the following example, the data in the `Title` and `ISBN` columns is left-aligned.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="79a23-108">Per modificare l'allineamento del `ISBN` colonna, è necessario specificare che il <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> proprietà di ogni <xref:System.Windows.Controls.ListViewItem> è <xref:System.Windows.HorizontalAlignment.Stretch>, in modo che gli elementi in ogni <xref:System.Windows.Controls.ListViewItem> può estendersi o essere posizionata lungo l'intera larghezza di ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="79a23-108">To change the alignment of the `ISBN` column, you need to specify that the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> property of each <xref:System.Windows.Controls.ListViewItem> is <xref:System.Windows.HorizontalAlignment.Stretch>, so that the elements in each <xref:System.Windows.Controls.ListViewItem> can span or be positioned along the entire width of each column.</span></span> <span data-ttu-id="79a23-109">Poiché il <xref:System.Windows.Controls.ListView> è associato a un'origine dati, è necessario creare uno stile che imposta il <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span><span class="sxs-lookup"><span data-stu-id="79a23-109">Because the <xref:System.Windows.Controls.ListView> is bound to a data source, you need to create a style that sets the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span></span> <span data-ttu-id="79a23-110">Successivamente, è necessario utilizzare un <xref:System.Windows.DataTemplate> per visualizzare il contenuto invece di usare il <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="79a23-110">Next, you need to use a <xref:System.Windows.DataTemplate> to display the content instead of using the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property.</span></span> <span data-ttu-id="79a23-111">Per visualizzare il `ISBN` di ogni modello, il <xref:System.Windows.DataTemplate> può contenere solo un <xref:System.Windows.Controls.TextBlock> con relativo <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà impostata su <xref:System.Windows.HorizontalAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="79a23-111">To display the `ISBN` of each template, the <xref:System.Windows.DataTemplate> can just contain a <xref:System.Windows.Controls.TextBlock> that has its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property set to <xref:System.Windows.HorizontalAlignment.Right>.</span></span>  
  
 <span data-ttu-id="79a23-112">L'esempio seguente definisce lo stile e <xref:System.Windows.DataTemplate> necessarie per rendere il `ISBN` colonna allineata a destra e la modifica di <xref:System.Windows.Controls.GridViewColumn> per fare riferimento il <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="79a23-112">The following example defines the style and <xref:System.Windows.DataTemplate> necessary to make the `ISBN` column right-aligned, and changes the <xref:System.Windows.Controls.GridViewColumn> to reference the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="79a23-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79a23-113">See Also</span></span>  
 [<span data-ttu-id="79a23-114">Cenni preliminari sull'associazione dati</span><span class="sxs-lookup"><span data-stu-id="79a23-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="79a23-115">Panoramica sui modelli di dati</span><span class="sxs-lookup"><span data-stu-id="79a23-115">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="79a23-116">Eseguire l'associazione ai dati XML usando un oggetto XMLDataProvider e le query XPath</span><span class="sxs-lookup"><span data-stu-id="79a23-116">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [<span data-ttu-id="79a23-117">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="79a23-117">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
