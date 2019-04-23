---
title: Funzionalità predefinite nel controllo DataGridView Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: 26633b0abaa8c1c2916153b2236ecf9e4982fd68
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208865"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a>Funzionalità predefinite nel controllo DataGridView Windows Form
I moduli di Windows <xref:System.Windows.Forms.DataGridView> controllo offre agli utenti con una quantità significativa di funzionalità predefinite.  
  
## <a name="default-functionality"></a>Funzionalità predefinite  
 Per impostazione predefinita, un <xref:System.Windows.Forms.DataGridView> controllo:  
  
-   Visualizza automaticamente le intestazioni di colonna e le intestazioni di riga che restano visibili durante lo scorrimento verticale della tabella.  
  
-   Include un'intestazione di riga che contiene un indicatore di selezione per la riga corrente.  
  
-   Dispone di un rettangolo di selezione nella prima cella.  
  
-   Include colonne che possono essere ridimensionate automaticamente quando l'utente fa doppio clic sui separatori di colonna.  
  
-   Supporta automaticamente gli stili famiglia di prodotti Windows Server 2003 e Windows XP quando la <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> viene chiamato dall'oggetto dell'applicazione `Main` (metodo).  
  
 Inoltre, il contenuto di un <xref:System.Windows.Forms.DataGridView> controllo può essere modificato per impostazione predefinita:  
  
-   Se l'utente fa doppio clic o preme F2 in una cella, il controllo viene automaticamente inserisce la cella in modalità di modifica e aggiorna il contenuto della cella mentre l'utente digita.  
  
-   Se l'utente scorre alla fine della griglia, verrà visualizzato l'utente che sia presente una riga per l'aggiunta di nuovi record. Quando l'utente fa clic su questa riga, viene aggiunta una nuova riga per il <xref:System.Windows.Forms.DataGridView> controllo, con i valori predefiniti. Quando l'utente preme ESC, questa nuova riga viene rimossa.  
  
-   Se l'utente fa clic su un'intestazione di riga, viene selezionata l'intera riga.  
  
 Quando si associa un <xref:System.Windows.Forms.DataGridView> controllo a un'origine dati tramite l'impostazione relativa <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà, il controllo:  
  
-   Usa automaticamente i nomi delle colonne dell'origine dati come testo dell'intestazione di colonna.  
  
-   Viene popolato con il contenuto dell'origine dati. <xref:System.Windows.Forms.DataGridView> le colonne vengono create automaticamente per ogni colonna nell'origine dati.  
  
-   Crea una riga per ogni riga visibile nella tabella.  
  
-   Ordina automaticamente le righe basate sui dati sottostanti quando l'utente fa clic su un'intestazione di colonna.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Controllo DataGridView](datagridview-control-windows-forms.md)
