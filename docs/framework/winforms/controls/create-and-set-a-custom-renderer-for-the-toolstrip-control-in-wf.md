---
title: 'Procedura: creare e impostare un renderer personalizzato per il controllo ToolStripHow to: Create and Set a Custom Renderer for the ToolStrip Control'
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
ms.openlocfilehash: 49db0d785155f19b7220ac64011eaf4253aaa7e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182400"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="52c06-102">Procedura: creare e impostare un renderer personalizzato per il controllo ToolStrip in Windows Form</span><span class="sxs-lookup"><span data-stu-id="52c06-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<span data-ttu-id="52c06-103"><xref:System.Windows.Forms.ToolStrip>controlli forniscono un facile supporto a temi e stili.</span><span class="sxs-lookup"><span data-stu-id="52c06-103"><xref:System.Windows.Forms.ToolStrip> controls give easy support to themes and styles.</span></span> <span data-ttu-id="52c06-104">È possibile ottenere un aspetto e un comportamento completamente <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> personalizzati <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> (aspetto) impostando la proprietà o la proprietà su un renderer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="52c06-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="52c06-105">È possibile assegnare renderer <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip>a <xref:System.Windows.Forms.StatusStrip> ogni singolo <xref:System.Windows.Forms.ToolStrip>controllo , <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> , , o oppure utilizzare la proprietà per modificare tutti gli oggetti impostando la <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> proprietà su <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="52c06-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52c06-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A>restituisce <xref:System.Windows.Forms.ToolStripRenderMode.Custom> solo se <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> il `null`valore di non è .</span><span class="sxs-lookup"><span data-stu-id="52c06-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="52c06-107">Per creare un renderer personalizzatoTo create a custom renderer</span><span class="sxs-lookup"><span data-stu-id="52c06-107">To create a custom renderer</span></span>  
  
1. <span data-ttu-id="52c06-108">Estendi la <xref:System.Windows.Forms.ToolStripRenderer> classe.</span><span class="sxs-lookup"><span data-stu-id="52c06-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2. <span data-ttu-id="52c06-109">Implementare il rendering personalizzato desiderato eseguendo l'override appropriato *On...*</span><span class="sxs-lookup"><span data-stu-id="52c06-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="52c06-110">Membri di</span><span class="sxs-lookup"><span data-stu-id="52c06-110">members</span></span>  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="52c06-111">Per impostare il renderer personalizzato come renderer correnteTo set the custom renderer to be the current renderer</span><span class="sxs-lookup"><span data-stu-id="52c06-111">To set the custom renderer to be the current renderer</span></span>  
  
1. <span data-ttu-id="52c06-112">Per impostare il renderer personalizzato per uno, <xref:System.Windows.Forms.ToolStrip>impostare la <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> proprietà sul renderer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="52c06-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. <span data-ttu-id="52c06-113">In alternativa, per impostare <xref:System.Windows.Forms.ToolStrip> il renderer personalizzato <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> per tutte le classi contenute <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>nell'applicazione: impostare la proprietà sul renderer personalizzato e impostare la proprietà su <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> .</span><span class="sxs-lookup"><span data-stu-id="52c06-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="52c06-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52c06-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [<span data-ttu-id="52c06-115">Cenni preliminari sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="52c06-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="52c06-116">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="52c06-116">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="52c06-117">Riepilogo della tecnologia ToolStrip</span><span class="sxs-lookup"><span data-stu-id="52c06-117">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
