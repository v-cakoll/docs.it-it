---
title: 'Procedura: Creare e impostare un renderer personalizzato per il controllo ToolStrip in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
ms.openlocfilehash: d8a85edf8c001b19191fdfd74d1f9ebdf87024ab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195488"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="8fd83-102">Procedura: Creare e impostare un renderer personalizzato per il controllo ToolStrip in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8fd83-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<xref:System.Windows.Forms.ToolStrip> <span data-ttu-id="8fd83-103">i controlli forniscono un semplice supporto per temi e stili.</span><span class="sxs-lookup"><span data-stu-id="8fd83-103">controls give easy support to themes and styles.</span></span> <span data-ttu-id="8fd83-104">È possibile ottenere un aspetto completamente personalizzato e comportamento (aspetto) impostando il <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> proprietà o il <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> proprietà a un renderer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8fd83-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="8fd83-105">È possibile assegnare i renderer per ogni singolo <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, o <xref:System.Windows.Forms.StatusStrip> controllo, oppure è possibile usare il <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> proprietà influiscono su tutti gli oggetti mediante l'impostazione la <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> proprietà <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8fd83-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> <span data-ttu-id="8fd83-106">Restituisce <xref:System.Windows.Forms.ToolStripRenderMode.Custom> solo se il valore di <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> non è `null`.</span><span class="sxs-lookup"><span data-stu-id="8fd83-106">returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="8fd83-107">Per creare un renderer personalizzato</span><span class="sxs-lookup"><span data-stu-id="8fd83-107">To create a custom renderer</span></span>  
  
1.  <span data-ttu-id="8fd83-108">Estendere il <xref:System.Windows.Forms.ToolStripRenderer> classe.</span><span class="sxs-lookup"><span data-stu-id="8fd83-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2.  <span data-ttu-id="8fd83-109">Implementare desiderato per il rendering personalizzata eseguendo l'override appropriato *su...*</span><span class="sxs-lookup"><span data-stu-id="8fd83-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="8fd83-110">membri</span><span class="sxs-lookup"><span data-stu-id="8fd83-110">members</span></span>  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)   
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
    ```  
  
    ```csharp  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
    ```  
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="8fd83-111">Per impostare il renderer personalizzato sia il programma di rendering corrente</span><span class="sxs-lookup"><span data-stu-id="8fd83-111">To set the custom renderer to be the current renderer</span></span>  
  
1.  <span data-ttu-id="8fd83-112">Per impostare il renderer personalizzato per uno <xref:System.Windows.Forms.ToolStrip>, impostare il <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> proprietà per il renderer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8fd83-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2.  <span data-ttu-id="8fd83-113">O impostare il renderer personalizzato per tutti i <xref:System.Windows.Forms.ToolStrip> classi contenute all'interno dell'applicazione: Impostare il <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> proprietà del renderer personalizzati e il <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> proprietà <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span><span class="sxs-lookup"><span data-stu-id="8fd83-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8fd83-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fd83-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [<span data-ttu-id="8fd83-115">Panoramica del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="8fd83-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="8fd83-116">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="8fd83-116">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="8fd83-117">Riepilogo della tecnologia ToolStrip</span><span class="sxs-lookup"><span data-stu-id="8fd83-117">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
