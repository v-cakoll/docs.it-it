---
title: Accedere agli oggetti nell'elenco a discesa DataGridViewComboBoxCell
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], accessing objects in combo box cells
- combo boxes [Windows Forms], in DataGridView control
- combo boxes [Windows Forms], accessing objects in DataGridViewComboBoxCell drop-down lists
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
ms.openlocfilehash: 7e76ab1ac9089778e4371f4ee65b06d5ebc570bf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746317"
---
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a>Procedura: accedere agli oggetti in un elenco a discesa DataGridViewComboBoxCell Windows Form
Analogamente al controllo <xref:System.Windows.Forms.ComboBox>, i tipi <xref:System.Windows.Forms.DataGridViewComboBoxColumn> e <xref:System.Windows.Forms.DataGridViewComboBoxCell> consentono di aggiungere oggetti arbitrari ai rispettivi elenchi a discesa. Con questa funzionalità è possibile rappresentare stati complessi in un elenco a discesa senza dover archiviare gli oggetti corrispondenti in una raccolta separata.  
  
 A differenza del controllo <xref:System.Windows.Forms.ComboBox>, i tipi di <xref:System.Windows.Forms.DataGridView> non dispongono di una proprietà <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> per il recupero dell'oggetto attualmente selezionato. Al contrario, è necessario impostare la proprietà <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> sul nome di una proprietà nell'oggetto business. Quando l'utente effettua una selezione, la proprietà indicata dell'oggetto business imposta la cella <xref:System.Windows.Forms.DataGridViewCell.Value%2A> proprietà.  
  
 Per recuperare l'oggetto business tramite il valore della cella, la proprietà `ValueMember` deve indicare una proprietà che restituisce un riferimento all'oggetto business stesso. Pertanto, se il tipo dell'oggetto business non è sotto il controllo, è necessario aggiungere tale proprietà estendendo il tipo mediante ereditarietà.  
  
 Nelle procedure riportate di seguito viene illustrato come popolare un elenco a discesa con oggetti business e come recuperare gli oggetti tramite la cella <xref:System.Windows.Forms.DataGridViewCell.Value%2A> proprietà.  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a>Per aggiungere oggetti business all'elenco a discesa  
  
1. Creare una nuova <xref:System.Windows.Forms.DataGridViewComboBoxColumn> e popolare la relativa raccolta di <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A>. In alternativa, è possibile impostare la colonna <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> proprietà sulla raccolta di oggetti business. In tal caso, tuttavia, non è possibile aggiungere "non assegnati" all'elenco a discesa senza creare un oggetto business corrispondente nella raccolta.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2. Impostare le proprietà <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> e <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> indica la proprietà dell'oggetto business da visualizzare nell'elenco a discesa. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> indica la proprietà che restituisce un riferimento all'oggetto business.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3. Verificare che il tipo di oggetto business contenga una proprietà che restituisce un riferimento all'istanza corrente. Questa proprietà deve essere denominata con il valore assegnato a <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> nel passaggio precedente.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a>Per recuperare l'oggetto business attualmente selezionato  
  
- Ottenere la cella <xref:System.Windows.Forms.DataGridViewCell.Value%2A> proprietà ed eseguirne il cast al tipo di oggetto business.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio completo viene illustrato l'utilizzo di oggetti business in un elenco a discesa. Nell'esempio un controllo <xref:System.Windows.Forms.DataGridView> viene associato a una raccolta di oggetti `Task`. Ogni oggetto `Task` dispone di una proprietà `AssignedTo` che indica l'oggetto `Employee` attualmente assegnato a tale attività. Nella colonna `Assigned To` viene visualizzato il valore della proprietà `Name` per ogni dipendente assegnato o "non assegnato" Se il valore della proprietà `Task.AssignedTo` è `null`.  
  
 Per visualizzare il comportamento di questo esempio, seguire questa procedura:  
  
1. Modificare le assegnazioni nella colonna `Assigned To` selezionando valori diversi dall'elenco a discesa o premendo CTRL + 0 in una cella della casella combinata.  
  
2. Fare clic su `Generate Report` per visualizzare le assegnazioni correnti. Ciò dimostra che una modifica nella colonna `Assigned To` aggiorna automaticamente la raccolta di `tasks`.  
  
3. Fare clic su un pulsante `Request Status` per chiamare il metodo `RequestStatus` dell'oggetto `Employee` corrente per la riga. Ciò dimostra che l'oggetto selezionato è stato recuperato correttamente.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System e System.Windows.Forms.  
  
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
- [Visualizzazione di dati nel controllo DataGridView di Windows Form](displaying-data-in-the-windows-forms-datagridview-control.md)
