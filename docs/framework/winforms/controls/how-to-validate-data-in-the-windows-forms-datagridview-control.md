---
title: Convalidare i dati nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
ms.assetid: d10aef35-701e-4a3c-a684-2a2ed1aeaca6
ms.openlocfilehash: 5fd881829f87fa1dec135d936f22996f196b0594
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728302"
---
# <a name="how-to-validate-data-in-the-windows-forms-datagridview-control"></a>Procedura: convalidare dati nel controllo DataGridView di Windows Form
Nell'esempio di codice seguente viene illustrato come convalidare i dati immessi da un utente in un controllo <xref:System.Windows.Forms.DataGridView>. In questo esempio il controllo <xref:System.Windows.Forms.DataGridView> viene compilato con righe della tabella `Customers` del database di esempio Northwind. Quando l'utente modifica una cella nella colonna `CompanyName`, viene verificato che il valore non sia vuoto e che sia valido. Se il gestore dell'evento <xref:System.Windows.Forms.DataGridView.CellValidating> rileva che il valore è una stringa vuota, il controllo <xref:System.Windows.Forms.DataGridView> impedisce all'utente di uscire dalla cella fino a quando non immette una stringa non vuota.  
  
 Per una spiegazione completa di questo esempio di codice, vedere [Procedura dettagliata: Convalida di dati nel controllo DataGridView Windows Form](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Data, System.Windows.Forms e System.XML.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Procedura dettagliata: convalida di dati nel controllo DataGridView di Windows Form](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [Immissione di dati nel controllo DataGridView di Windows Form](data-entry-in-the-windows-forms-datagridview-control.md)
- [Procedura dettagliata: Gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Form](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md)
