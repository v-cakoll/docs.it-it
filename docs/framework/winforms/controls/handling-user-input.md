---
title: Gestione dell'input dell'utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user input using code
- custom controls [Windows Forms], keyboard events using code
- custom controls [Windows Forms], mouse events using code
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
ms.openlocfilehash: 3ebe82fc18deba52fafe76da7ff85fb247446e46
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074952"
---
# <a name="handling-user-input"></a>Gestione dell'input dell'utente
In questo argomento descrive gli eventi di tastiera e mouse principali forniti da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Quando si gestisce un evento, gli autori dei controlli devono eseguire l'override del metodo protetto `On`*EventName* anziché associare un delegato all'evento. Per una panoramica degli eventi, vedere [Generazione di eventi da un componente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).  
  
> [!NOTE]
>  Se non sono presenti dati associati a un evento, un'istanza della classe di base <xref:System.EventArgs> viene passato come argomento per il `On` *EventName* (metodo).  
  
## <a name="keyboard-events"></a>Eventi della tastiera  
 Gli eventi della tastiera comuni che il controllo può gestire sono <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, e <xref:System.Windows.Forms.Control.KeyUp>.  
  
|Nome evento|Metodo di cui eseguire l'override|Descrizione dell'evento|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|Generato solo quando un tasto viene premuto inizialmente.|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|Generato ogni volta che un tasto viene premuto. Se un tasto viene tenuto premuto, un <xref:System.Windows.Forms.Control.KeyPress> evento viene generato alla frequenza di ripetizione definita dal sistema operativo.|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|Viene generato quando un tasto viene rilasciato.|  
  
> [!NOTE]
>  La gestione dell'input da tastiera è notevolmente più complessa dell'override degli eventi nella tabella precedente ed esula dall'ambito di questo argomento. Per altre informazioni, vedere [Input dell'utente in Windows Forms](../user-input-in-windows-forms.md).  
  
## <a name="mouse-events"></a>Eventi del mouse  
 Gli eventi del mouse che il controllo può gestire sono <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, e <xref:System.Windows.Forms.Control.MouseUp>.  
  
|Nome evento|Metodo di cui eseguire l'override|Descrizione dell'evento|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|Viene generato quando il pulsante del mouse viene premuto mentre il puntatore si trova sopra il controllo.|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|Viene generato quando il puntatore del mouse entra nell'area del controllo.|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|Viene generato quando il puntatore è posizionato sul controllo.|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|Viene generato quando il puntatore esce dall'area del controllo.|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|Viene generato quando il puntatore si sposta nell'area del controllo.|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|Viene generato quando il pulsante del mouse viene rilasciato mentre il puntatore si trova sul controllo o il puntatore esce dall'area del controllo.|  
  
 Il frammento di codice seguente viene illustrato un esempio di override di <xref:System.Windows.Forms.Control.MouseDown> evento.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 Il frammento di codice seguente viene illustrato un esempio di override di <xref:System.Windows.Forms.Control.MouseMove> evento.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 Il frammento di codice seguente viene illustrato un esempio di override di <xref:System.Windows.Forms.Control.MouseUp> evento.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 Il codice sorgente completo per il `FlashTrackBar` di esempio, vedere [come: Creare un controllo di Windows Form che mostra lo stato di avanzamento](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## <a name="see-also"></a>Vedere anche

- [Eventi dei controlli di Windows Form](events-in-windows-forms-controls.md)
- [Definizione di un evento](defining-an-event-in-windows-forms-controls.md)
- [Eventi](../../../standard/events/index.md)
- [Input dell'utente in Windows Forms](../user-input-in-windows-forms.md)
