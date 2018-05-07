---
title: Caratteri internazionali nei controlli e in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: 38a6928dfb548c6b514b598dbebe5bbc62d2e3f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="international-fonts-in-windows-forms-and-controls"></a>Caratteri internazionali nei controlli e in Windows Form
Applicazioni internazionali il metodo consigliato per la selezione del carattere consiste nell'utilizzare il fallback ove possibile. Per fallback si intende che il sistema determina quali il carattere di script a cui appartiene.  
  
## <a name="using-font-fallback"></a>Tramite il Fallback  
 Per sfruttare i vantaggi di questa funzionalità, non impostare la <xref:System.Drawing.Font> proprietà per il form o qualsiasi altro elemento. L'applicazione utilizzerà automaticamente il carattere di sistema predefinito, che differisce da una lingua localizzata del sistema operativo a un altro. Quando viene eseguita l'applicazione, il sistema viene fornito automaticamente il tipo di carattere corretto per la lingua selezionata nel sistema operativo.  
  
 Si verifica un'eccezione alla regola di non impostare il tipo di carattere, ovvero per modificare lo stile del carattere. Questo potrebbe essere importante per un'applicazione in cui l'utente fa clic su un pulsante per visualizzare testo in una casella di testo in grassetto. A tale scopo, è necessario scrivere una funzione per modificare lo stile del carattere della casella di testo da visualizzare in grassetto, in base a qualsiasi carattere del form è. È importante chiamare questa funzione in due posizioni: il pulsante <xref:System.Windows.Forms.Control.Click> gestore dell'evento e il <xref:System.Windows.Forms.Control.FontChanged> gestore dell'evento. Se la funzione viene chiamata solo il <xref:System.Windows.Forms.Control.Click> gestore eventi e altre parti di codice modifica la famiglia di caratteri dell'intero form, la casella di testo non cambia con il resto del form.  
  
```  
' Visual Basic  
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
  
// C#  
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
  
 Tuttavia, quando si localizza l'applicazione, il tipo di carattere grassetto potrebbe essere visualizzato in modo inadeguato per determinate lingue. Se si tratta di un problema, si desidera che i localizzatori di hanno la possibilità di passare il tipo di carattere da grassetto in testo normale. Poiché i localizzatori non sono in genere gli sviluppatori e non hanno accesso al codice sorgente, solo per i file di risorse, questa opzione deve essere impostata nei file di risorse. A tale scopo, impostare il <xref:System.Drawing.Font.Bold%2A> proprietà `true`. Ciò comporta l'impostazione del tipo di carattere viene scritto i file di risorse, in cui potrà essere modificata. È quindi scrivere codice dopo il `InitializeComponent` per reimpostare il tipo di carattere dal qualsiasi carattere del form, ma utilizzando lo stile del carattere specificato nel file di risorse.  
  
```  
' Visual Basic  
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)  
  
// C#  
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Globalizzazione di Windows Form](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)  
 [Uso di tipi di carattere e testo](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
