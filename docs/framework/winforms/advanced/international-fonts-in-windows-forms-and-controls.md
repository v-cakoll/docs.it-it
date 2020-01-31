---
title: Tipi di carattere internazionali nei form e nei controlli
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
dev_langs:
- csharp
- vb
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: 59dde6bb384d644321a8ff5674d735f8e6d36fd0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743513"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a>Tipi di carattere internazionali in Windows Forms e controlli

Nelle applicazioni internazionali, il metodo consigliato per la selezione di tipi di carattere consiste nell'usare il fallback del tipo di carattere laddove possibile. Il fallback del tipo di carattere significa che il sistema determina a quale script appartiene il carattere.

## <a name="using-font-fallback"></a>Uso del fallback dei tipi di carattere

Per sfruttare i vantaggi di questa funzionalità, non impostare la proprietà <xref:System.Drawing.Font> per il form o qualsiasi altro elemento. L'applicazione userà automaticamente il tipo di carattere di sistema predefinito, che differisce da una lingua localizzata del sistema operativo a un'altra. Quando l'applicazione viene eseguita, il sistema fornisce automaticamente il tipo di carattere corretto per le impostazioni cultura selezionate nel sistema operativo.

Si verifica un'eccezione alla regola di non impostare il tipo di carattere, ovvero per modificare lo stile del tipo di carattere. Questo potrebbe essere importante per un'applicazione in cui l'utente fa clic su un pulsante per creare il testo in una casella di testo in grassetto. A tale scopo, è necessario scrivere una funzione per modificare lo stile del tipo di carattere della casella di testo in grassetto, in base a qualsiasi tipo di carattere del modulo. È importante chiamare questa funzione in due posizioni: nel gestore dell'evento <xref:System.Windows.Forms.Control.Click> del pulsante e nel gestore dell'evento <xref:System.Windows.Forms.Control.FontChanged>. Se la funzione viene chiamata solo nel gestore eventi <xref:System.Windows.Forms.Control.Click> e alcune altre parti di codice modificano la famiglia di caratteri dell'intero form, la casella di testo non cambia con il resto del modulo.

```vb
Private Sub MakeBold()
   ' Change the TextBox to a bold version of the form font
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)
End Sub

Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
   ' Clicking this button makes the TextBox bold
   MakeBold()
End Sub

Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged
   ' If the TextBox is already bold and the form's font changes,
   ' change the TextBox to a bold version of the new form font
   If (TextBox1.Font.Style = FontStyle.Bold) Then
      MakeBold()
   End If
End Sub
```

```csharp
private void button1_Click(object sender, System.EventArgs e)
{
   // Clicking this button makes the TextBox bold
   MakeBold();
}

private void MakeBold()
{
   // Change the TextBox to a bold version of the form's font
   textBox1.Font = new Font(this.Font, FontStyle.Bold);
}

private void Form1_FontChanged(object sender, System.EventArgs e)
{
   // If the TextBox is already bold and the form's font changes,
   // change the TextBox to a bold version of the new form font
   if (textBox1.Font.Style == FontStyle.Bold)
   {
      MakeBold();
   }
}
```

Tuttavia, quando si localizza l'applicazione, il tipo di carattere in grassetto potrebbe risultare scarso per alcune lingue. Se si tratta di un problema, si desidera che i localizzatori abbiano la possibilità di cambiare il tipo di carattere da grassetto a testo normale. Poiché i localizzatori non sono in genere sviluppatori e non hanno accesso al codice sorgente, solo ai file di risorse, questa opzione deve essere impostata nei file di risorse. A tale scopo, impostare la proprietà <xref:System.Drawing.Font.Bold%2A> su `true`. In questo modo, l'impostazione del tipo di carattere viene scritta nei file di risorse, in cui i localizzatori possono modificarlo. Si scrive quindi il codice dopo il metodo `InitializeComponent` per reimpostare il tipo di carattere in base a qualsiasi tipo di carattere del form, ma usando lo stile del carattere specificato nel file di risorse.

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a>Vedere anche

- [Uso di tipi di carattere e testo](using-fonts-and-text.md)
