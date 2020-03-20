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
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>Procedura: creare e impostare un renderer personalizzato per il controllo ToolStrip in Windows Form
<xref:System.Windows.Forms.ToolStrip>controlli forniscono un facile supporto a temi e stili. È possibile ottenere un aspetto e un comportamento completamente <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> personalizzati <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> (aspetto) impostando la proprietà o la proprietà su un renderer personalizzato.  
  
 È possibile assegnare renderer <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip>a <xref:System.Windows.Forms.StatusStrip> ogni singolo <xref:System.Windows.Forms.ToolStrip>controllo , <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> , , o oppure utilizzare la proprietà per modificare tutti gli oggetti impostando la <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> proprietà su <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.  
  
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>restituisce <xref:System.Windows.Forms.ToolStripRenderMode.Custom> solo se <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> il `null`valore di non è .  
  
### <a name="to-create-a-custom-renderer"></a>Per creare un renderer personalizzatoTo create a custom renderer  
  
1. Estendi la <xref:System.Windows.Forms.ToolStripRenderer> classe.  
  
2. Implementare il rendering personalizzato desiderato eseguendo l'override appropriato *On...* Membri di  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>Per impostare il renderer personalizzato come renderer correnteTo set the custom renderer to be the current renderer  
  
1. Per impostare il renderer personalizzato per uno, <xref:System.Windows.Forms.ToolStrip>impostare la <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> proprietà sul renderer personalizzato.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. In alternativa, per impostare <xref:System.Windows.Forms.ToolStrip> il renderer personalizzato <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> per tutte le classi contenute <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>nell'applicazione: impostare la proprietà sul renderer personalizzato e impostare la proprietà su <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> .  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [Cenni preliminari sul controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Architettura del controllo ToolStrip](toolstrip-control-architecture.md)
- [Riepilogo della tecnologia ToolStrip](toolstrip-technology-summary.md)
