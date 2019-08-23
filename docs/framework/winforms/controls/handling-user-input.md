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
ms.openlocfilehash: f92b742c3f6feec72e5b3150204d7d984636281d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934084"
---
# <a name="handling-user-input"></a>Gestione dell'input dell'utente
In questo argomento vengono descritti gli eventi principali della tastiera e <xref:System.Windows.Forms.Control?displayProperty=nameWithType>del mouse forniti da. Quando si gestisce un evento, gli autori dei controlli devono eseguire l'override del metodo protetto `On`*EventName* anziché associare un delegato all'evento. Per una panoramica degli eventi, vedere [Generazione di eventi da un componente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).  
  
> [!NOTE]
> Se non sono presenti dati associati a un evento, un'istanza della classe <xref:System.EventArgs> di base viene passata come argomento `On`al metodo *EventName* .  
  
## <a name="keyboard-events"></a>Eventi della tastiera  
 Gli eventi di tastiera comuni che il controllo è in <xref:System.Windows.Forms.Control.KeyDown>grado <xref:System.Windows.Forms.Control.KeyPress>di gestire <xref:System.Windows.Forms.Control.KeyUp>sono, e.  
  
|Nome evento|Metodo di cui eseguire l'override|Descrizione dell'evento|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|Generato solo quando un tasto viene premuto inizialmente.|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|Generato ogni volta che un tasto viene premuto. Se un tasto viene mantenuto attivo, viene <xref:System.Windows.Forms.Control.KeyPress> generato un evento alla frequenza di ripetizione definita dal sistema operativo.|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|Viene generato quando un tasto viene rilasciato.|  
  
> [!NOTE]
> La gestione dell'input da tastiera è notevolmente più complessa dell'override degli eventi nella tabella precedente ed esula dall'ambito di questo argomento. Per altre informazioni, vedere [Input dell'utente in Windows Forms](../user-input-in-windows-forms.md).  
  
## <a name="mouse-events"></a>Eventi del mouse  
 Gli eventi del mouse che il controllo è in <xref:System.Windows.Forms.Control.MouseDown>grado di gestire sono <xref:System.Windows.Forms.Control.MouseMove> <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseEnter> <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseUp>,, e.  
  
|Nome evento|Metodo di cui eseguire l'override|Descrizione dell'evento|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|Viene generato quando il pulsante del mouse viene premuto mentre il puntatore si trova sopra il controllo.|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|Viene generato quando il puntatore del mouse entra nell'area del controllo.|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|Viene generato quando il puntatore è posizionato sul controllo.|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|Viene generato quando il puntatore esce dall'area del controllo.|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|Viene generato quando il puntatore si sposta nell'area del controllo.|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|Viene generato quando il pulsante del mouse viene rilasciato mentre il puntatore si trova sul controllo o il puntatore esce dall'area del controllo.|  
  
 Il frammento di codice seguente illustra un esempio di override <xref:System.Windows.Forms.Control.MouseDown> dell'evento.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 Il frammento di codice seguente illustra un esempio di override <xref:System.Windows.Forms.Control.MouseMove> dell'evento.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 Il frammento di codice seguente illustra un esempio di override <xref:System.Windows.Forms.Control.MouseUp> dell'evento.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 Per il codice sorgente completo per l' `FlashTrackBar` esempio, vedere [procedura: Creare un controllo Windows Forms che mostra lo](how-to-create-a-windows-forms-control-that-shows-progress.md)stato di avanzamento.  
  
## <a name="see-also"></a>Vedere anche

- [Eventi dei controlli di Windows Form](events-in-windows-forms-controls.md)
- [Definizione di un evento](defining-an-event-in-windows-forms-controls.md)
- [Eventi](../../../standard/events/index.md)
- [Input dell'utente in Windows Forms](../user-input-in-windows-forms.md)
