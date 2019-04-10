---
title: 'Procedura: Accedere agli oggetti in un elenco a discesa DataGridViewComboBoxCell di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], accessing objects in combo box cells
- combo boxes [Windows Forms], in DataGridView control
- combo boxes [Windows Forms], accessing objects in DataGridViewComboBoxCell drop-down lists
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
ms.openlocfilehash: 17b7c93effe9338a9e2d6cb207a948a956d9b666
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59334276"
---
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a>Procedura: Accedere agli oggetti in un elenco a discesa DataGridViewComboBoxCell di Windows Forms
Ad esempio la <xref:System.Windows.Forms.ComboBox> (controllo), il <xref:System.Windows.Forms.DataGridViewComboBoxColumn> e <xref:System.Windows.Forms.DataGridViewComboBoxCell> tipi consentono di aggiungere oggetti arbitrari agli elenchi a discesa. Con questa funzionalità, è possibile rappresentare gli stati complessi in un elenco a discesa senza la necessità di archiviare oggetti corrispondenti in una raccolta separata.  
  
 A differenza di <xref:System.Windows.Forms.ComboBox> (controllo), il <xref:System.Windows.Forms.DataGridView> tipi non è un <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> proprietà per il recupero dell'oggetto attualmente selezionato. In alternativa, è necessario impostare il <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> proprietà sul nome di una proprietà nell'oggetto business. Quando l'utente effettua una selezione, la proprietà indicata dell'oggetto business imposta la cella <xref:System.Windows.Forms.DataGridViewCell.Value%2A> proprietà.  
  
 Per recuperare l'oggetto business tramite il valore della cella, il `ValueMember` proprietà deve indicare una proprietà che restituisce un riferimento all'oggetto di business stesso. Pertanto, se il tipo dell'oggetto business non controllati dall'utente, è necessario aggiungere questo tipo di proprietà dall'estensione del tipo tramite l'ereditarietà.  
  
 Le procedure seguenti illustrano come compilare un elenco a discesa con gli oggetti business e recuperare gli oggetti tramite la cella <xref:System.Windows.Forms.DataGridViewCell.Value%2A> proprietà.  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a>Per aggiungere gli oggetti business per l'elenco a discesa  
  
1. Creare una nuova <xref:System.Windows.Forms.DataGridViewComboBoxColumn> e popolare il <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> raccolta. In alternativa, è possibile impostare la colonna <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> proprietà alla raccolta di oggetti business. In tal caso, tuttavia, non è possibile aggiungere "non assegnati" per l'elenco a discesa senza creare un oggetto business corrispondente nella raccolta.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2. Impostare le proprietà <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> e <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> indica la proprietà dell'oggetto business da visualizzare nell'elenco a discesa. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> indica la proprietà che restituisce un riferimento all'oggetto business.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3. Assicurarsi che il tipo di oggetto business contiene una proprietà che restituisce un riferimento all'istanza corrente. Questa proprietà deve essere denominata con il valore assegnato a <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> nel passaggio precedente.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a>Per recuperare l'oggetto business attualmente selezionata  
  
-   Ottiene la cella <xref:System.Windows.Forms.DataGridViewCell.Value%2A> proprietà ed eseguirne il cast al tipo di oggetto business.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a>Esempio  
 L'esempio completo viene illustrato l'utilizzo di oggetti business in un elenco a discesa. Nell'esempio, un <xref:System.Windows.Forms.DataGridView> è associato a una raccolta di `Task` oggetti. Ciascuna `Task` oggetto ha un `AssignedTo` proprietà che indica il `Employee` oggetto attualmente assegnato a tale attività. Il `Assigned To` colonna vengono visualizzati la `Name` valore della proprietà per ogni dipendente assegnato, o "non assegnati" se il `Task.AssignedTo` valore della proprietà è `null`.  
  
 Per visualizzare il comportamento di questo esempio, procedere come segue:  
  
1. Modificare le assegnazioni nel `Assigned To` colonna selezionando valori diversi dagli elenchi a discesa o premendo CTRL + 0 in una cella di casella combinata.  
  
2. Fare clic su `Generate Report` per visualizzare le assegnazioni correnti. Ciò dimostra che una modifica nel `Assigned To` colonna Aggiorna automaticamente il `tasks` raccolta.  
  
3. Fare clic su un `Request Status` il pulsante per chiamare il `RequestStatus` metodo dell'oggetto corrente `Employee` oggetto per la riga. Ciò dimostra che l'oggetto selezionato è stato recuperato.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ComboBox>
- [Visualizzazione di dati nel controllo DataGridView Windows Form](displaying-data-in-the-windows-forms-datagridview-control.md)
