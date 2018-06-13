---
title: Cenni preliminari sul controllo Label (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.assetid: dcad7f44-11b7-4c55-b0c0-d984ade43d7d
ms.openlocfilehash: e5ad4416703e20a8e00299d496d360e1e84005a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536302"
---
# <a name="label-control-overview-windows-forms"></a>Cenni preliminari sul controllo Label (Windows Form)
Windows Form <xref:System.Windows.Forms.Label> controlli vengono utilizzati per visualizzare un testo o immagini che non possono essere modificate dall'utente. Vengono utilizzati per identificare gli oggetti in un form, per fornire una descrizione dell'azione di un determinato controllo eseguirà se si fa clic, ad esempio, o per visualizzare le informazioni in risposta a un evento di runtime o un processo dell'applicazione. Ad esempio, è possibile utilizzare le etichette per aggiungere didascalie descrittive a caselle di testo, caselle di riepilogo, caselle combinate e così via. È anche possibile scrivere codice che modifica il testo visualizzato da un'etichetta in risposta agli eventi in fase di esecuzione. Ad esempio, se l'applicazione richiede alcuni minuti per elaborare una modifica, è possibile visualizzare un messaggio di stato di elaborazione in un'etichetta.  
  
## <a name="working-with-the-label-control"></a>Utilizzo del controllo etichetta  
 Poiché il <xref:System.Windows.Forms.Label> controllo non può ricevere lo stato attivo, può essere utilizzato anche per creare le chiavi di accesso per altri controlli. Una chiave di accesso consente di selezionare l'altro controllo premendo il tasto ALT con la chiave di accesso. Per ulteriori informazioni, vedere [creazione di chiavi per i controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) e [procedura: creare tasti di scelta con controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md).  
  
 La didascalia visualizzata nell'etichetta è contenuta nel <xref:System.Windows.Forms.Label.Text%2A> proprietà. Il <xref:System.Windows.Forms.Label.TextAlign%2A> proprietà consente di impostare l'allineamento del testo all'interno dell'etichetta. Per ulteriori informazioni, vedere [procedura: impostare il testo visualizzato da un controllo Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Label>  
 [Procedura: Ridimensionare un controllo Label di Windows Form in base al contenuto](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)  
 [Procedura: Creare tasti di scelta con i controlli Label di Windows Form](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)
