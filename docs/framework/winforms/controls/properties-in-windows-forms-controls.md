---
title: Proprietà dei controlli Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
ms.openlocfilehash: e531b80cffabb94d2589383936a425b740c9cc07
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012504"
---
# <a name="properties-in-windows-forms-controls"></a>Proprietà dei controlli Windows Form
Un controllo Windows Forms eredita molte proprietà dalla classe di base <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Queste sono incluse proprietà, ad esempio <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>e molti altri. Per informazioni dettagliate sulle proprietà ereditate, vedere <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
 È possibile eseguire l'override delle proprietà ereditate dal controllo nonché definirne di nuove.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Definizione di una proprietà](defining-a-property-in-windows-forms-controls.md)  
 Viene illustrato come implementare una proprietà per un controllo o un componente personalizzato e come integrare la proprietà nell'ambiente di progettazione.  
  
 [Definizione dei valori predefiniti utilizzando i metodi ShouldSerialize e Reset](defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 Viene illustrato come definire valori di proprietà predefiniti per un controllo o un componente personalizzato.  
  
 [Eventi di modifica delle proprietà](property-changed-events.md)  
 Viene descritto come attivare le notifiche di modifiche alle proprietà quando un valore di una proprietà viene modificato.  
  
 [Procedura: Esporre le proprietà dei controlli costitutivi](how-to-expose-properties-of-constituent-controls.md)  
 Viene illustrato come esporre le proprietà dei controlli che fanno parte di un controllo composito personalizzato.  
  
 [Implementazione dei metodi nei controlli personalizzati](method-implementation-in-custom-controls.md)  
 Viene descritto come implementare metodi nei controlli e nei componenti personalizzati.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Forms.UserControl>  
 Viene descritta la classe base per l'implementazione dei controlli compositi.  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 Viene descritto l'attributo che specifica il <xref:System.ComponentModel.TypeConverter> da utilizzare per un tipo di proprietà personalizzato.  
  
 <xref:System.ComponentModel.EditorAttribute>  
 Viene descritto l'attributo che specifica il <xref:System.Drawing.Design.UITypeEditor> da utilizzare per una proprietà personalizzata.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Attributi nei controlli Windows Forms](attributes-in-windows-forms-controls.md)  
 Descrive gli attributi che è possibile applicare alle proprietà o ad altri membri e componenti dei controlli personalizzati.  
  
 [Attributi per componenti in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))  
 Elenca gli attributi dei metadati da applicare ai componenti e ai controlli in modo che vengano visualizzati correttamente in fase di progettazione nelle finestre di progettazione visiva.  
  
 [Estensione del supporto in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))  
 Descrive come implementare classi, quali editor e finestre di progettazione, che forniscono supporto in fase di progettazione.
