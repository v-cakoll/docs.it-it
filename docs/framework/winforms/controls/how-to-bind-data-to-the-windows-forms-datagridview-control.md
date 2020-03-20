---
title: Associare dati al controllo DataGridViewBind data to DataGridView Control
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 643dcd37cd1bb3f8b5938fedff66c67cd68278ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182267"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a>Procedura: associare dati al controllo DataGridView di Windows FormHow to: Bind data to the Windows Forms DataGridView control

Il <xref:System.Windows.Forms.DataGridView> controllo supporta il modello di associazione dati standard di Windows Form, pertanto può essere associato a un'ampia gamma di origini dati. In genere, si <xref:System.Windows.Forms.BindingSource> esegue l'associazione a un che gestisce l'interazione con l'origine dati. Il <xref:System.Windows.Forms.BindingSource> può essere qualsiasi origine dati Windows Form, che offre una grande flessibilità quando si sceglie o modifica la posizione dei dati. Per ulteriori informazioni sulle <xref:System.Windows.Forms.DataGridView> origini dati supportate dai controlli, vedere Panoramica del [controllo DataGridView](datagridview-control-overview-windows-forms.md).  

Visual Studio include un ampio supporto per l'associazione dati al dataGridView controllo. Per ulteriori informazioni, vedere [Procedura: associare dati al controllo DataGridView di Windows Form mediante la finestra di progettazione](bind-data-to-the-datagrid-using-the-designer.md).  

Per connettere un controllo DataGridView ai dati:

1. Implementare un metodo per gestire i dettagli del recupero dei dati. Nell'esempio di `GetData` codice riportato <xref:System.Data.SqlClient.SqlDataAdapter>di seguito viene implementato <xref:System.Data.DataTable>un metodo che inizializza un oggetto , e utilizzato per popolare un oggetto . Si lega quindi <xref:System.Data.DataTable> il <xref:System.Windows.Forms.BindingSource>al file .

2. Nel gestore <xref:System.Windows.Forms.Form.Load> eventi del form <xref:System.Windows.Forms.DataGridView> associare <xref:System.Windows.Forms.BindingSource>il controllo `GetData` a , quindi chiamare il metodo per recuperare i dati.  

## <a name="example"></a>Esempio

Questo esempio di codice completo recupera i dati da un database per popolare un DataGridView controllo in un Windows Form.This complete code example retrieves data from a database to populate a DataGridView control in a Windows Form. Il modulo dispone anche di pulsanti per ricaricare i dati e inviare le modifiche al database.  

L'esempio presenta i requisiti seguenti:

- Accesso a un database di esempio Northwind SQL Server. Per ulteriori informazioni sull'installazione del database di esempio Northwind, vedere [Ottenere i database di esempio per ADO.NET esempi](../../data/adonet/sql/linq/downloading-sample-databases.md)di codice .

- Riferimenti agli assembly System, System.Windows.Forms, System.Data e System.Xml.  

Per compilare ed eseguire questo esempio, incollare il codice nel file di codice Form1 in un nuovo progetto Windows Form.To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project. Per informazioni sulla compilazione dalla riga di comando di Visual Basic o di C, vedere Compilazione dalla riga di comando [con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o [Compilazione dalla riga](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)di comando .  
  
Popolare `connectionString` la variabile nell'esempio con i valori per la connessione al database di esempio Northwind SQL Server. L'autenticazione di Windows, detta anche sicurezza integrata, è un modo più sicuro per connettersi al database rispetto all'archiviazione di una password nella stringa di connessione. Per ulteriori informazioni sulla sicurezza della connessione, vedere [Proteggere le informazioni di connessione](../../data/adonet/protecting-connection-information.md).  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [Visualizzare dati nel controllo DataGridView di Windows FormDisplay data in the Windows Forms DataGridView control](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Proteggere le informazioni di connessione](../../data/adonet/protecting-connection-information.md)
