---
title: 'Procedura: determinare il figlio MDI attivo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- MDI [Windows Forms], child windows
- child forms
- MDI [Windows Forms], activating forms
- MDI [Windows Forms], locating focus
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
ms.openlocfilehash: 57491faa10c182630d41565ba236d65e393929b3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182540"
---
# <a name="how-to-determine-the-active-mdi-child"></a>Procedura: determinare il figlio MDI attivo
In alcuni casi, è necessario fornire un comando che opera sul controllo che ha lo stato attivo sul form figlio attualmente attivo. Si supponga, ad esempio, di voler copiare negli Appunti il testo selezionato dalla casella di testo del form figlio. È possibile creare una routine che copia il <xref:System.Windows.Forms.Control.Click> testo selezionato negli Appunti utilizzando l'evento della voce di menu Copia del menu Modifica standard.  
  
 Poiché un'applicazione MDI può avere molte istanze dello stesso form figlio, la procedura deve sapere quale form utilizzare. Per specificare il form <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> corretto, utilizzare la proprietà , che restituisce il form figlio con lo stato attivo o attivo più di recente.  
  
 Quando in un form sono presenti più controlli, è necessario specificare anche quale controllo è attivo. Come <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> la proprietà, la <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> proprietà restituisce il controllo con lo stato attivo sul form figlio attivo. Nella procedura riportata di seguito viene illustrata una procedura di copia che può essere chiamata da un menu del form figlio, da un menu del form MDI o da un pulsante della barra degli strumenti.  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>Per determinare l'elemento figlio MDI attivo (per copiarne il testo negli Appunti)  
  
1. All'interno di un metodo, copiare il testo del controllo attivo del form figlio attivo negli Appunti.  
  
    > [!NOTE]
    > In questo esempio si presuppone che`Form1`sia presente un form padre MDI <xref:System.Windows.Forms.RichTextBox> ( ) con una o più finestre figlio MDI contenenti un controllo . Per ulteriori informazioni, vedere [Creazione di form padre MDI](how-to-create-mdi-parent-forms.md).  
  
    ```vb  
    Public Sub mniCopy_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniCopy.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Dim theBox As RichTextBox = _  
            TryCast(activeChild.ActiveControl, RichTextBox)  
  
          If (Not theBox Is Nothing) Then  
             'Put selected text on Clipboard.  
             Clipboard.SetDataObject(theBox.SelectedText)  
          Else  
             MessageBox.Show("You need to select a RichTextBox.")  
          End If  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniCopy_Click (object sender, System.EventArgs e)  
    {  
       // Determine the active child form.  
       Form activeChild = this.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {
          try  
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Put the selected text on the Clipboard.  
                Clipboard.SetDataObject(theBox.SelectedText);  
  
             }  
          }  
          catch  
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)](multiple-document-interface-mdi-applications.md)
- [Procedura: Creare form padre MDI](how-to-create-mdi-parent-forms.md)
- [Procedura: creare form figlio MDI](how-to-create-mdi-child-forms.md)
- [Procedura: inviare dati al figlio MDI attivo](how-to-send-data-to-the-active-mdi-child.md)
- [Procedura: Disporre i form figlio MDI](how-to-arrange-mdi-child-forms.md)
