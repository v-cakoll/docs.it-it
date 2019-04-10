---
title: 'Procedura: Creare tasti di scelta con i controlli Label di Windows Forms'
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
ms.openlocfilehash: ffe4bf6fb29e82b04938e2ba9a2d9d21e5eabcde
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59314308"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>Procedura: Creare tasti di scelta con i controlli Label di Windows Forms
Windows Form <xref:System.Windows.Forms.Label> controlli possono essere utilizzati per definire le chiavi di accesso per altri controlli. Quando si definisce una chiave di accesso in un controllo etichetta, l'utente può premere il tasto ALT più il carattere che si è scelto di spostare lo stato attivo al controllo che lo segue nell'ordine di tabulazione. Poiché le etichette non possono ricevere lo stato attivo, lo stato attivo si sposta automaticamente al controllo successivo nell'ordine di tabulazione. Usare questa tecnica per assegnare le chiavi di accesso per le caselle di testo, caselle combinate, caselle di riepilogo e griglie di dati.  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>Per assegnare una chiave di accesso a un controllo con un'etichetta  
  
1. Creare prima l'etichetta e quindi disegnare l'altro controllo.  
  
     -oppure-  
  
     Disegnare i controlli in qualsiasi ordine e impostare il <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà dell'etichetta di altro controllo meno uno.  
  
2. Impostare l'etichetta <xref:System.Windows.Forms.Label.UseMnemonic%2A> proprietà `true`.  
  
3. Usare una e commerciale (&) dell'etichetta <xref:System.Windows.Forms.Label.Text%2A> proprietà da assegnare la chiave di accesso per l'etichetta. Per altre informazioni, vedere [creazione di chiavi per i controlli Windows Form](how-to-create-access-keys-for-windows-forms-controls.md).  
  
    > [!NOTE]
    >  È possibile visualizzare le e commerciali in un controllo etichetta, anziché a usarle per creare le chiavi di accesso. Ciò può verificarsi se si associa un controllo etichetta a un campo in un set di record in cui i dati includono le e commerciali. Per visualizzare le e commerciali in un controllo etichetta, impostare il <xref:System.Windows.Forms.Label.UseMnemonic%2A> proprietà `false`. Se si desidera visualizzare le e commerciali e anche di una chiave di accesso, impostare il <xref:System.Windows.Forms.Label.UseMnemonic%2A> proprietà `true` e indicare la chiave di accesso con una e commerciale (&) e la e commerciale da visualizzare con due caratteri e commerciale.  
  
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

- [Procedura: Ridimensionare un controllo Label di Windows Forms in base al contenuto](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [Panoramica del controllo Label](label-control-overview-windows-forms.md)
- [Controllo Label](label-control-windows-forms.md)
