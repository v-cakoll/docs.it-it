---
title: 'Procedura: associare dati al controllo DataGridView di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 4064ef26ee550c02ac8825ac4c1a417472b64de6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43419922"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a>Procedura: associare dati al controllo DataGridView di Windows Form
Il controllo <xref:System.Windows.Forms.DataGridView> supporta il modello di data binding standard di Windows Form che consente l'associazione a un'ampia gamma di origini dati. Nella maggior parte dei casi, tuttavia, l'associazione verrà eseguita a un componente <xref:System.Windows.Forms.BindingSource> che gestisce i dettagli dell'interazione con l'origine dati. Il componente <xref:System.Windows.Forms.BindingSource> può rappresentare qualsiasi origine dati di Windows Form e offre una notevole flessibilità per la scelta o la modifica del percorso dei dati. Per altre informazioni sulle origini dati supportate per il <xref:System.Windows.Forms.DataGridView> controllano, vedere [Cenni preliminari sul controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).  
  
 In Visual Studio è disponibile supporto completo per questa attività.  Vedere anche [Procedura: Associare dati al controllo DataGridView di Windows Form usando la finestra di progettazione](https://msdn.microsoft.com/library/33w255ac\(v=vs.110\)).  
  
## <a name="procedure"></a>Routine  
  
#### <a name="to-connect-a-datagridview-control-to-data"></a>Per connettere un controllo DataGridView ai dati  
  
1.  Implementare un metodo per gestire i dettagli del recupero di dati da un database. L'esempio di codice seguente implementa un metodo `GetData` che inizializza un componente <xref:System.Data.SqlClient.SqlDataAdapter> e lo usa per popolare un <xref:System.Data.DataTable>. <xref:System.Data.DataTable> viene quindi associato al componente <xref:System.Windows.Forms.BindingSource>. Assicurarsi di impostare la variabile `connectionString` su un valore appropriato per il database. È necessario accedere a un server con installato il database di esempio Northwind di SQL Server.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#20)]
     [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#20)]  
  
2.  Nel gestore eventi del form <xref:System.Windows.Forms.Form.Load> associare il controllo <xref:System.Windows.Forms.DataGridView> al componente <xref:System.Windows.Forms.BindingSource> e chiamare il metodo `GetData` per recuperare i dati dal database.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#10)]
     [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#10)]  
  
## <a name="example"></a>Esempio  
 L'esempio di codice completo seguente fornisce i pulsanti per ricaricare i dati dal database e inviare le modifiche al database.  
  
 [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#00)]
 [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System, System.Windows.Forms, System.Data e System.Xml.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo tramite Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.BindingSource>  
 [Visualizzazione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md)
