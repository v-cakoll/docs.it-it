---
title: "Procedura: gestire l'evento MouseDoubleClick per ciascun elemento di ListView"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 7bbc7bad36b3b1f2c92065e5f5699e5a86ac6189
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646103"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="9a21f-102">Procedura: gestire l'evento MouseDoubleClick per ciascun elemento di ListView</span><span class="sxs-lookup"><span data-stu-id="9a21f-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="9a21f-103">Per gestire un evento per <xref:System.Windows.Controls.ListView>un elemento in un oggetto <xref:System.Windows.Controls.ListViewItem>, è necessario aggiungere un gestore eventi a ciascuno di essi .</span><span class="sxs-lookup"><span data-stu-id="9a21f-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="9a21f-104">Quando <xref:System.Windows.Controls.ListView> un oggetto è associato a un'origine <xref:System.Windows.Controls.ListViewItem>dati, non si crea in modo <xref:System.Windows.EventSetter> esplicito un <xref:System.Windows.Controls.ListViewItem>oggetto , ma è possibile gestire l'evento per ogni elemento aggiungendo un a uno stile di un oggetto .</span><span class="sxs-lookup"><span data-stu-id="9a21f-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a21f-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="9a21f-105">Example</span></span>  
 <span data-ttu-id="9a21f-106">Nell'esempio riportato di <xref:System.Windows.Controls.ListView> seguito <xref:System.Windows.Style> viene creata una associazione a dati e viene creato un oggetto per aggiungere un gestore eventi a each <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="9a21f-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="9a21f-107">Nell'esempio seguente <xref:System.Windows.Controls.Control.MouseDoubleClick> viene gestita l'evento.</span><span class="sxs-lookup"><span data-stu-id="9a21f-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> <span data-ttu-id="9a21f-108">Sebbene sia più comune <xref:System.Windows.Controls.ListView> associare un oggetto a un'origine dati, <xref:System.Windows.Controls.ListViewItem> è possibile utilizzare uno <xref:System.Windows.Controls.ListView> stile per aggiungere un <xref:System.Windows.Controls.ListViewItem>gestore eventi a ciascuno in un'origine dati non associata, indipendentemente dal fatto che venga creato in modo esplicito un oggetto .</span><span class="sxs-lookup"><span data-stu-id="9a21f-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="9a21f-109">Per ulteriori informazioni sui controlli <xref:System.Windows.Controls.ListViewItem> creati <xref:System.Windows.Controls.ItemsControl>in modo esplicito e implicito, vedere .</span><span class="sxs-lookup"><span data-stu-id="9a21f-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a21f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a21f-110">See also</span></span>

- <xref:System.Xml.XmlElement>
- [<span data-ttu-id="9a21f-111">Cenni preliminari sull'associazione dati</span><span class="sxs-lookup"><span data-stu-id="9a21f-111">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="9a21f-112">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="9a21f-112">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="9a21f-113">Eseguire l'associazione a dati XML utilizzando un XMLDataProvider e query XPathBind to XML Data Using an XMLDataProvider and XPath Queries</span><span class="sxs-lookup"><span data-stu-id="9a21f-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="9a21f-114">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="9a21f-114">ListView Overview</span></span>](listview-overview.md)
