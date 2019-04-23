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
ms.openlocfilehash: ca1a7444c029632f83b1600e5855a13c83777594
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296381"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>Procedura: Creare e impostare un renderer personalizzato per il controllo ToolStrip in Windows Forms
<xref:System.Windows.Forms.ToolStrip> i controlli forniscono un semplice supporto per temi e stili. È possibile ottenere un aspetto completamente personalizzato e comportamento (aspetto) impostando il <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> proprietà o il <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> proprietà a un renderer personalizzato.  
  
 È possibile assegnare i renderer per ogni singolo <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, o <xref:System.Windows.Forms.StatusStrip> controllo, oppure è possibile usare il <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> proprietà influiscono su tutti gli oggetti mediante l'impostazione la <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> proprietà <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> Restituisce <xref:System.Windows.Forms.ToolStripRenderMode.Custom> solo se il valore di <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> non è `null`.  
  
### <a name="to-create-a-custom-renderer"></a>Per creare un renderer personalizzato  
  
1. Estendere il <xref:System.Windows.Forms.ToolStripRenderer> classe.  
  
2. Implementare desiderato per il rendering personalizzata eseguendo l'override appropriato *su...* membri  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>Per impostare il renderer personalizzato sia il programma di rendering corrente  
  
1. Per impostare il renderer personalizzato per uno <xref:System.Windows.Forms.ToolStrip>, impostare il <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> proprietà per il renderer personalizzato.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. O impostare il renderer personalizzato per tutti i <xref:System.Windows.Forms.ToolStrip> classi contenute all'interno dell'applicazione: Impostare il <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> proprietà del renderer personalizzati e il <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> proprietà <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.  
  
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
- [Panoramica sul controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Architettura del controllo ToolStrip](toolstrip-control-architecture.md)
- [Riepilogo della tecnologia ToolStrip](toolstrip-technology-summary.md)
