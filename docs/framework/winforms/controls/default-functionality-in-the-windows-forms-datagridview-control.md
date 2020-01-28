---
title: Funzionalità predefinite nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: b695883ac7ec3fb0c459adb66214b0eceab3a128
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746129"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a>Funzionalità predefinite nel controllo DataGridView Windows Form
Il controllo Windows Forms <xref:System.Windows.Forms.DataGridView> fornisce agli utenti una quantità significativa di funzionalità predefinite.  
  
## <a name="default-functionality"></a>Funzionalità predefinite  
 Per impostazione predefinita, un controllo <xref:System.Windows.Forms.DataGridView>:  
  
- Visualizza automaticamente le intestazioni di colonna e le intestazioni di riga che rimangono visibili quando la tabella scorre verticalmente.  
  
- Dispone di un'intestazione di riga che contiene un indicatore di selezione per la riga corrente.  
  
- Dispone di un rettangolo di selezione nella prima cella.  
  
- Include colonne che possono essere ridimensionate automaticamente quando l'utente fa doppio clic sui divisori di colonna.  
  
- Supporta automaticamente gli stili di visualizzazione in Windows XP e la famiglia Windows Server 2003 quando il metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> viene chiamato dal metodo `Main` dell'applicazione.  
  
 Inoltre, è possibile modificare il contenuto di un controllo <xref:System.Windows.Forms.DataGridView> per impostazione predefinita:  
  
- Se l'utente fa doppio clic o preme F2 in una cella, il controllo inserisce automaticamente la cella in modalità di modifica e aggiorna il contenuto della cella come tipi di utente.  
  
- Se l'utente scorre fino alla fine della griglia, l'utente noterà che è presente una riga per l'aggiunta di nuovi record. Quando l'utente fa clic su questa riga, viene aggiunta una nuova riga al controllo <xref:System.Windows.Forms.DataGridView> con i valori predefiniti. Quando l'utente preme ESC, la nuova riga scompare.  
  
- Se l'utente fa clic su un'intestazione di riga, viene selezionata l'intera riga.  
  
 Quando si associa un controllo <xref:System.Windows.Forms.DataGridView> a un'origine dati impostando la relativa proprietà <xref:System.Windows.Forms.DataGridView.DataSource%2A>, il controllo:  
  
- Usa automaticamente i nomi delle colonne dell'origine dati come testo dell'intestazione di colonna.  
  
- Viene popolato con il contenuto dell'origine dati. <xref:System.Windows.Forms.DataGridView> colonne vengono create automaticamente per ogni colonna nell'origine dati.  
  
- Crea una riga per ogni riga visibile della tabella.  
  
- Ordina automaticamente le righe in base ai dati sottostanti quando l'utente fa clic su un'intestazione di colonna.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Controllo DataGridView](datagridview-control-windows-forms.md)
