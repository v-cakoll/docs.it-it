---
title: Funzionalità predefinite nel controllo DataGridView Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: a475d8bce388860c88571fbf638d206bfe01223d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a>Funzionalità predefinite nel controllo DataGridView Windows Form
Windows Form <xref:System.Windows.Forms.DataGridView> controllo offre agli utenti con una quantità significativa di funzionalità predefinite.  
  
## <a name="default-functionality"></a>Funzionalità predefinita  
 Per impostazione predefinita, un <xref:System.Windows.Forms.DataGridView> controllo:  
  
-   Visualizza automaticamente le intestazioni di colonna e intestazioni di riga che restano visibili durante lo scorrimento verticale della tabella.  
  
-   Include un'intestazione di riga che contiene un indicatore di selezione per la riga corrente.  
  
-   Dispone di un rettangolo di selezione nella prima cella.  
  
-   Sono presenti colonne che possono essere ridimensionate automaticamente quando l'utente fa doppio clic i separatori di colonna.  
  
-   In Windows XP e nella famiglia Windows Server 2003 sono automaticamente supportati gli stili di visualizzazione quando il <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> metodo viene chiamato da dell'applicazione `Main` metodo.  
  
 Inoltre, il contenuto di un <xref:System.Windows.Forms.DataGridView> controllo può essere modificato per impostazione predefinita:  
  
-   Se l'utente fa doppio clic o preme F2 in una cella, il controllo viene automaticamente pone la cella in modalità di modifica e aggiorna il contenuto della cella, come i tipi di utente.  
  
-   Se l'utente scorre verso la fine della griglia, verrà visualizzato l'utente che sia presente una riga per l'aggiunta di nuovi record. Quando l'utente fa clic su questa riga, viene aggiunta una nuova riga per il <xref:System.Windows.Forms.DataGridView> controllo con i valori predefiniti. Quando l'utente preme ESC, questa nuova riga viene rimossa.  
  
-   Se l'utente fa clic su un'intestazione di riga, viene selezionata l'intera riga.  
  
 Quando si associa un <xref:System.Windows.Forms.DataGridView> controllo a un'origine dati impostando il relativo <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà, il controllo:  
  
-   Utilizza automaticamente i nomi delle colonne dell'origine dati come il testo dell'intestazione di colonna.  
  
-   Viene popolata con il contenuto dell'origine dati. <xref:System.Windows.Forms.DataGridView> le colonne vengono create automaticamente per ogni colonna nell'origine dati.  
  
-   Crea una riga per ogni riga visibile nella tabella.  
  
-   Ordina automaticamente le righe in base ai dati sottostanti quando l'utente fa clic su un'intestazione di colonna.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 [Controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
