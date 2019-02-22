---
title: 'Procedura: Associare dati al controllo DataGridView di Windows Form'
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f98f095f888a8ef3622fabbf4c4745af60e930e3
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584057"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a>Procedura: Associare dati al controllo DataGridView di Windows Form

Il <xref:System.Windows.Forms.DataGridView> controllo supporta il modello di associazione dati standard di Windows Form, pertanto è possibile associare a un'ampia gamma di origini dati. In genere, si associa a un <xref:System.Windows.Forms.BindingSource> che gestisce l'interazione con l'origine dati. Il <xref:System.Windows.Forms.BindingSource> può essere qualsiasi origine dati di Windows Form, che consente una notevole flessibilità, la scelta o la modifica del percorso dei dati. Per altre informazioni sulle origini dati di <xref:System.Windows.Forms.DataGridView> controllo supporta, vedere la [Cenni preliminari sul controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).  

Visual Studio offre supporto completo per il data binding al controllo DataGridView. Per altre informazioni, vedere [Procedura: Associare dati al controllo DataGridView di Windows Form usando la finestra di progettazione](bind-data-to-the-datagrid-using-the-designer.md).  

Per connettere un controllo DataGridView ai dati:

1. Implementare un metodo per gestire i dettagli del recupero dei dati. Il codice seguente esempio implementa un `GetData` metodo che inizializza un <xref:System.Data.SqlClient.SqlDataAdapter>e lo usa per popolare un <xref:System.Data.DataTable>. Viene quindi associato il <xref:System.Data.DataTable> per il <xref:System.Windows.Forms.BindingSource>. 

2. Il modulo <xref:System.Windows.Forms.Form.Load> gestore dell'evento, associare il <xref:System.Windows.Forms.DataGridView> il controllo al <xref:System.Windows.Forms.BindingSource>e chiamare il `GetData` metodo per recuperare i dati.  

## <a name="example"></a>Esempio

In questo esempio di codice completo recupera i dati da un database per popolare un controllo DataGridView in un modulo di Windows. Il form contiene inoltre i pulsanti per ricaricare i dati e inviare modifiche al database.  

L'esempio presenta i requisiti seguenti: 

- Accesso a un database di esempio Northwind di SQL Server. Per altre informazioni sull'installazione di database di esempio Northwind, vedere [ottenere i database di esempio per gli esempi di codice ADO.NET](../../data/adonet/sql/linq/downloading-sample-databases.md). 

- Riferimenti agli assembly System, System, System. Data e System. Xml.  

Per compilare ed eseguire questo esempio, incollare il codice nel *Form1* file di codice in un nuovo progetto Windows Form. Per informazioni sulla compilazione dal C# o riga di comando di Visual Basic, vedere [della riga di comando edificio con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oppure [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
Popolare il `connectionString` variabili nell'esempio con i valori per la connessione di database di esempio Northwind di SQL Server. L'autenticazione di Windows, denominato anche sicurezza integrata, è un modo più sicuro per la connessione al database di archiviare una password nella stringa di connessione. Per altre informazioni sulla sicurezza della connessione, vedere [proteggere le informazioni di connessione](../../data/adonet/protecting-connection-information.md).  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [Visualizzare i dati nel controllo DataGridView di Windows Form](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Proteggere le informazioni di connessione](../../data/adonet/protecting-connection-information.md)
