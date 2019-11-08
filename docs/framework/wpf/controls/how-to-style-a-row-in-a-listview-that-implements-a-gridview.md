---
title: 'Procedura: applicare uno stile a una riga in un ListView che implementa una GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: ce79899d5c8e825ecb39e14ae8af4e0c33f13db3
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733550"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="8aaa8-102">Procedura: applicare uno stile a una riga in un ListView che implementa una GridView</span><span class="sxs-lookup"><span data-stu-id="8aaa8-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="8aaa8-103">Questo esempio illustra come applicare uno stile a una riga in un controllo <xref:System.Windows.Controls.ListView> che implementa una modalità di <xref:System.Windows.Controls.ListView.View%2A> <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="8aaa8-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that implements a <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8aaa8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8aaa8-104">Example</span></span>  
 <span data-ttu-id="8aaa8-105">È possibile applicare uno stile a una riga in un controllo <xref:System.Windows.Controls.ListView> impostando una <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> sul controllo <xref:System.Windows.Controls.ListView>.</span><span class="sxs-lookup"><span data-stu-id="8aaa8-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="8aaa8-106">Impostare lo stile per gli elementi rappresentati come oggetti <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="8aaa8-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="8aaa8-107">Il <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> fa riferimento agli oggetti <xref:System.Windows.Controls.ControlTemplate> utilizzati per visualizzare il contenuto della riga.</span><span class="sxs-lookup"><span data-stu-id="8aaa8-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="8aaa8-108">Nell'esempio completo, da cui vengono estratti gli esempi seguenti, viene visualizzata una raccolta di informazioni sui brani archiviate in un database XML.</span><span class="sxs-lookup"><span data-stu-id="8aaa8-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an XML database.</span></span> <span data-ttu-id="8aaa8-109">Ogni brano nel database include un campo di classificazione e il valore di questo campo specifica la modalità di visualizzazione di una riga di informazioni relative al brano.</span><span class="sxs-lookup"><span data-stu-id="8aaa8-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="8aaa8-110">Nell'esempio seguente viene illustrato come definire <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> per gli oggetti <xref:System.Windows.Controls.ListViewItem> che rappresentano i brani della raccolta Song.</span><span class="sxs-lookup"><span data-stu-id="8aaa8-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="8aaa8-111">Il <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> fa riferimento a <xref:System.Windows.Controls.ControlTemplate> oggetti che specificano come visualizzare una riga di informazioni sul brano.</span><span class="sxs-lookup"><span data-stu-id="8aaa8-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="8aaa8-112">Nell'esempio seguente viene illustrato un <xref:System.Windows.Controls.ControlTemplate> che aggiunge la stringa di testo `"Strongly Recommended"` alla riga.</span><span class="sxs-lookup"><span data-stu-id="8aaa8-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="8aaa8-113">Si fa riferimento a questo modello nel <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> e viene visualizzato quando la classificazione del brano ha un valore pari a 5 (cinque).</span><span class="sxs-lookup"><span data-stu-id="8aaa8-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="8aaa8-114">Il <xref:System.Windows.Controls.ControlTemplate> include un oggetto <xref:System.Windows.Controls.GridViewRowPresenter> che imposta il contenuto della riga nelle colonne, come definito dalla modalità di visualizzazione <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="8aaa8-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="8aaa8-115">Nell'esempio seguente viene definito <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="8aaa8-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="8aaa8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8aaa8-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="8aaa8-117">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="8aaa8-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="8aaa8-118">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="8aaa8-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="8aaa8-119">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="8aaa8-119">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
