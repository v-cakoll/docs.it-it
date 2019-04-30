---
title: 'Procedura: Aggiungere funzionalità di ricerca a un controllo ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- lists [Windows Forms], enabling searching
- list views [Windows Forms], enabling searching
- ListView control [Windows Forms], adding search capabilities
- searching [Windows Forms], adding search capabilities to ListView control
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
ms.openlocfilehash: d5d4dae55fc9f0613ab6535b2fe57e262d0ef141
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011022"
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a><span data-ttu-id="5dcc2-102">Procedura: Aggiungere funzionalità di ricerca a un controllo ListView</span><span class="sxs-lookup"><span data-stu-id="5dcc2-102">How to: Add Search Capabilities to a ListView Control</span></span>
<span data-ttu-id="5dcc2-103">Spesso quando si lavora con un lungo elenco di elementi in un <xref:System.Windows.Forms.ListView> (controllo), si desidera offrire funzionalità di ricerca per l'utente.</span><span class="sxs-lookup"><span data-stu-id="5dcc2-103">Oftentimes when working with a large list of items in a <xref:System.Windows.Forms.ListView> control, you want to offer search capabilities to the user.</span></span> <span data-ttu-id="5dcc2-104">Il <xref:System.Windows.Forms.ListView> controllo offre questa funzionalità in due modi diversi: i criteri di testo e la ricerca di posizione.</span><span class="sxs-lookup"><span data-stu-id="5dcc2-104">The <xref:System.Windows.Forms.ListView> control offers this capability in two different ways: text matching and location searching.</span></span>  
  
 <span data-ttu-id="5dcc2-105">Il <xref:System.Windows.Forms.ListView.FindItemWithText%2A> metodo consente di eseguire una ricerca di testo in un <xref:System.Windows.Forms.ListView> nella visualizzazione elenco o dettagli, data una stringa di ricerca e un inizio e fine facoltativi dell'indice.</span><span class="sxs-lookup"><span data-stu-id="5dcc2-105">The <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method allows you to perform a text search on a <xref:System.Windows.Forms.ListView> in list or details view, given a search string and an optional starting and ending index.</span></span> <span data-ttu-id="5dcc2-106">Al contrario, il <xref:System.Windows.Forms.ListView.FindNearestItem%2A> metodo consente di trovare un elemento in un <xref:System.Windows.Forms.ListView> nella visualizzazione riquadro o sull'icona, dato un set di coordinate x e y e una direzione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="5dcc2-106">In contrast, the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method allows you to find an item in a <xref:System.Windows.Forms.ListView> in icon or tile view, given a set of x- and y-coordinates and a direction to search.</span></span>  
  
### <a name="to-find-an-item-using-text"></a><span data-ttu-id="5dcc2-107">Per trovare un elemento utilizzando il testo</span><span class="sxs-lookup"><span data-stu-id="5dcc2-107">To find an item using text</span></span>  
  
1. <span data-ttu-id="5dcc2-108">Creare un <xref:System.Windows.Forms.ListView> con il <xref:System.Windows.Forms.ListView.View%2A> proprietà impostata su <xref:System.Windows.Forms.View.Details> o <xref:System.Windows.Forms.View.List>, quindi compilare il <xref:System.Windows.Forms.ListView> con gli elementi.</span><span class="sxs-lookup"><span data-stu-id="5dcc2-108">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.ListView.View%2A> property set to <xref:System.Windows.Forms.View.Details> or <xref:System.Windows.Forms.View.List>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2. <span data-ttu-id="5dcc2-109">Chiamare il <xref:System.Windows.Forms.ListView.FindItemWithText%2A> , passando il testo dell'elemento da trovare.</span><span class="sxs-lookup"><span data-stu-id="5dcc2-109">Call the <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method, passing the text of the item you would like to find.</span></span>  
  
3. <span data-ttu-id="5dcc2-110">Esempio di codice seguente viene illustrato come creare una semplice <xref:System.Windows.Forms.ListView>viene popolato con gli elementi e input di testo da parte dell'utente viene utilizzato per trovare un elemento nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="5dcc2-110">The following code example demonstrates how to create a basic <xref:System.Windows.Forms.ListView>, populate it with items, and use text input from the user to find an item in the list.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a><span data-ttu-id="5dcc2-111">Per trovare un elemento utilizzando le coordinate x e y</span><span class="sxs-lookup"><span data-stu-id="5dcc2-111">To find an item using x- and y-coordinates</span></span>  
  
1. <span data-ttu-id="5dcc2-112">Creare un <xref:System.Windows.Forms.ListView> con il <xref:System.Windows.Forms.View> proprietà impostata su <xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon>, quindi compilare il <xref:System.Windows.Forms.ListView> con gli elementi.</span><span class="sxs-lookup"><span data-stu-id="5dcc2-112">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.View> property set to <xref:System.Windows.Forms.View.SmallIcon> or <xref:System.Windows.Forms.View.LargeIcon>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2. <span data-ttu-id="5dcc2-113">Chiamare il <xref:System.Windows.Forms.ListView.FindNearestItem%2A> , passando le coordinate x e y desiderata e la direzione in cui si vuole eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="5dcc2-113">Call the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method, passing the desired x- and y-coordinates and the direction you would like to search.</span></span>  
  
3. <span data-ttu-id="5dcc2-114">Esempio di codice seguente viene illustrato come creare un'icona di base <xref:System.Windows.Forms.ListView>, viene popolato con elementi e acquisire il <xref:System.Windows.Forms.Control.MouseDown> eventi per trovare l'elemento più vicino in alto.</span><span class="sxs-lookup"><span data-stu-id="5dcc2-114">The following code example demonstrates how to create a basic icon <xref:System.Windows.Forms.ListView>, populate it with items, and capture the <xref:System.Windows.Forms.Control.MouseDown> event to find the nearest item in the up direction.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="5dcc2-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dcc2-115">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.FindItemWithText%2A>
- <xref:System.Windows.Forms.ListView.FindNearestItem%2A>
- [<span data-ttu-id="5dcc2-116">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="5dcc2-116">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="5dcc2-117">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="5dcc2-117">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="5dcc2-118">Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5dcc2-118">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
