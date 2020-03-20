---
title: 'Procedura: eseguire un disegno personalizzato di un controllo ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], custom drawing
- drawing [Windows Forms], owner
- ProfessionalColorTable class [Windows Forms], overriding
- examples [Windows Forms], toolbars
- drawing [Windows Forms], custom
- toolbars [Windows Forms], changing colors
- ToolStrip control [Windows Forms], drawing
- ToolStrip control [Windows Forms], changing colors
- custom drawing
- owner drawing
ms.assetid: 94e7d7bd-a752-441c-b5b3-7acf98881163
ms.openlocfilehash: a9f603efdb4b4a5f68154da9c6a8bd05b55b8f46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182218"
---
# <a name="how-to-custom-draw-a-toolstrip-control"></a><span data-ttu-id="76fd3-102">Procedura: eseguire un disegno personalizzato di un controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="76fd3-102">How to: Custom Draw a ToolStrip Control</span></span>
<span data-ttu-id="76fd3-103">Ai controlli <xref:System.Windows.Forms.ToolStrip> sono associate le classi di rendering (disegno) seguenti:</span><span class="sxs-lookup"><span data-stu-id="76fd3-103">The <xref:System.Windows.Forms.ToolStrip> controls have the following associated rendering (painting) classes:</span></span>  
  
- <span data-ttu-id="76fd3-104"><xref:System.Windows.Forms.ToolStripSystemRenderer> fornisce l'aspetto e lo stile del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="76fd3-104"><xref:System.Windows.Forms.ToolStripSystemRenderer> provides the appearance and style of your operating system.</span></span>  
  
- <span data-ttu-id="76fd3-105"><xref:System.Windows.Forms.ToolStripProfessionalRenderer> fornisce l'aspetto e lo stile di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="76fd3-105"><xref:System.Windows.Forms.ToolStripProfessionalRenderer> provides the appearance and style of Microsoft Office.</span></span>  
  
- <span data-ttu-id="76fd3-106"><xref:System.Windows.Forms.ToolStripRenderer> è la classe di base astratta per le altre due classi di rendering.</span><span class="sxs-lookup"><span data-stu-id="76fd3-106"><xref:System.Windows.Forms.ToolStripRenderer> is the abstract base class for the other two rendering classes.</span></span>  
  
 <span data-ttu-id="76fd3-107">Per disegnare un controllo <xref:System.Windows.Forms.ToolStrip> personalizzato (modalità nota anche come "Owner Draw"), è possibile eseguire l'override di una delle classi renderer e modificare un aspetto della logica di rendering.</span><span class="sxs-lookup"><span data-stu-id="76fd3-107">To custom draw (also known as owner draw) a <xref:System.Windows.Forms.ToolStrip>, you can override one of the renderer classes and change an aspect of the rendering logic.</span></span>  
  
 <span data-ttu-id="76fd3-108">Le procedure seguenti descrivono vari aspetti del disegno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="76fd3-108">The following procedures describe various aspects of custom drawing.</span></span>  
  
### <a name="to-switch-between-the-provided-renderers"></a><span data-ttu-id="76fd3-109">Per passare da un renderer fornito all'altro</span><span class="sxs-lookup"><span data-stu-id="76fd3-109">To switch between the provided renderers</span></span>  
  
- <span data-ttu-id="76fd3-110">Impostare la proprietà <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> sul valore <xref:System.Windows.Forms.ToolStripRenderMode> desiderato.</span><span class="sxs-lookup"><span data-stu-id="76fd3-110">Set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to the <xref:System.Windows.Forms.ToolStripRenderMode> value you want.</span></span>  
  
     <span data-ttu-id="76fd3-111">Con <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> la proprietà statica <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> determina il renderer per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="76fd3-111">With <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>, the static <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> determines the renderer for your application.</span></span> <span data-ttu-id="76fd3-112">Gli altri valori di <xref:System.Windows.Forms.ToolStripRenderMode> sono <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional> e <xref:System.Windows.Forms.ToolStripRenderMode.System>.</span><span class="sxs-lookup"><span data-stu-id="76fd3-112">The other values of <xref:System.Windows.Forms.ToolStripRenderMode> are <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional>, and <xref:System.Windows.Forms.ToolStripRenderMode.System>.</span></span>  
  
### <a name="to-change-the-microsoft-officestyle-borders-to-straight"></a><span data-ttu-id="76fd3-113">Per usare bordi diritti al posto dello stile Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="76fd3-113">To change the Microsoft Office–style borders to straight</span></span>  
  
- <span data-ttu-id="76fd3-114">Eseguire l'override di <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, ma senza chiamare la classe di base.</span><span class="sxs-lookup"><span data-stu-id="76fd3-114">Override <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, but do not call the base class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="76fd3-115">Esiste una versione di questo metodo per <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer> e <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span><span class="sxs-lookup"><span data-stu-id="76fd3-115">There is a version of this method for <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer>, and <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span></span>  
  
### <a name="to-change-the-professionalcolortable"></a><span data-ttu-id="76fd3-116">Per modificare la classe ProfessionalColorTable</span><span class="sxs-lookup"><span data-stu-id="76fd3-116">To change the ProfessionalColorTable</span></span>  
  
- <span data-ttu-id="76fd3-117">Eseguire l'override di <xref:System.Windows.Forms.ProfessionalColorTable> e cambiare i colori desiderati.</span><span class="sxs-lookup"><span data-stu-id="76fd3-117">Override <xref:System.Windows.Forms.ProfessionalColorTable> and change the colors you want.</span></span>  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As _  
    System.EventArgs) Handles Me.Load  
        Dim t As MyColorTable = New MyColorTable  
        ToolStrip1.Renderer = New ToolStripProfessionalRenderer(t)  
    End Sub  
  
    Class MyColorTable
    Inherits ProfessionalColorTable  
  
    Public Overrides ReadOnly Property ButtonPressedGradientBegin() As Color  
        Get  
            Return Color.Red  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonPressedGradientMiddle() _  
    As System.Drawing.Color  
        Get  
            Return Color.Blue  
        End Get  
            End Property  
  
    Public Overrides ReadOnly Property ButtonPressedGradientEnd() _  
    As System.Drawing.Color  
        Get  
            Return Color.Green  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientBegin() _  
    As Color  
        Get  
            Return Color.Yellow  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientMiddle() As System.Drawing.Color  
        Get  
            Return Color.Orange  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientEnd() _  
    As System.Drawing.Color  
        Get  
            Return Color.Violet  
        End Get  
    End Property  
    End Class  
    ```  
  
### <a name="to-change-the-rendering-for-all-toolstrip-controls-in-your-application"></a><span data-ttu-id="76fd3-118">Per modificare il rendering di tutti i controlli ToolStrip nell'applicazione</span><span class="sxs-lookup"><span data-stu-id="76fd3-118">To change the rendering for all ToolStrip controls in your application</span></span>  
  
1. <span data-ttu-id="76fd3-119">Usare la proprietà <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> per scegliere uno dei renderer forniti.</span><span class="sxs-lookup"><span data-stu-id="76fd3-119">Use the <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> property to choose one of the provided renderers.</span></span>  
  
2. <span data-ttu-id="76fd3-120">Usare <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> per assegnare un renderer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="76fd3-120">Use <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> to assign a custom renderer.</span></span>  
  
3. <span data-ttu-id="76fd3-121">Accertarsi che <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> sia impostata sul valore predefinito di <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span><span class="sxs-lookup"><span data-stu-id="76fd3-121">Ensure that <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> is set to the default value of <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
### <a name="to-turn-off-the-microsoft-office-colors-for-the-entire-application"></a><span data-ttu-id="76fd3-122">Per disattivare i colori di Microsoft Office in tutta l'applicazione</span><span class="sxs-lookup"><span data-stu-id="76fd3-122">To turn off the Microsoft Office colors for the entire application</span></span>  
  
- <span data-ttu-id="76fd3-123">Impostare <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> su `false`.</span><span class="sxs-lookup"><span data-stu-id="76fd3-123">Set <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> to `false`.</span></span>  
  
### <a name="to-turn-off-the-microsoft-office-colors-for-one-toolstrip-control"></a><span data-ttu-id="76fd3-124">Per disattivare i colori di Microsoft Office in un controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="76fd3-124">To turn off the Microsoft Office colors for one ToolStrip control</span></span>  
  
- <span data-ttu-id="76fd3-125">Usare codice simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="76fd3-125">Use code similar to the following code example.</span></span>  
  
    ```vb  
    Dim colorTable As ProfessionalColorTable()  
    colorTable.UseSystemColors = True  
    Dim toolStrip.Renderer As ToolStripProfessionalRenderer(colorTable)  
    ```  
  
    ```csharp  
    ProfessionalColorTable colorTable = new ProfessionalColorTable();  
    colorTable.UseSystemColors = true;  
    toolStrip.Renderer = new ToolStripProfessionalRenderer(colorTable);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="76fd3-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76fd3-126">See also</span></span>

- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripRenderer>
- [<span data-ttu-id="76fd3-127">Controlli con supporto predefinito per il disegno da parte del proprietario</span><span class="sxs-lookup"><span data-stu-id="76fd3-127">Controls with Built-In Owner-Drawing Support</span></span>](controls-with-built-in-owner-drawing-support.md)
- [<span data-ttu-id="76fd3-128">Procedura: creare e impostare un renderer personalizzato per il controllo ToolStrip in Windows Form</span><span class="sxs-lookup"><span data-stu-id="76fd3-128">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)
- [<span data-ttu-id="76fd3-129">Cenni preliminari sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="76fd3-129">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
