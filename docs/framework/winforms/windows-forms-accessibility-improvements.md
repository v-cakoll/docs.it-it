---
title: Windows Forms Accessibility Improvements
description: Informazioni sui modi in cui Windows Form di .NET Core tenta di migliorare l'accessibilità rispetto a Windows Form di .NET Framework.
ms.date: 04/20/2020
helpviewer_keywords:
- Windows Forms accessibility
- accessibility
author: M-Lipin
ms.openlocfilehash: 30eb8b3bd0aaf646ea23f4f036e822f9bba78dc4
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739752"
---
# <a name="accessibility-improvements-in-windows-forms-controls-for-net-core-30"></a>Miglioramenti dell'accessibilità nei controlli Windows Form per .NET Core 3.0

Windows Form continua a migliorare il funzionamento delle tecnologie di accessibilità per supportare meglio i clienti Di Windows Form.Windows Forms is continue to improve how it works with accessibility technologies to better better Windows Forms customers. Questi miglioramenti includono le modifiche seguenti:

- Modifiche in varie aree di interazione con le applicazioni client per l'accessibilità, incluso l'Assistente vocale.
- Modifiche alla gerarchia accessibile grazie al miglioramento della navigazione attraverso l'albero di automazione interfaccia utente.
- Modifiche nella navigazione da tastiera.

> [!IMPORTANT]
> Le modifiche all'accessibilità apportate in .NET Framework 4.7.1 a .NET Framework 4.8 sono incluse in .NET Core 3.0 e versioni successive e sono abilitate per impostazione predefinita. .NET Framework supportava le opzioni di compatibilità che consentivano alle applicazioni di rifiutare esplicitamente il nuovo comportamento dell'accessibilità. D'altra parte, .NET Core non supporta queste impostazioni e non consente alle applicazioni di rifiutare esplicitamente il comportamento di accessibilità.
  
A partire da .NET Core 3.0, le applicazioni Windows Form traggono vantaggio da tutte le nuove funzionalità di accessibilità (introdotte in .NET Framework 4.7.1 - 4.8) senza configurazione aggiuntiva.

## <a name="listbox-accessibility-support"></a>Supporto per l'accessibilità di ListBox

Le seguenti modifiche <xref:System.Windows.Forms.ListBox> si applicano al controllo:

- Supporto di Automazione interfaccia utenteUI Automation abilitato per `ListBox` il controllo.
- Migliorato `ListBox` il supporto <xref:System.Windows.Automation.ScrollItemPattern> per `ListBox` l'accessibilità aggiungendo gli elementi agli elementi e migliorando involontariamente la generazione e la gestione degli eventi di accessibilità e lo spostamento tra gli elementi dell'Assistente vocale (la navigazione tramite blocco maiuscole non è corretta e non genera la navigazione all'esterno del controllo).

## <a name="checkedlistbox-accessibility-support"></a>Supporto per l'accessibilità CheckedListBox

Le seguenti modifiche <xref:System.Windows.Forms.CheckedListBox> si applicano al controllo:

- Sono `CheckedListBox` stati corretti i limiti forniti dalle proprietà di accessibilità per le voci.
- Generale `ListBox` e `CheckedListBox` accessibilità migliorati: corretti i valori delle proprietà e il modello di evento.

## <a name="combobox-accessibility-support"></a>Supporto per l'accessibilità di ComboBox

Le seguenti modifiche <xref:System.Windows.Forms.ComboBox> si applicano al controllo:

- È stato aggiornato `ComboBox` il processo di recupero degli oggetti di accessibilità degli elementi per consentire la generazione <xref:System.Object.GetHashCode%2A> di ID per gli elementi anziché ottenere codici hash dagli elementi, che potrebbero non essere sicuri nel caso in cui la funzione venga sottoposta a override.

## <a name="datagridview-accessibility-support"></a>Supporto per l'accessibilità di DataGridViewDataGridView Accessibility support

Le seguenti modifiche <xref:System.Windows.Forms.DataGridView> si applicano al controllo:

- Corretto `DataGridView.Bounds` dalle proprietà di accessibilità per colonne, righe, celle e intestazioni corrispondenti, miglioramento delle prestazioni del calcolo del rettangolo di delimitazione. Tutti i limiti di accessibilità vengono rappresentati correttamente tenendo conto dei limiti dell'intero controllo, insieme al relativo riquadro di visualizzazione.
- Corretto `Value.IsReadOnly` il valore della proprietà che fornisce per le applicazioni client accessibili. La proprietà ora `IsReadOnly` mostra lo stato corretto per le celle.
- Risolto il <xref:System.Windows.Forms.DataGridView.CellParsing> problema relativo alla generazione di eventi per la prima modifica di cella. Il valore della cella può essere `DataGridView` modificato senza problemi, inclusa la prima interazione di controllo.
- Migliorato `DataGridView` il contrasto dei colori di sfondo quando si utilizzano i temi a contrasto elevato di Windows. È `DataGridView` stato modificato il colore di sfondo predefinito quando si utilizzano i temi HC, HC-2 e HC Black.

## <a name="propertygrid-accessibility-support"></a>Supporto per l'accessibilità propertyGrid

Le seguenti modifiche <xref:System.Windows.Forms.PropertyGrid> si applicano al controllo:

- Corretto `PropertyGrid.Bounds` fornito dalle proprietà di accessibilità per le voci della griglia, miglioramento delle prestazioni del calcolo del rettangolo di delimitazione. Per ora tutti i limiti di accessibilità vengono rappresentati correttamente tenendo conto dei limiti dell'intero controllo, insieme al relativo riquadro di visualizzazione.
- Sono stati corretti i nomi accessibili e le descrizioni dei sottocontrolli per non includere i nomi dei tipi di controllo ed evitare un doppio annuncio per i nomi dei tipi di controllo.

## <a name="toolstrip-accessibility-support"></a>Supporto per l'accessibilità di ToolStripToolStrip Accessibility support

Le seguenti modifiche <xref:System.Windows.Forms.ToolStrip> si applicano al controllo:

- Navigazione migliorata all'attraversata da `ToolStrip`, `MenuStrip`e `StatusStrip` gli elementi. Corretta `ToolStrip` e `MenuStrip` spostamento della scheda shift, a rifai clic sulle voci di menu quando viene premuto maiusc-tab up-arrow, che consente di passare all'elemento di menu in basso.
- Miglioramento `MenuStrip` della navigazione accessibile, corretto i tipi di controllo accessibili dal menu per i sottomenu per rendere i sottomenu di tipo 'Menu' anziché 'MenuItem'.

## <a name="printpreviewcontrol-and-printpreviewdialog-accessibility-support"></a>Supporto per l'accessibilità PrintPreviewControl e PrintPreviewDialog

Le seguenti modifiche si applicano ai controlli di stampa:

- Miglioramento dell'esplorazione accessibile (inclusa la navigazione dell'Assistente vocale) tramite le voci di menu.
- Migliorato il supporto dei temi ad contrasto elevato e rendendo l'elemento di controllo più contrastato.

## <a name="stringcollectioneditor-accessibility-support"></a>Supporto per l'accessibilità di StringCollectionEditor

Progettazione Windows Form ora utilizza l'editor della raccolta di stringhe con un supporto migliorato per l'accessibilità.

## <a name="monthcalendar-accessibility-support-available-in-net-core-31"></a>Supporto per l'accessibilità di MonthCalendar (disponibile in .NET Core 3.1)

Le seguenti modifiche <xref:System.Windows.Forms.MonthCalendar> si applicano al controllo:

- Sono stati aggiunti `MonthCalendar` provider di server di automazione interfaccia utente per il controllo, aggiunti provider di pattern di griglia di automazione interfaccia utente e pattern table.Added UI Automation server providers to control, added UI Automation Grid pattern providers and Table pattern providers.
- È stato modificato il tipo di controllo accessibile dalla _tabella_ al tipo di `MonthCalendar` controllo accessibile da _calendario,_ `MonthCalendar` ad eccezione del caso in cui il controllo disponga di un controllo Label precedente che definisce il nome accessibile dal controllo, in questo caso specifico il tipo di controllo accessibile diventa _table_.
- Migliorato l'annuncio `MonthCalendar` della data selezionata per il controllo.
- Supporto `MonthCalendar` di controllo migliorato per utilità per la lettura dello schermo e altri strumenti di accessibilità. In questo momento, gli utenti possono esplorare gli elementi del controllo e interagire con questi elementi utilizzando l'input solo tastiera. Con l'Assistente vocale, usa i tasti di direzione MAIUSC per scorrere gli elementi di controllo e IL tasto MAIUSC e INVIO per richiamare l'azione predefinita dell'elemento.
- Miglioramento dello spostamento `MonthCalendar` dei tasti di direzione tra gli elementi figlio con un rettangolo di messa a fuoco: rettangolo di attivazione blu per l'Assistente vocale.
- Migliorata l'accessibilità `MonthCalendar` per l'azione `MonthCalendar` di hit test per gli elementi di controllo per consentire il recupero dell'elemento accessibile figlio in base alle coordinate fornite.

## <a name="tooltips-accessibility-available-in-net-core-31"></a>Accessibilità delle descrizioni comandi (disponibile in .NET Core 3.1)ToolTips accessibility (available in .NET Core 3.1)

- Aggiunta la possibilità di annunciare il testo di una descrizione comando dalle applicazioni di lettura dello schermo come NVDA e Assistente vocale. L'applicazione screen reader può ora annunciare il testo della descrizione comando della tastiera o del mouse di qualsiasi controllo Windows Form configurato per visualizzare le descrizioni comandi.

## <a name="ui-automation-support-for-datagridview-propertygrid-listbox-combobox-toolstrip-and-other-controls"></a>Supporto dell'automazione interfaccia utente per DataGridView, PropertyGrid, ListBox, ComboBox, ToolStrip e altri controlli

Il supporto di Automazione interfaccia utenteUI Automation è abilitato per i controlli in fase di esecuzione, ma non viene usato in fase di progettazione. Per una panoramica dell'automazione interfaccia utente, vedere [Panoramica di automazione interfaccia utente](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview).

## <a name="see-also"></a>Vedere anche

- [Procedure consigliate per l'accessibilità](../ui-automation/accessibility-best-practices.md).
