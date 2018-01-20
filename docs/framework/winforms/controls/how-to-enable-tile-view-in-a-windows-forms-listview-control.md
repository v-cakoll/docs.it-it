---
title: 'Procedura: abilitare la visualizzazione affiancata in un controllo ListView di Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad4680490e95da91e72b3b8d6d5f65eec2d115f8
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control"></a><span data-ttu-id="63225-102">Procedura: abilitare la visualizzazione affiancata in un controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="63225-102">How to: Enable Tile View in a Windows Forms ListView Control</span></span>
<span data-ttu-id="63225-103">La funzionalità di visualizzazione affiancata del controllo <xref:System.Windows.Forms.ListView>, è possibile fornire un equilibrio visivo tra informazioni grafiche e testuali.</span><span class="sxs-lookup"><span data-stu-id="63225-103">With the tile view feature of the <xref:System.Windows.Forms.ListView> control, you can provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="63225-104">Le informazioni testuali visualizzate per un elemento nella visualizzazione affiancata corrisponde alle informazioni della colonna definite per la visualizzazione dettagli.</span><span class="sxs-lookup"><span data-stu-id="63225-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="63225-105">La visualizzazione affiancata viene usata in combinazione con le funzionalità di raggruppamento o segno di inserimento nel controllo <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="63225-105">Tile view works in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 <span data-ttu-id="63225-106">La visualizzazione affiancata usa un'icona di 32 x 32 pixel e alcune righe di testo, come illustrato nelle immagini seguenti.</span><span class="sxs-lookup"><span data-stu-id="63225-106">The tile view uses a 32 x 32 pixel icon and several lines of text, as shown in the following images.</span></span>  
  
 <span data-ttu-id="63225-107">![Visualizzazione affiancata in un controllo ListView](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")</span><span class="sxs-lookup"><span data-stu-id="63225-107">![Tile View in a ListView Control](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")</span></span>  
<span data-ttu-id="63225-108">Icone e testo di visualizzazione affiancata</span><span class="sxs-lookup"><span data-stu-id="63225-108">Tile view icons and text</span></span>  
  
 <span data-ttu-id="63225-109">Per abilitare la visualizzazione affiancata, impostare la proprietà <xref:System.Windows.Forms.ListView.View%2A> su <xref:System.Windows.Forms.View.Tile>.</span><span class="sxs-lookup"><span data-stu-id="63225-109">To enable tile view, set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Tile>.</span></span> <span data-ttu-id="63225-110">È possibile regolare la dimensione dei riquadri impostando la proprietà <xref:System.Windows.Forms.ListView.TileSize%2A> e il numero di righe di testo visualizzate nel riquadro regolando la raccolta <xref:System.Windows.Forms.ListView.Columns%2A>.</span><span class="sxs-lookup"><span data-stu-id="63225-110">You can adjust the size of the tiles by setting the <xref:System.Windows.Forms.ListView.TileSize%2A> property, and the number of text lines displayed in the tile by adjusting the <xref:System.Windows.Forms.ListView.Columns%2A> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63225-111">La visualizzazione affiancata è disponibile solo in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] quando l'applicazione chiama il metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="63225-111">The tile view is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="63225-112">Nei sistemi operativi precedenti, qualsiasi codice correlato alla visualizzazione affiancata non ha alcun effetto e il controllo <xref:System.Windows.Forms.ListView> viene visualizzato nella visualizzazione Icone grandi.</span><span class="sxs-lookup"><span data-stu-id="63225-112">On earlier operating systems, any code related to the tile view has no effect, and the <xref:System.Windows.Forms.ListView> control displays in the large icon view.</span></span> <span data-ttu-id="63225-113">Per altre informazioni, vedere <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="63225-113">For more information, see <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-set-tile-view-programmatically"></a><span data-ttu-id="63225-114">Per impostare la visualizzazione affiancata a livello di codice</span><span class="sxs-lookup"><span data-stu-id="63225-114">To set tile view programmatically</span></span>  
  
1.  <span data-ttu-id="63225-115">Usare l'enumerazione <xref:System.Windows.Forms.View> del controllo <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="63225-115">Use the <xref:System.Windows.Forms.View> enumeration of the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
    ```vb  
    ListView1.View = View.Tile  
    ```  
  
    ```csharp  
    listView1.View = View.Tile;  
    ```  
  
## <a name="example"></a><span data-ttu-id="63225-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="63225-116">Example</span></span>  
 <span data-ttu-id="63225-117">L'esempio di codice completo seguente illustra la visualizzazione affiancata con riquadri modificati in modo da visualizzare tre righe di testo.</span><span class="sxs-lookup"><span data-stu-id="63225-117">The following complete code example demonstrates Tile view with tiles modified to show three lines of text.</span></span> <span data-ttu-id="63225-118">La dimensione dei riquadri è stata modificata per evitare il ritorno a capo.</span><span class="sxs-lookup"><span data-stu-id="63225-118">The tile size has been adjusted to prevent line-wrapping.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListView.Tiling#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CPP/listviewtilingexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.Tiling#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CS/listviewtilingexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Tiling#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/VB/listviewtilingexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="63225-119">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="63225-119">Compiling the Code</span></span>  
 <span data-ttu-id="63225-120">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="63225-120">This example requires:</span></span>  
  
-   <span data-ttu-id="63225-121">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="63225-121">References to the System and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="63225-122">Un file di icona denominato book.ico nella stessa directory del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="63225-122">An icon file named book.ico in the same directory as the executable file.</span></span>  
  
 <span data-ttu-id="63225-123">Per informazioni sulla compilazione di questo esempio dalla riga di comando per [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], vedere [Compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilazione dalla riga di comando con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="63225-123">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="63225-124">È anche possibile compilare questo esempio in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="63225-124">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="63225-125">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="63225-125">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63225-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63225-126">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.TileSize%2A>  
 [<span data-ttu-id="63225-127">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="63225-127">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="63225-128">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="63225-128">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="63225-129">Funzionalità di Windows XP e controlli di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="63225-129">Windows XP Features and Windows Forms Controls</span></span>](http://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)
