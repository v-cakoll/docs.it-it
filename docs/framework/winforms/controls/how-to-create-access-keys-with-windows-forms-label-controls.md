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
ms.openlocfilehash: dd7f238f8c20ba990158f23344e36376d3b1cb7a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950530"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>Procedura: Creare tasti di scelta con i controlli Label di Windows Forms
È <xref:System.Windows.Forms.Label> possibile utilizzare i controlli Windows Forms per definire le chiavi di accesso per altri controlli. Quando si definisce una chiave di accesso in un controllo etichetta, l'utente può premere il tasto ALT più il carattere designato per spostare lo stato attivo sul controllo che lo segue nell'ordine di tabulazione. Poiché le etichette non possono ricevere lo stato attivo, lo stato attivo passa automaticamente al controllo successivo nell'ordine di tabulazione. Usare questa tecnica per assegnare chiavi di accesso a caselle di testo, caselle combinate, caselle di riepilogo e griglie di dati.  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>Per assegnare una chiave di accesso a un controllo con un'etichetta  
  
1. Creare prima l'etichetta, quindi creare l'altro controllo.  
  
     -oppure-  
  
     Creare i controlli in qualsiasi ordine e impostare la <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà dell'etichetta su uno minore dell'altro controllo.  
  
2. Impostare la <xref:System.Windows.Forms.Label.UseMnemonic%2A> proprietà dell'etichetta su `true`.  
  
3. Usare una e commerciale (&) nella <xref:System.Windows.Forms.Label.Text%2A> proprietà dell'etichetta per assegnare la chiave di accesso per l'etichetta. Per ulteriori informazioni, vedere [creazione di chiavi di accesso per controlli Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md).  
  
    > [!NOTE]
    > È possibile che si desideri visualizzare le e commerciali in un controllo etichetta, anziché usarle per creare chiavi di accesso. Questo problema può verificarsi se si associa un controllo Label a un campo in un recordset in cui i dati includono le e commerciali. Per visualizzare le e commerciali in un controllo Label, impostare <xref:System.Windows.Forms.Label.UseMnemonic%2A> la proprietà `false`su. Se si desidera visualizzare le e commerciali e avere anche una chiave di accesso, impostare <xref:System.Windows.Forms.Label.UseMnemonic%2A> la proprietà `true` su e indicare la chiave di accesso con una e commerciale (&) e la e commerciale da visualizzare con due e commerciali.  
  
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

- [Procedura: Ridimensionare un controllo etichetta Windows Forms per adattarne il contenuto](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [Panoramica sul controllo Label](label-control-overview-windows-forms.md)
- [Controllo Label](label-control-windows-forms.md)
