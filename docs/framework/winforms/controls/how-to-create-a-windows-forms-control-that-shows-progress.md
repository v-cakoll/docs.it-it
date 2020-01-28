---
title: Crea controllo che mostra lo stato di avanzamento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], progress tracking
- controls [Windows Forms], creating
- progress [Windows Forms], reporting [Windows Forms]
- FlashTrackBar custom control
ms.assetid: 24c5a2e3-058c-4b8d-a217-c06e6a130c2f
ms.openlocfilehash: 9d2cf353ba2309380221bb51733baaca1b81a5d5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731183"
---
# <a name="how-to-create-a-windows-forms-control-that-shows-progress"></a>Procedura: creare un controllo di Windows Form che visualizzi lo stato di avanzamento
L'esempio di codice seguente visualizza un controllo personalizzato denominato `FlashTrackBar` che può essere usato per visualizzare all'utente il livello o lo stato di avanzamento di un'applicazione. Usa una sfumatura per rappresentare visivamente lo stato di avanzamento.  
  
 Il controllo `FlashTrackBar` illustra i concetti seguenti:  
  
- Definizione di proprietà personalizzate.  
  
- Definizione di eventi personalizzati. (`FlashTrackBar` definisce l'evento `ValueChanged`.)  
  
- Override del metodo <xref:System.Windows.Forms.Control.OnPaint%2A> per fornire la logica per creare il controllo.  
  
- Calcolo dell'area disponibile per il disegno del controllo tramite la relativa proprietà <xref:System.Windows.Forms.Control.ClientRectangle%2A>. `FlashTrackBar` esegue questa operazione nel relativo metodo `OptimizedInvalidate`.  
  
- Implementazione della serializzazione o del salvataggio permanente per una proprietà quando viene modificata nella Progettazione Windows Form. `FlashTrackBar` definisce i metodi `ShouldSerializeStartColor` e `ShouldSerializeEndColor` per la serializzazione delle relative proprietà `StartColor` e `EndColor`.  
  
 La tabella seguente elenca le proprietà personalizzate definite da `FlashTrackBar`.  
  
|Gli|Descrizione|  
|--------------|-----------------|  
|`AllowUserEdit`|Indica se l'utente può modificare il valore del controllo FlashTrackBar tramite selezione e trascinamento.|  
|`EndColor`|Specifica il colore finale della barra di avanzamento.|  
|`DarkenBy`|Specifica di quanto scurire lo sfondo rispetto alla sfumatura di primo piano.|  
|`Max`|Specifica il valore massimo della barra di avanzamento.|  
|`Min`|Specifica il valore minimo della barra di avanzamento.|  
|`StartColor`|Specifica il colore iniziale della sfumatura.|  
|`ShowPercentage`|Indica se visualizzare una percentuale sulla sfumatura.|  
|`ShowValue`|Indica se visualizzare il valore corrente sulla sfumatura.|  
|`ShowGradient`|Indica se l'indicatore di avanzamento deve visualizzare una sfumatura di colore che indica il valore corrente.|  
|-   `Value`|Specifica il valore corrente della barra di avanzamento.|  
  
 La tabella seguente elenca membri aggiuntivi definiti dalla proprietà `FlashTrackBar:`: l'evento proprietà modificata e il metodo che genera tale evento.  
  
|Member|Descrizione|  
|------------|-----------------|  
|`ValueChanged`|L'evento generato quando viene modificata la proprietà `Value` della barra di avanzamento.|  
|`OnValueChanged`|Il metodo che genera l'evento `ValueChanged`.|  
  
> [!NOTE]
> `FlashTrackBar` usa la classe <xref:System.EventArgs> per i dati dell'evento e <xref:System.EventHandler> per il delegato dell'evento.  
  
 Per gestire gli eventi *EventName* corrispondenti, `FlashTrackBar` esegue l'override dei metodi seguenti ereditati da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:  
  
- <xref:System.Windows.Forms.Control.OnPaint%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseDown%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseMove%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseUp%2A>  
  
- <xref:System.Windows.Forms.Control.OnResize%2A>  
  
 Per gestire gli eventi di modifica di proprietà corrispondenti, `FlashTrackBar` esegue l'override dei metodi seguenti ereditati da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:  
  
- <xref:System.Windows.Forms.Control.OnBackColorChanged%2A>  
  
- <xref:System.Windows.Forms.Control.OnBackgroundImageChanged%2A>  
  
- <xref:System.Windows.Forms.Control.OnTextChanged%2A>  
  
## <a name="example"></a>Esempio  
 Il controllo `FlashTrackBar` definisce due editor di tipi dell'interfaccia utente, `FlashTrackBarValueEditor` e `FlashTrackBarDarkenByEditor`, visualizzati negli elenchi di codice seguenti. La classe `HostApp` usa il controllo `FlashTrackBar` in un Windows Form.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#1)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#1)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarDarkenByEditor.cs#10)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarDarkenByEditor.vb#10)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarValueEditor.cs#20)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarValueEditor.vb#20)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/HostApp.cs#30)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/HostApp.vb#30)]  
  
## <a name="see-also"></a>Vedere anche

- [Estensione del supporto in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))
- [Nozioni fondamentali sullo sviluppo di controlli Windows Form](windows-forms-control-development-basics.md)
