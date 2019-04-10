---
title: 'Procedura: Definire il ridimensionamento e il posizionamento in una finestra divisa'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
ms.openlocfilehash: 8cdcfdfaa135a92ed6a6e96d4a72de2c97f2493d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59328673"
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a><span data-ttu-id="8788a-102">Procedura: Definire il ridimensionamento e il posizionamento in una finestra divisa</span><span class="sxs-lookup"><span data-stu-id="8788a-102">How to: Define Resize and Positioning Behavior in a Split Window</span></span>
<span data-ttu-id="8788a-103">I pannelli del <xref:System.Windows.Forms.SplitContainer> controllo si prestano bene a viene ridimensionata e modificati dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="8788a-103">The panels of the <xref:System.Windows.Forms.SplitContainer> control lend themselves well to being resized and manipulated by users.</span></span> <span data-ttu-id="8788a-104">Tuttavia, vi saranno si vogliano verrà a livello di programmazione della barra di divisione, in cui è posizionato e in che misura può essere spostato.</span><span class="sxs-lookup"><span data-stu-id="8788a-104">However, there will be times when you will want to programmatically control the splitter—where it is positioned and to what degree it can be moved.</span></span>  
  
 <span data-ttu-id="8788a-105">Il <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> proprietà e le altre proprietà di <xref:System.Windows.Forms.SplitContainer> controllo consentono di controllare con precisione il comportamento dell'interfaccia utente in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="8788a-105">The <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property and the other properties on the <xref:System.Windows.Forms.SplitContainer> control give you precise control over the behavior of your user interface to suit your needs.</span></span> <span data-ttu-id="8788a-106">Queste proprietà sono elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8788a-106">These properties are listed in the following table.</span></span>  
  
|<span data-ttu-id="8788a-107">Nome</span><span class="sxs-lookup"><span data-stu-id="8788a-107">Name</span></span>|<span data-ttu-id="8788a-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8788a-108">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> <span data-ttu-id="8788a-109">proprietà</span><span class="sxs-lookup"><span data-stu-id="8788a-109">property</span></span>|<span data-ttu-id="8788a-110">Determina se la barra di divisione è mobile tramite mouse o tastiera.</span><span class="sxs-lookup"><span data-stu-id="8788a-110">Determines if the splitter is movable by means of the keyboard or mouse.</span></span>|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> <span data-ttu-id="8788a-111">proprietà</span><span class="sxs-lookup"><span data-stu-id="8788a-111">property</span></span>|<span data-ttu-id="8788a-112">Determina la distanza in pixel dal bordo sinistro o superiore per la barra di divisione mobile.</span><span class="sxs-lookup"><span data-stu-id="8788a-112">Determines the distance in pixels from the left or upper edge to the movable splitter bar.</span></span>|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> <span data-ttu-id="8788a-113">proprietà</span><span class="sxs-lookup"><span data-stu-id="8788a-113">property</span></span>|<span data-ttu-id="8788a-114">Determina la distanza minima, in pixel, che la barra di divisione può essere spostato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="8788a-114">Determines the minimum distance, in pixels, that the splitter can be moved by the user.</span></span>|  
  
 <span data-ttu-id="8788a-115">Nell'esempio seguente viene modificato il <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> proprietà per creare un effetto "allineamento splitter"; quando l'utente trascina la barra di divisione, viene automaticamente incrementato in unità pari a 10 pixel anziché il valore predefinito 1.</span><span class="sxs-lookup"><span data-stu-id="8788a-115">The example below modifies the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to create a "snapping splitter" effect; when the user drags the splitter, it increments in units of 10 pixels rather than the default 1.</span></span>  
  
### <a name="to-define-splitcontainer-resize-behavior"></a><span data-ttu-id="8788a-116">Per definire il comportamento di ridimensionamento SplitContainer</span><span class="sxs-lookup"><span data-stu-id="8788a-116">To define SplitContainer resize behavior</span></span>  
  
1. <span data-ttu-id="8788a-117">In una procedura, impostare il <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> proprietà sulla dimensione desiderata, in modo da ottenuta il comportamento della barra di divisione 'snap'.</span><span class="sxs-lookup"><span data-stu-id="8788a-117">In a procedure, set the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to the desired size, so that the 'snapping' behavior of the splitter is achieved.</span></span>  
  
     <span data-ttu-id="8788a-118">Nell'esempio di codice seguente, all'interno del form <xref:System.Windows.Forms.Form.Load> evento, la barra di divisione all'interno di <xref:System.Windows.Forms.SplitContainer> NFS è impostata su jump 10 pixel quando trascinata.</span><span class="sxs-lookup"><span data-stu-id="8788a-118">In the following code example, within the form's <xref:System.Windows.Forms.Form.Load> event, the splitter within the <xref:System.Windows.Forms.SplitContainer> control is set to jump 10 pixels when dragged.</span></span>  
  
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
  
     <span data-ttu-id="8788a-119">(Visual C#) Inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="8788a-119">(Visual C#) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     <span data-ttu-id="8788a-120">Spostare leggermente la barra di divisione verso sinistra o destra non avranno alcun effetto visibile. Tuttavia, quando il puntatore del mouse esce 10 pixel in direzione orizzontale, la barra di divisione verrà bloccato per la nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="8788a-120">Moving the splitter slightly to the left or right will have no discernible effect; however, when the mouse pointer goes 10 pixels in either direction, the splitter will snap to the new position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8788a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8788a-121">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
