---
title: 'Procedura: Associare un oggetto DataView a un controllo DataGridView di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b73d60a-6049-446a-85a7-3e5a68b183e2
ms.openlocfilehash: 3a3089073cdc5afb4ee51caca9114b401c740b45
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795012"
---
# <a name="how-to-bind-a-dataview-object-to-a-windows-forms-datagridview-control"></a>Procedura: Associare un oggetto DataView a un controllo DataGridView di Windows Form
Il controllo <xref:System.Windows.Forms.DataGridView> fornisce un sistema efficiente e flessibile per visualizzare i dati in formato tabulare. Il controllo <xref:System.Windows.Forms.DataGridView> supporta il modello di data binding standard di Windows Form ed è quindi possibile associarlo a <xref:System.Data.DataView> e a varie altre origini dati. Nella maggior parte dei casi, tuttavia, l'associazione viene eseguita a un componente <xref:System.Windows.Forms.BindingSource>, che gestisce i dettagli dell'interazione con l'origine dati.  
  
 Per ulteriori informazioni sul <xref:System.Windows.Forms.DataGridView> controllo, vedere [Cenni preliminari sul controllo DataGridView](../../winforms/controls/datagridview-control-overview-windows-forms.md).  
  
### <a name="to-connect-a-datagridview-control-to-a-dataview"></a>Per connettere un controllo DataGridView a un oggetto DataView  
  
1. Implementare un metodo per gestire i dettagli del recupero di dati da un database. Nell'esempio di codice seguente viene implementato un metodo `GetData` che inizializza un componente <xref:System.Data.SqlClient.SqlDataAdapter> e lo usa per compilare <xref:System.Data.DataSet>. Assicurarsi di impostare la variabile `connectionString` su un valore appropriato per il database. Sarà necessario disporre di accesso a un server in cui sia installato il database SQL Server di esempio AdventureWorks.  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1getdata)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1getdata)]  
  
2. Nel gestore eventi <xref:System.Windows.Forms.Form.Load> del form associare il controllo <xref:System.Windows.Forms.DataGridView> al componente <xref:System.Windows.Forms.BindingSource> e chiamare il metodo `GetData` per recuperare i dati dal database. Viene creato da una query LINQ to DataSet sul contatto <xref:System.Data.DataTable> e <xref:System.Windows.Forms.BindingSource> viene quindi associato al componente. <xref:System.Data.DataView>  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1formload)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1formload)]  
  
## <a name="see-also"></a>Vedere anche

- [Data binding e LINQ to DataSet](data-binding-and-linq-to-dataset.md)
