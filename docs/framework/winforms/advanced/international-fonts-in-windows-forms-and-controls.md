---
title: Caratteri internazionali in Windows Form e controlli
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
ms.openlocfilehash: 1f9afd575e2de04e0b11556ad34436839e13d968
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693240"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a>Caratteri internazionali in Windows Form e controlli

Nelle applicazioni internazionali, il metodo consigliato per la selezione del carattere è utilizzare il fallback laddove possibile. Si intende fallback del tipo di carattere che il sistema determina ciò che il carattere di script appartiene.

## <a name="using-font-fallback"></a>Usa il fallback del tipo di carattere

Per sfruttare i vantaggi di questa funzionalità, non vengono impostate le <xref:System.Drawing.Font> proprietà per il form o qualsiasi altro elemento. L'applicazione userà automaticamente il carattere di sistema predefinito, che è diverso da una lingua localizzata del sistema operativo a un altro. Quando viene eseguita l'applicazione, il sistema fornirà automaticamente il tipo di carattere per le impostazioni cultura selezionate del sistema operativo.

Si verifica un'eccezione alla regola di non impostare il tipo di carattere, ovvero per modificare lo stile del carattere. Questo potrebbe essere importante per un'applicazione in cui l'utente fa clic su un pulsante per visualizzare testo in una casella di testo in grassetto. A tale scopo, si scriverebbe una funzione per modificare lo stile del carattere della casella di testo in grassetto, basato sul tipo di carattere qualsiasi del form. È importante chiamare questa funzione in due posizioni: nel pulsante <xref:System.Windows.Forms.Control.Click> gestore dell'evento e il <xref:System.Windows.Forms.Control.FontChanged> gestore dell'evento. Se la funzione viene chiamata solo nel <xref:System.Windows.Forms.Control.Click> gestore dell'evento e altre parti di codice modifica la famiglia di caratteri dell'intero form, la casella di testo non cambia con il resto del form.

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

Tuttavia, quando si localizza l'applicazione, il tipo di carattere grassetto potrebbe essere visualizzato in modo inadeguato per alcune lingue. Se si tratta di un problema, si desidera che i localizzatori per avere la possibilità di passare il tipo di carattere da grassetto al testo normale. Poiché i localizzatori non sono in genere gli sviluppatori e non hanno accesso al codice sorgente, solo ai file di risorse, questa opzione deve essere impostata nei file di risorse. A tale scopo, è necessario impostare il <xref:System.Drawing.Font.Bold%2A> proprietà `true`. Ciò comporta l'impostazione del tipo di carattere in corso di scrittura per i file di risorse, dove potrà essere modificata. Sarà quindi necessario scrivere codice dopo la `InitializeComponent` base è qualsiasi carattere del form per reimpostare il tipo di carattere, ma usando lo stile del carattere specificati nel file di risorse.

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a>Vedere anche

- [Globalizzazione di applicazioni Windows Form](globalizing-windows-forms.md)
- [Uso di tipi di carattere e testo](using-fonts-and-text.md)
