---
title: Cenni preliminari sul controllo Label
ms.date: 03/30/2017
f1_keywords:
- Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.assetid: dcad7f44-11b7-4c55-b0c0-d984ade43d7d
ms.openlocfilehash: 1ca14553c7cb51d2b7a329950aeaec4c0439762a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745281"
---
# <a name="label-control-overview-windows-forms"></a>Cenni preliminari sul controllo Label (Windows Form)
Windows Forms controlli <xref:System.Windows.Forms.Label> vengono utilizzati per visualizzare testo o immagini che non possono essere modificate dall'utente. Vengono usati per identificare gli oggetti in un form, per fornire una descrizione dell'operazione eseguita da un determinato controllo, ad esempio, o per visualizzare le informazioni in risposta a un evento o a un processo in fase di esecuzione nell'applicazione. Ad esempio, è possibile usare le etichette per aggiungere didascalie descrittive a caselle di testo, caselle di riepilogo, caselle combinate e così via. È anche possibile scrivere codice che modifica il testo visualizzato da un'etichetta in risposta agli eventi in fase di esecuzione. Se, ad esempio, l'applicazione richiede alcuni minuti per l'elaborazione di una modifica, è possibile visualizzare un messaggio di stato di elaborazione in un'etichetta.  
  
## <a name="working-with-the-label-control"></a>Utilizzo del controllo Label  
 Poiché il controllo <xref:System.Windows.Forms.Label> non può ricevere lo stato attivo, può anche essere usato per creare chiavi di accesso per altri controlli. Una chiave di accesso consente a un utente di selezionare l'altro controllo premendo ALT con il tasto di scelta. Per altre informazioni, vedere [creazione di chiavi di accesso per i controlli Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md) e [procedura: creare chiavi di accesso con Windows Forms controlli Label](how-to-create-access-keys-with-windows-forms-label-controls.md).  
  
 La didascalia visualizzata nell'etichetta è contenuta nella proprietà <xref:System.Windows.Forms.Label.Text%2A>. La proprietà <xref:System.Windows.Forms.Label.TextAlign%2A> consente di impostare l'allineamento del testo all'interno dell'etichetta. Per altre informazioni, vedere [procedura: impostare il testo visualizzato da un controllo Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Label>
- [Procedura: Ridimensionare un controllo Label di Windows Form in base al contenuto](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [Procedura: Creare tasti di scelta con i controlli Label di Windows Form](how-to-create-access-keys-with-windows-forms-label-controls.md)
