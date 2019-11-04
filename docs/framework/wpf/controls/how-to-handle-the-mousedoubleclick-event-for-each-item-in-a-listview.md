---
title: "Procedura: gestire l'evento MouseDoubleClick per ciascun elemento di ListView"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 25308ee87fb387787e20c8a8887ae8e4e60742b9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460225"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="1cbf8-102">Procedura: gestire l'evento MouseDoubleClick per ciascun elemento di ListView</span><span class="sxs-lookup"><span data-stu-id="1cbf8-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="1cbf8-103">Per gestire un evento per un elemento in una <xref:System.Windows.Controls.ListView>, è necessario aggiungere un gestore eventi a ogni <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="1cbf8-104">Quando un <xref:System.Windows.Controls.ListView> viene associato a un'origine dati, non si crea in modo esplicito una <xref:System.Windows.Controls.ListViewItem>, ma è possibile gestire l'evento per ogni elemento aggiungendo un <xref:System.Windows.EventSetter> a uno stile di una <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cbf8-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="1cbf8-105">Example</span></span>  
 <span data-ttu-id="1cbf8-106">Nell'esempio seguente viene creata una <xref:System.Windows.Controls.ListView> associata a dati e viene creato un <xref:System.Windows.Style> per aggiungere un gestore eventi a ogni <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="1cbf8-107">Nell'esempio seguente viene gestito l'evento <xref:System.Windows.Controls.Control.MouseDoubleClick>.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> <span data-ttu-id="1cbf8-108">Sebbene sia più comune associare un <xref:System.Windows.Controls.ListView> a un'origine dati, è possibile utilizzare uno stile per aggiungere un gestore eventi a ogni <xref:System.Windows.Controls.ListViewItem> in un <xref:System.Windows.Controls.ListView> non associato ai dati indipendentemente dal fatto che si crei in modo esplicito un <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="1cbf8-109">Per ulteriori informazioni sui controlli <xref:System.Windows.Controls.ListViewItem> creati in modo esplicito e implicito, vedere <xref:System.Windows.Controls.ItemsControl>.</span><span class="sxs-lookup"><span data-stu-id="1cbf8-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cbf8-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cbf8-110">See also</span></span>

- <xref:System.Xml.XmlElement>
- [<span data-ttu-id="1cbf8-111">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="1cbf8-111">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="1cbf8-112">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="1cbf8-112">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="1cbf8-113">Eseguire l'associazione ai dati XML usando un oggetto XMLDataProvider e le query XPath</span><span class="sxs-lookup"><span data-stu-id="1cbf8-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="1cbf8-114">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="1cbf8-114">ListView Overview</span></span>](listview-overview.md)
