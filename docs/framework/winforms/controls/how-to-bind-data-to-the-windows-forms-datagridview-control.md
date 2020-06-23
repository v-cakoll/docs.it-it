---
title: Associare dati al controllo DataGridView
ms.date: 02/08/2019
description: Informazioni sul modo in cui il controllo DataGridView supporta il modello di data binding Windows Forms standard in modo che possa essere associato a un'ampia gamma di origini dati.
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 3c3502804d1bc4a5eeffc22b4ec5f2773411ef69
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904416"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a>Procedura: associare dati al controllo DataGridView Windows Forms

Il <xref:System.Windows.Forms.DataGridView> controllo supporta il modello di data binding Windows Forms standard, in modo che possa essere associato a un'ampia gamma di origini dati. In genere, si esegue l'associazione a un oggetto <xref:System.Windows.Forms.BindingSource> che gestisce l'interazione con l'origine dati. <xref:System.Windows.Forms.BindingSource>Può essere qualsiasi origine dati Windows Forms, che offre una grande flessibilità durante la scelta o la modifica del percorso dei dati. Per ulteriori informazioni sulle origini dati <xref:System.Windows.Forms.DataGridView> supportate dal controllo, vedere [Cenni preliminari sul controllo DataGridView](datagridview-control-overview-windows-forms.md).  

Visual Studio offre supporto esteso per data binding al controllo DataGridView. Per altre informazioni, vedere [procedura: associare dati al controllo DataGridView Windows Forms usando la finestra di progettazione](bind-data-to-the-datagrid-using-the-designer.md).  

Per connettere un controllo DataGridView ai dati:

1. Implementare un metodo per gestire i dettagli del recupero dei dati. Nell'esempio di codice seguente viene implementato un `GetData` metodo che Inizializza un oggetto <xref:System.Data.SqlClient.SqlDataAdapter> e lo utilizza per popolare un oggetto <xref:System.Data.DataTable> . Associa quindi <xref:System.Data.DataTable> a <xref:System.Windows.Forms.BindingSource> .

2. Nel <xref:System.Windows.Forms.Form.Load> gestore eventi del form, associare il <xref:System.Windows.Forms.DataGridView> controllo a <xref:System.Windows.Forms.BindingSource> e chiamare il `GetData` metodo per recuperare i dati.  

## <a name="example"></a>Esempio

Questo esempio di codice completo recupera i dati da un database per popolare un controllo DataGridView in un Windows Form. Il modulo include anche pulsanti per ricaricare i dati e inviare le modifiche al database.  

L'esempio presenta i requisiti seguenti:

- Accesso a un database di esempio Northwind SQL Server. Per ulteriori informazioni sull'installazione del database di esempio Northwind, vedere [ottenere i database di esempio per esempi di codice ADO.NET](../../data/adonet/sql/linq/downloading-sample-databases.md).

- Riferimenti agli assembly System, System. Windows. Forms, System. Data e System.Xml.  

Per compilare ed eseguire questo esempio, incollare il codice nel file di codice *Form1* in un nuovo progetto Windows Forms. Per informazioni sulla compilazione dalla riga di comando C# o Visual Basic, vedere compilazione dalla [riga di comando con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
Popolare la `connectionString` variabile nell'esempio con i valori per la connessione al database di esempio Northwind SQL Server. L'autenticazione di Windows, detta anche sicurezza integrata, è un modo più sicuro per connettersi al database rispetto all'archiviazione di una password nella stringa di connessione. Per ulteriori informazioni sulla sicurezza della connessione, vedere [proteggere le informazioni di connessione](../../data/adonet/protecting-connection-information.md).  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [Visualizzare i dati nel controllo DataGridView Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Proteggere le informazioni di connessione](../../data/adonet/protecting-connection-information.md)
