---
title: 'Procedura: Applicare uno stile a una riga in un ListView che implementa un oggetto GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 9af8d10c7db2d3bbe8b9443402cbb1cfeaa7edb3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091460"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="e0c4b-102">Procedura: Applicare uno stile a una riga in un ListView che implementa un oggetto GridView</span><span class="sxs-lookup"><span data-stu-id="e0c4b-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="e0c4b-103">Questo esempio viene illustrato come applicare uno stile a una riga in una <xref:System.Windows.Controls.ListView> controllo che implementa un <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> modalità.</span><span class="sxs-lookup"><span data-stu-id="e0c4b-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that implements a <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0c4b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e0c4b-104">Example</span></span>  
 <span data-ttu-id="e0c4b-105">È possibile applicare uno stile a una riga in una <xref:System.Windows.Controls.ListView> controllo impostando un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> nel <xref:System.Windows.Controls.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="e0c4b-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="e0c4b-106">Impostare lo stile per i relativi elementi rappresentati come <xref:System.Windows.Controls.ListViewItem> oggetti.</span><span class="sxs-lookup"><span data-stu-id="e0c4b-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="e0c4b-107">Il <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> riferimenti di <xref:System.Windows.Controls.ControlTemplate> gli oggetti che consentono di visualizzare il contenuto della riga.</span><span class="sxs-lookup"><span data-stu-id="e0c4b-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="e0c4b-108">L'esempio completo, da cui sono estratti gli esempi seguenti, visualizza una raccolta di informazioni relative a brani archiviati in un database [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0c4b-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] database.</span></span> <span data-ttu-id="e0c4b-109">Ogni brano nel database include un campo di classificazione e il valore di questo campo specifica la modalità di visualizzazione di una riga di informazioni relative al brano.</span><span class="sxs-lookup"><span data-stu-id="e0c4b-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="e0c4b-110">Nell'esempio seguente viene illustrato come definire <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> per il <xref:System.Windows.Controls.ListViewItem> gli oggetti che rappresentano i brani nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="e0c4b-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="e0c4b-111">Il <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> riferimenti <xref:System.Windows.Controls.ControlTemplate> gli oggetti che specificano come visualizzare una riga di informazioni relative al brano.</span><span class="sxs-lookup"><span data-stu-id="e0c4b-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="e0c4b-112">L'esempio seguente mostra una <xref:System.Windows.Controls.ControlTemplate> che aggiunge la stringa di testo `"Strongly Recommended"` alla riga.</span><span class="sxs-lookup"><span data-stu-id="e0c4b-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="e0c4b-113">Questo modello fa riferimento il <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> e viene visualizzato quando la valutazione del brano ha un valore pari a 5 (cinque).</span><span class="sxs-lookup"><span data-stu-id="e0c4b-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="e0c4b-114">Il <xref:System.Windows.Controls.ControlTemplate> include un <xref:System.Windows.Controls.GridViewRowPresenter> che applica il contenuto della riga di colonne come definito dall'oggetto di <xref:System.Windows.Controls.GridView> modalità di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="e0c4b-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="e0c4b-115">L'esempio seguente definisce <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="e0c4b-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="e0c4b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0c4b-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="e0c4b-117">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="e0c4b-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="e0c4b-118">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="e0c4b-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="e0c4b-119">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="e0c4b-119">Styling and Templating</span></span>](styling-and-templating.md)
