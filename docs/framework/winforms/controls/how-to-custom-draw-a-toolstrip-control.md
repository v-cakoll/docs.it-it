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
# <a name="how-to-custom-draw-a-toolstrip-control"></a>Procedura: eseguire un disegno personalizzato di un controllo ToolStrip
Ai controlli <xref:System.Windows.Forms.ToolStrip> sono associate le classi di rendering (disegno) seguenti:  
  
- <xref:System.Windows.Forms.ToolStripSystemRenderer> fornisce l'aspetto e lo stile del sistema operativo.  
  
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer> fornisce l'aspetto e lo stile di Microsoft Office.  
  
- <xref:System.Windows.Forms.ToolStripRenderer> è la classe di base astratta per le altre due classi di rendering.  
  
 Per disegnare un controllo <xref:System.Windows.Forms.ToolStrip> personalizzato (modalità nota anche come "Owner Draw"), è possibile eseguire l'override di una delle classi renderer e modificare un aspetto della logica di rendering.  
  
 Le procedure seguenti descrivono vari aspetti del disegno personalizzato.  
  
### <a name="to-switch-between-the-provided-renderers"></a>Per passare da un renderer fornito all'altro  
  
- Impostare la proprietà <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> sul valore <xref:System.Windows.Forms.ToolStripRenderMode> desiderato.  
  
     Con <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> la proprietà statica <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> determina il renderer per l'applicazione. Gli altri valori di <xref:System.Windows.Forms.ToolStripRenderMode> sono <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional> e <xref:System.Windows.Forms.ToolStripRenderMode.System>.  
  
### <a name="to-change-the-microsoft-officestyle-borders-to-straight"></a>Per usare bordi diritti al posto dello stile Microsoft Office  
  
- Eseguire l'override di <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, ma senza chiamare la classe di base.  
  
> [!NOTE]
> Esiste una versione di questo metodo per <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer> e <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.  
  
### <a name="to-change-the-professionalcolortable"></a>Per modificare la classe ProfessionalColorTable  
  
- Eseguire l'override di <xref:System.Windows.Forms.ProfessionalColorTable> e cambiare i colori desiderati.  
  
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
  
### <a name="to-change-the-rendering-for-all-toolstrip-controls-in-your-application"></a>Per modificare il rendering di tutti i controlli ToolStrip nell'applicazione  
  
1. Usare la proprietà <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> per scegliere uno dei renderer forniti.  
  
2. Usare <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> per assegnare un renderer personalizzato.  
  
3. Accertarsi che <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> sia impostata sul valore predefinito di <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.  
  
### <a name="to-turn-off-the-microsoft-office-colors-for-the-entire-application"></a>Per disattivare i colori di Microsoft Office in tutta l'applicazione  
  
- Impostare <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> su `false`.  
  
### <a name="to-turn-off-the-microsoft-office-colors-for-one-toolstrip-control"></a>Per disattivare i colori di Microsoft Office in un controllo ToolStrip  
  
- Usare codice simile all'esempio seguente.  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripRenderer>
- [Controlli con supporto predefinito per il disegno da parte del proprietario](controls-with-built-in-owner-drawing-support.md)
- [Procedura: creare e impostare un renderer personalizzato per il controllo ToolStrip in Windows Form](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)
- [Cenni preliminari sul controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
