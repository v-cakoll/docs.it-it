---
title: Eventi per proprietà modificate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
ms.openlocfilehash: f4e6a6267df88cdd33a58093f276c6005209f38d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="property-changed-events"></a>Eventi per proprietà modificate
Se si desidera che il controllo per inviare notifiche quando una proprietà denominata *PropertyName* , definire un evento denominato *PropertyName* `Changed` e un metodo denominato `On` *PropertyName* `Changed` che genera l'evento. La convenzione di denominazione in Windows Form consiste nell'aggiungere la parola *Changed* per il nome della proprietà. Il tipo del delegato di evento associata per gli eventi di modifica della proprietà è <xref:System.EventHandler>, e il tipo di dati di evento è <xref:System.EventArgs>. La classe di base <xref:System.Windows.Forms.Control> definisce molti eventi di modifica della proprietà, ad esempio <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>e altri. Per informazioni generali sugli eventi, vedere [eventi](../../../../docs/standard/events/index.md) e [eventi nei controlli Windows Form](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md).  
  
 Gli eventi di modifica della proprietà sono utili perché consentono ai consumer di un controllo di associare gestori di eventi che rispondono alla modifica. Se il controllo deve rispondere a un evento di modifica della proprietà da esso generato, eseguire l'override corrispondente `On` *PropertyName* `Changed` metodo anziché associare un delegato all'evento. Un controllo in genere risponde a un evento di modifica della proprietà eseguendo l'aggiornamento di altre proprietà o ridisegnando alcuni o tutti della relativa superficie di disegno.  
  
 L'esempio seguente mostra come `FlashTrackBar` controllo personalizzato risponda ad alcuni degli eventi di modifica della proprietà che eredita da <xref:System.Windows.Forms.Control>. Per l'esempio completo, vedere [procedura: creare un Windows Form controllo che mostra lo stato di avanzamento](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 [Eventi](../../../../docs/standard/events/index.md)  
 [Eventi dei controlli di Windows Form](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [Proprietà dei controlli Windows Form](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
