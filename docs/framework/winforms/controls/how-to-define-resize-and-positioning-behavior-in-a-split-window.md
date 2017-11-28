---
title: 'Procedura: definire il ridimensionamento e il posizionamento in una finestra divisa'
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
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: db4a99c7dae7783e8ea51f43ad51fcd2214997e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a><span data-ttu-id="28b5b-102">Procedura: definire il ridimensionamento e il posizionamento in una finestra divisa</span><span class="sxs-lookup"><span data-stu-id="28b5b-102">How to: Define Resize and Positioning Behavior in a Split Window</span></span>
<span data-ttu-id="28b5b-103">I pannelli del <xref:System.Windows.Forms.SplitContainer> controllo si prestano bene a essere ridimensionati e modificati dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="28b5b-103">The panels of the <xref:System.Windows.Forms.SplitContainer> control lend themselves well to being resized and manipulated by users.</span></span> <span data-ttu-id="28b5b-104">Tuttavia, verranno indicate le ore verrà quando si desidera controllare a livello di codice della barra di divisione, in cui è posizionato e in quale misura può essere spostato.</span><span class="sxs-lookup"><span data-stu-id="28b5b-104">However, there will be times when you will want to programmatically control the splitter—where it is positioned and to what degree it can be moved.</span></span>  
  
 <span data-ttu-id="28b5b-105">Il <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> proprietà e le altre proprietà di <xref:System.Windows.Forms.SplitContainer> controllo offrono un controllo preciso il comportamento dell'interfaccia utente in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="28b5b-105">The <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property and the other properties on the <xref:System.Windows.Forms.SplitContainer> control give you precise control over the behavior of your user interface to suit your needs.</span></span> <span data-ttu-id="28b5b-106">Queste proprietà sono elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="28b5b-106">These properties are listed in the following table.</span></span>  
  
|<span data-ttu-id="28b5b-107">Nome</span><span class="sxs-lookup"><span data-stu-id="28b5b-107">Name</span></span>|<span data-ttu-id="28b5b-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28b5b-108">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="28b5b-109">Proprietà <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A></span><span class="sxs-lookup"><span data-stu-id="28b5b-109"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property</span></span>|<span data-ttu-id="28b5b-110">Determina se la barra di divisione può essere spostata tramite mouse o tastiera.</span><span class="sxs-lookup"><span data-stu-id="28b5b-110">Determines if the splitter is movable by means of the keyboard or mouse.</span></span>|  
|<span data-ttu-id="28b5b-111">Proprietà <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A></span><span class="sxs-lookup"><span data-stu-id="28b5b-111"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> property</span></span>|<span data-ttu-id="28b5b-112">Determina la distanza in pixel dal bordo sinistro o superiore alla barra di divisione mobile.</span><span class="sxs-lookup"><span data-stu-id="28b5b-112">Determines the distance in pixels from the left or upper edge to the movable splitter bar.</span></span>|  
|<span data-ttu-id="28b5b-113">Proprietà <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A></span><span class="sxs-lookup"><span data-stu-id="28b5b-113"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property</span></span>|<span data-ttu-id="28b5b-114">Determina la distanza minima, in pixel, che la barra di divisione può essere spostato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="28b5b-114">Determines the minimum distance, in pixels, that the splitter can be moved by the user.</span></span>|  
  
 <span data-ttu-id="28b5b-115">Nell'esempio seguente viene modificato il <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> proprietà per creare un effetto "aggancio divisione"; quando l'utente trascina la barra di divisione, viene incrementata in unità di 10 pixel anziché il valore predefinito 1.</span><span class="sxs-lookup"><span data-stu-id="28b5b-115">The example below modifies the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to create a "snapping splitter" effect; when the user drags the splitter, it increments in units of 10 pixels rather than the default 1.</span></span>  
  
### <a name="to-define-splitcontainer-resize-behavior"></a><span data-ttu-id="28b5b-116">Per definire il comportamento di ridimensionamento SplitContainer</span><span class="sxs-lookup"><span data-stu-id="28b5b-116">To define SplitContainer resize behavior</span></span>  
  
1.  <span data-ttu-id="28b5b-117">In una routine, impostare il <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> proprietà sulla dimensione desiderata, in modo da ottenuta il comportamento della barra di divisione 'snap'.</span><span class="sxs-lookup"><span data-stu-id="28b5b-117">In a procedure, set the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to the desired size, so that the 'snapping' behavior of the splitter is achieved.</span></span>  
  
     <span data-ttu-id="28b5b-118">Nell'esempio di codice seguente all'interno del form <xref:System.Windows.Forms.Form.Load> evento, la barra di divisione all'interno di <xref:System.Windows.Forms.SplitContainer> NFS è impostata su 10 pixel quando trascinato di spostamento.</span><span class="sxs-lookup"><span data-stu-id="28b5b-118">In the following code example, within the form's <xref:System.Windows.Forms.Form.Load> event, the splitter within the <xref:System.Windows.Forms.SplitContainer> control is set to jump 10 pixels when dragged.</span></span>  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     <span data-ttu-id="28b5b-119">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]) Inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="28b5b-119">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     <span data-ttu-id="28b5b-120">Spostare leggermente la barra di divisione verso sinistra o destra non avrà alcun effetto visibile. Tuttavia, quando il puntatore del mouse esce 10 pixel in direzione orizzontale, la barra di divisione verrà bloccata la nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="28b5b-120">Moving the splitter slightly to the left or right will have no discernible effect; however, when the mouse pointer goes 10 pixels in either direction, the splitter will snap to the new position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28b5b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28b5b-121">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
