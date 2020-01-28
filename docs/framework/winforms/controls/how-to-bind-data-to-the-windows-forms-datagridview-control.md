---
title: Associare dati al controllo DataGridView
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: e2762bf363a469abf8c1e57b851d351c1cb41b62
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745083"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a>Procedura: associare dati al controllo DataGridView Windows Forms

Il controllo <xref:System.Windows.Forms.DataGridView> supporta il modello standard di data binding Windows Forms, in modo che possa essere associato a un'ampia gamma di origini dati. In genere, si esegue l'associazione a una <xref:System.Windows.Forms.BindingSource> che gestisce l'interazione con l'origine dati. Il <xref:System.Windows.Forms.BindingSource> può essere qualsiasi origine dati Windows Forms, che offre una grande flessibilità durante la scelta o la modifica del percorso dei dati. Per ulteriori informazioni sulle origini dati supportate dal controllo <xref:System.Windows.Forms.DataGridView>, vedere [Cenni preliminari sul controllo DataGridView](datagridview-control-overview-windows-forms.md).  

Visual Studio offre supporto esteso per data binding al controllo DataGridView. Per altre informazioni, vedere [procedura: associare dati al controllo DataGridView Windows Forms usando la finestra di progettazione](bind-data-to-the-datagrid-using-the-designer.md).  

Per connettere un controllo DataGridView ai dati:

1. Implementare un metodo per gestire i dettagli del recupero dei dati. Nell'esempio di codice seguente viene implementato un metodo di `GetData` che Inizializza un <xref:System.Data.SqlClient.SqlDataAdapter>e lo utilizza per popolare un <xref:System.Data.DataTable>. Il <xref:System.Data.DataTable> viene quindi associato al <xref:System.Windows.Forms.BindingSource>. 

2. Nel gestore dell'evento del modulo <xref:System.Windows.Forms.Form.Load>, associare il controllo <xref:System.Windows.Forms.DataGridView> al <xref:System.Windows.Forms.BindingSource>e chiamare il metodo `GetData` per recuperare i dati.  

## <a name="example"></a>Esempio

Questo esempio di codice completo recupera i dati da un database per popolare un controllo DataGridView in un Windows Form. Il modulo include anche pulsanti per ricaricare i dati e inviare le modifiche al database.  

L'esempio presenta i requisiti seguenti: 

- Accesso a un database di esempio Northwind SQL Server. Per ulteriori informazioni sull'installazione del database di esempio Northwind, vedere [ottenere i database di esempio per esempi di codice ADO.NET](../../data/adonet/sql/linq/downloading-sample-databases.md). 

- Riferimenti agli assembly System, System. Windows. Forms, System. Data e System. XML.  

Per compilare ed eseguire questo esempio, incollare il codice nel file di codice *Form1* in un nuovo progetto Windows Forms. Per informazioni sulla compilazione dalla riga C# di comando o Visual Basic, vedere compilazione dalla [riga di comando con csc. exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
Popolare la variabile `connectionString` nell'esempio con i valori per la connessione al database Northwind SQL Server di esempio. L'autenticazione di Windows, detta anche sicurezza integrata, è un modo più sicuro per connettersi al database rispetto all'archiviazione di una password nella stringa di connessione. Per ulteriori informazioni sulla sicurezza della connessione, vedere [proteggere le informazioni di connessione](../../data/adonet/protecting-connection-information.md).  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [Visualizzare i dati nel controllo DataGridView Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Proteggere le informazioni di connessione](../../data/adonet/protecting-connection-information.md)
