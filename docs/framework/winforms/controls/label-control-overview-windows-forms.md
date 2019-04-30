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
ms.openlocfilehash: cc38b0f3ded9e3c2a5a4146eb6bb474921d1e19f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012860"
---
# <a name="label-control-overview-windows-forms"></a>Cenni preliminari sul controllo Label (Windows Form)
Windows Form <xref:System.Windows.Forms.Label> controlli vengono usati per visualizzare un testo o immagini che non possono essere modificate dall'utente. Vengono usati per identificare gli oggetti in un form, per fornire una descrizione dell'azione di un determinato controllo producono se si fa clic, ad esempio, o per visualizzare le informazioni in risposta a un evento di runtime o un processo dell'applicazione. Ad esempio, è possibile usare etichette per aggiungere sottotitoli in lingua originale descrittivi per le caselle di testo, caselle di riepilogo, caselle combinate e così via. È anche possibile scrivere codice che modifica il testo visualizzato da un'etichetta in risposta agli eventi in fase di esecuzione. Ad esempio, se l'applicazione richiede alcuni minuti per elaborare una modifica, è possibile visualizzare un messaggio di stato di elaborazione in un'etichetta.  
  
## <a name="working-with-the-label-control"></a>Utilizzo del controllo etichetta  
 Poiché il <xref:System.Windows.Forms.Label> controllo non può ricevere lo stato attivo, può essere utilizzato anche per creare le chiavi di accesso per altri controlli. Una chiave di accesso consente all'utente di selezionare l'altro controllo premendo il tasto ALT con la chiave di accesso. Per altre informazioni, vedere [creazione di chiavi per i controlli Windows Form](how-to-create-access-keys-for-windows-forms-controls.md) e [come: Creare le chiavi di accesso con i controlli Label di Windows Form](how-to-create-access-keys-with-windows-forms-label-controls.md).  
  
 La didascalia visualizzata nell'etichetta è contenuta nel <xref:System.Windows.Forms.Label.Text%2A> proprietà. Il <xref:System.Windows.Forms.Label.TextAlign%2A> proprietà consente di impostare l'allineamento del testo all'interno dell'etichetta. Per altre informazioni, vedere [Procedura: Impostare il testo visualizzato dal controllo di un Windows Form](how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Label>
- [Procedura: Ridimensionare un controllo Label di Windows Form in base al contenuto](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [Procedura: Creare le chiavi di accesso con i controlli Label di Windows Form](how-to-create-access-keys-with-windows-forms-label-controls.md)
