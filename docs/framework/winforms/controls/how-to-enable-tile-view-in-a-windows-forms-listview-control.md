---
title: 'Procedura: Abilitare la visualizzazione affiancata in un controllo ListView di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tile view feature
- tiling
- Windows Forms, controls
- ListView control [Windows Forms], tile view
ms.assetid: c20e67a3-2d94-413d-9fcf-ecbd0fe251da
ms.openlocfilehash: 489b9a9d0341391c756175acb19d962d642eb7b2
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960457"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control"></a><span data-ttu-id="9e166-102">Procedura: Abilitare la visualizzazione affiancata in un controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9e166-102">How to: Enable Tile View in a Windows Forms ListView Control</span></span>
<span data-ttu-id="9e166-103">La funzionalità di visualizzazione affiancata del controllo <xref:System.Windows.Forms.ListView>, è possibile fornire un equilibrio visivo tra informazioni grafiche e testuali.</span><span class="sxs-lookup"><span data-stu-id="9e166-103">With the tile view feature of the <xref:System.Windows.Forms.ListView> control, you can provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="9e166-104">Le informazioni testuali visualizzate per un elemento nella visualizzazione affiancata corrisponde alle informazioni della colonna definite per la visualizzazione dettagli.</span><span class="sxs-lookup"><span data-stu-id="9e166-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="9e166-105">La visualizzazione affiancata viene usata in combinazione con le funzionalità di raggruppamento o segno di inserimento nel controllo <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="9e166-105">Tile view works in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 <span data-ttu-id="9e166-106">La visualizzazione affiancata usa un'icona di 32 x 32 pixel e alcune righe di testo, come illustrato nelle immagini seguenti.</span><span class="sxs-lookup"><span data-stu-id="9e166-106">The tile view uses a 32 x 32 pixel icon and several lines of text, as shown in the following images.</span></span>  
  
 <span data-ttu-id="9e166-107">![Visualizzazione affiancata in un controllo ListView](./media/how-to-enable-tile-view-in-a-windows-forms-listview-control/tile-view-in-listview-control.gif "Icone e testo di visualizzazione affiancata")</span><span class="sxs-lookup"><span data-stu-id="9e166-107">![Tile View in a ListView Control](./media/how-to-enable-tile-view-in-a-windows-forms-listview-control/tile-view-in-listview-control.gif "Tile view icons and text")</span></span>  
 
 <span data-ttu-id="9e166-108">Per abilitare la visualizzazione affiancata, impostare la proprietà <xref:System.Windows.Forms.ListView.View%2A> su <xref:System.Windows.Forms.View.Tile>.</span><span class="sxs-lookup"><span data-stu-id="9e166-108">To enable tile view, set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Tile>.</span></span> <span data-ttu-id="9e166-109">È possibile regolare la dimensione dei riquadri impostando la proprietà <xref:System.Windows.Forms.ListView.TileSize%2A> e il numero di righe di testo visualizzate nel riquadro regolando la raccolta <xref:System.Windows.Forms.ListView.Columns%2A>.</span><span class="sxs-lookup"><span data-stu-id="9e166-109">You can adjust the size of the tiles by setting the <xref:System.Windows.Forms.ListView.TileSize%2A> property, and the number of text lines displayed in the tile by adjusting the <xref:System.Windows.Forms.ListView.Columns%2A> collection.</span></span>  
  
### <a name="to-set-tile-view-programmatically"></a><span data-ttu-id="9e166-110">Per impostare la visualizzazione affiancata a livello di codice</span><span class="sxs-lookup"><span data-stu-id="9e166-110">To set tile view programmatically</span></span>  
  
1. <span data-ttu-id="9e166-111">Usare l'enumerazione <xref:System.Windows.Forms.View> del controllo <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="9e166-111">Use the <xref:System.Windows.Forms.View> enumeration of the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
    ```vb  
    ListView1.View = View.Tile  
    ```  
  
    ```csharp  
    listView1.View = View.Tile;  
    ```  
  
## <a name="example"></a><span data-ttu-id="9e166-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="9e166-112">Example</span></span>  
 <span data-ttu-id="9e166-113">L'esempio di codice completo seguente illustra la visualizzazione affiancata con riquadri modificati in modo da visualizzare tre righe di testo.</span><span class="sxs-lookup"><span data-stu-id="9e166-113">The following complete code example demonstrates Tile view with tiles modified to show three lines of text.</span></span> <span data-ttu-id="9e166-114">La dimensione dei riquadri è stata modificata per evitare il ritorno a capo.</span><span class="sxs-lookup"><span data-stu-id="9e166-114">The tile size has been adjusted to prevent line-wrapping.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CPP/listviewtilingexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CS/listviewtilingexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/VB/listviewtilingexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9e166-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="9e166-115">Compiling the Code</span></span>  
 <span data-ttu-id="9e166-116">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9e166-116">This example requires:</span></span>  
  
- <span data-ttu-id="9e166-117">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="9e166-117">References to the System and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="9e166-118">Un file di icona denominato book.ico nella stessa directory del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="9e166-118">An icon file named book.ico in the same directory as the executable file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e166-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e166-119">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [<span data-ttu-id="9e166-120">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="9e166-120">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="9e166-121">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="9e166-121">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
