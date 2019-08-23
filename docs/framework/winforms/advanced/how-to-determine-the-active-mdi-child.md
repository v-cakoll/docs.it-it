---
title: 'Procedura: Determinare il figlio MDI attivo'
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
ms.openlocfilehash: 91100b37e4cae9041479b209e40034efe376df5b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946224"
---
# <a name="how-to-determine-the-active-mdi-child"></a>Procedura: Determinare il figlio MDI attivo
In alcuni casi, sarà necessario fornire un comando che opera sul controllo che ha lo stato attivo sul form figlio attualmente attivo. Si supponga, ad esempio, di voler copiare negli Appunti il testo selezionato dalla casella di testo del form figlio. Si creerebbe una procedura che consente di copiare il testo selezionato negli Appunti <xref:System.Windows.Forms.Control.Click> utilizzando l'evento della voce di menu copia nel menu modifica standard.  
  
 Poiché un'applicazione MDI può avere più istanze dello stesso form figlio, è necessario che la procedura conosca il formato da utilizzare. Per specificare il formato corretto, utilizzare la <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> proprietà, che restituisce il form figlio con lo stato attivo o che è stato attivato più di recente.  
  
 Quando si dispone di più controlli in un form, è necessario specificare anche il controllo attivo. Analogamente <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> alla proprietà, <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> la proprietà restituisce il controllo con lo stato attivo sul form figlio attivo. Nella procedura riportata di seguito viene illustrata una procedura di copia che può essere chiamata da un menu form figlio, da un menu nel form MDI o da un pulsante della barra degli strumenti.  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>Per determinare il figlio MDI attivo (per copiare il testo negli Appunti)  
  
1. All'interno di un metodo, copiare il testo del controllo attivo del form figlio attivo negli Appunti.  
  
    > [!NOTE]
    > In questo esempio si presuppone che esista un form padre`Form1`MDI () con una o più finestre figlio MDI contenenti <xref:System.Windows.Forms.RichTextBox> un controllo. Per ulteriori informazioni, vedere [creazione di form padre MDI](how-to-create-mdi-parent-forms.md).  
  
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
- [Procedura: Creare form figlio MDI](how-to-create-mdi-child-forms.md)
- [Procedura: Invia dati al figlio MDI attivo](how-to-send-data-to-the-active-mdi-child.md)
- [Procedura: Disponi form figlio MDI](how-to-arrange-mdi-child-forms.md)
