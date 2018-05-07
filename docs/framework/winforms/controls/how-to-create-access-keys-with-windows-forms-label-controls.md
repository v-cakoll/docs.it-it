---
title: 'Procedura: creare tasti di scelta con i controlli Label di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
ms.openlocfilehash: fc9592981f3d926b2b5b85b6869da13dc644e7a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>Procedura: creare tasti di scelta con i controlli Label di Windows Form
Windows Form <xref:System.Windows.Forms.Label> controlli possono essere utilizzati per definire le chiavi di accesso per altri controlli. Quando si definisce una chiave di accesso in un controllo etichetta, l'utente può premere il tasto ALT più il carattere di spostare lo stato attivo al controllo successivo nell'ordine di tabulazione. Poiché le etichette non possono ricevere lo stato attivo, lo stato attivo si sposta automaticamente al controllo successivo nell'ordine di tabulazione. Utilizzare questa tecnica per assegnare le chiavi di accesso per le caselle di testo, caselle combinate, caselle di riepilogo e griglie dei dati.  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>Per assegnare una chiave di accesso a un controllo con un'etichetta  
  
1.  Creare prima l'etichetta e quindi trascinare il controllo di altri.  
  
     oppure  
  
     Creare i controlli in qualsiasi ordine e impostare il <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà dell'etichetta e l'altro controllo meno uno.  
  
2.  Impostare l'etichetta <xref:System.Windows.Forms.Label.UseMnemonic%2A> proprietà `true`.  
  
3.  Usare una e commerciale (&) dell'etichetta <xref:System.Windows.Forms.Label.Text%2A> proprietà a cui assegnare la chiave di accesso per l'etichetta. Per ulteriori informazioni, vedere [creazione di chiavi per i controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).  
  
    > [!NOTE]
    >  Si desidera, visualizzare le e commerciali in un controllo etichetta, anziché utilizzarle per creare le chiavi di accesso. Ciò può verificarsi se si associa un controllo etichetta a un campo in un recordset in cui i dati includono le e commerciali. Per visualizzare le e commerciali in un controllo etichetta, impostare il <xref:System.Windows.Forms.Label.UseMnemonic%2A> proprietà `false`. Se si desidera visualizzare le e commerciali e dispongano di una chiave di accesso, impostare il <xref:System.Windows.Forms.Label.UseMnemonic%2A> proprietà `true` e indicare la chiave di accesso con una e commerciale (&) due e.  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Ridimensionare un controllo Label di Windows Form in base al contenuto](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)  
 [Panoramica sul controllo Label](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [Controllo Label](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
