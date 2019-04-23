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
ms.openlocfilehash: cabfd9e799288a332a0b2f96140f5f1cc328508b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105769"
---
# <a name="property-changed-events"></a>Eventi per proprietà modificate
Se si desidera che il controllo per inviare notifiche quando una proprietà denominata *PropertyName* modifiche, definire un evento denominato *PropertyName* `Changed` e un metodo denominato `On` *PropertyName* `Changed` che genera l'evento. La convenzione di denominazione in Windows Form consiste nell'aggiungere la parola *Changed* al nome della proprietà. Il tipo di delegato di evento associato per gli eventi di modifica della proprietà è <xref:System.EventHandler>, e il tipo di dati di evento è <xref:System.EventArgs>. La classe di base <xref:System.Windows.Forms.Control> definisce molti eventi di modifica delle proprietà, ad esempio <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>e così via. Per informazioni generali sugli eventi, vedere [eventi](../../../standard/events/index.md) e [eventi nei controlli di Windows Form](events-in-windows-forms-controls.md).  
  
 Eventi di modifica delle proprietà sono utili perché consentono agli utenti di un controllo di associazione dei gestori di eventi che rispondono alla modifica. Se il controllo deve rispondere a un evento di modifica della proprietà da esso generato, eseguire l'override `On` *PropertyName* `Changed` metodo anziché associare un delegato all'evento. Un controllo in genere risponde a un evento di modifica della proprietà aggiornando le altre proprietà o dal ridisegno alcuni o tutti relativa superficie di disegno.  
  
 L'esempio seguente illustra come la `FlashTrackBar` risposta del controllo personalizzato per alcuni degli eventi di modifica della proprietà che eredita da <xref:System.Windows.Forms.Control>. Per l'esempio completo, vedere [come: Creare un controllo di Windows Form che mostra lo stato di avanzamento](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Eventi](../../../standard/events/index.md)
- [Eventi dei controlli di Windows Form](events-in-windows-forms-controls.md)
- [Proprietà dei controlli Windows Form](properties-in-windows-forms-controls.md)
