---
title: "Proprietà dei controlli Windows Form"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d5de09635fb92b46a2c0f89427ad03449de6bd53
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="properties-in-windows-forms-controls"></a>Proprietà dei controlli Windows Form
Un controllo Windows Form eredita molte proprietà della classe base <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Queste sono incluse proprietà, ad esempio <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>e molti altri. Per informazioni dettagliate sulle proprietà ereditate, vedere <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
 È possibile eseguire l'override delle proprietà ereditate dal controllo nonché definirne di nuove.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Definizione di una proprietà](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 Viene illustrato come implementare una proprietà per un controllo o un componente personalizzato e come integrare la proprietà nell'ambiente di progettazione.  
  
 [Definizione dei valori predefiniti utilizzando i metodi ShouldSerialize e Reset](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 Viene illustrato come definire valori di proprietà predefiniti per un controllo o un componente personalizzato.  
  
 [Eventi di modifica delle proprietà](../../../../docs/framework/winforms/controls/property-changed-events.md)  
 Viene descritto come attivare le notifiche di modifiche alle proprietà quando un valore di una proprietà viene modificato.  
  
 [Procedura: esporre le proprietà dei controlli costitutivi](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md)  
 Viene illustrato come esporre le proprietà dei controlli che fanno parte di un controllo composito personalizzato.  
  
 [Implementazione dei metodi nei controlli personalizzati](../../../../docs/framework/winforms/controls/method-implementation-in-custom-controls.md)  
 Viene descritto come implementare metodi nei controlli e nei componenti personalizzati.  
  
## <a name="reference"></a>Riferimento  
 <xref:System.Windows.Forms.UserControl>  
 Viene descritta la classe base per l'implementazione dei controlli compositi.  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 Viene descritto l'attributo che specifica il <xref:System.ComponentModel.TypeConverter> da usare per un tipo di proprietà personalizzata.  
  
 <xref:System.ComponentModel.EditorAttribute>  
 Viene descritto l'attributo che specifica il <xref:System.Drawing.Design.UITypeEditor> da utilizzare per una proprietà personalizzata.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Attributi nei controlli Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 Descrive gli attributi che è possibile applicare alle proprietà o ad altri membri e componenti dei controlli personalizzati.  
  
 [Attributi per componenti in fase di progettazione](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3)  
 Elenca gli attributi dei metadati da applicare ai componenti e ai controlli in modo che vengano visualizzati correttamente in fase di progettazione nelle finestre di progettazione visiva.  
  
 [Estensione del supporto in fase di progettazione](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 Descrive come implementare classi, quali editor e finestre di progettazione, che forniscono supporto in fase di progettazione.
