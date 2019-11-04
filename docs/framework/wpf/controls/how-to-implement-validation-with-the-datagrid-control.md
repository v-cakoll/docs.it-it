---
title: 'Procedura: implementare la convalida con il controllo DataGrid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
ms.openlocfilehash: 401949aa4bea924b458a91dc00c454c97aff4895
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458463"
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a>Procedura: implementare la convalida con il controllo DataGrid
Il controllo <xref:System.Windows.Controls.DataGrid> consente di eseguire la convalida a livello di cella e di riga. Con la convalida a livello di cella, le singole proprietà di un oggetto dati associato vengono convalidate quando un utente aggiorna un valore. Con la convalida a livello di riga, è possibile convalidare interi oggetti dati quando un utente esegue il commit delle modifiche a una riga. È inoltre possibile fornire un feedback visivo personalizzato per gli errori di convalida oppure utilizzare il feedback visivo predefinito fornito dal controllo <xref:System.Windows.Controls.DataGrid>.  
  
 Nelle procedure riportate di seguito viene descritto come applicare le regole di convalida per <xref:System.Windows.Controls.DataGrid> associazioni e personalizzare il feedback visivo.  
  
### <a name="to-validate-individual-cell-values"></a>Per convalidare i valori delle singole celle  
  
- Specificare una o più regole di convalida nell'associazione utilizzata con una colonna. Questa operazione è simile alla convalida dei dati nei controlli semplici, come descritto in [Cenni preliminari sul data binding](../data/data-binding-overview.md).  
  
     Nell'esempio seguente viene illustrato un controllo <xref:System.Windows.Controls.DataGrid> con quattro colonne associate a proprietà diverse di un oggetto business. Tre colonne specificano il <xref:System.Windows.Controls.ExceptionValidationRule> impostando la proprietà <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> su `true`.  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     Quando un utente immette un valore non valido, ad esempio un valore non integer nella colonna Course ID, viene visualizzato un bordo rosso intorno alla cella. È possibile modificare questo feedback di convalida predefinito come descritto nella procedura seguente.  
  
### <a name="to-customize-cell-validation-feedback"></a>Per personalizzare il feedback sulla convalida delle celle  
  
- Impostare la proprietà <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> della colonna su uno stile appropriato per il controllo di modifica della colonna. Poiché i controlli di modifica vengono creati in fase di esecuzione, non è possibile usare la proprietà associata <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> come per i controlli semplici.  
  
     Nell'esempio seguente viene aggiornato l'esempio precedente aggiungendo uno stile di errore condiviso dalle tre colonne con regole di convalida. Quando un utente immette un valore non valido, lo stile modifica il colore di sfondo della cella e aggiunge una descrizione comando. Si noti l'uso di un trigger per determinare se si è verificato un errore di convalida. Questa operazione è necessaria perché non è attualmente disponibile un modello di errore dedicato per le celle.  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     È possibile implementare una personalizzazione più estesa sostituendo le <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> utilizzate dalla colonna.  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a>Per convalidare più valori in una singola riga  
  
1. Implementare una sottoclasse <xref:System.Windows.Controls.ValidationRule> che controlla più proprietà dell'oggetto dati associato. Nell'implementazione del metodo <xref:System.Windows.Controls.ValidationRule.Validate%2A> eseguire il cast del valore del parametro `value` a un'istanza di <xref:System.Windows.Data.BindingGroup>. È quindi possibile accedere all'oggetto dati tramite la proprietà <xref:System.Windows.Data.BindingGroup.Items%2A>.  
  
     Nell'esempio seguente viene illustrato questo processo per verificare se il valore della proprietà `StartDate` per un oggetto `Course` è precedente al relativo valore della proprietà `EndDate`.  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2. Aggiungere la regola di convalida alla raccolta di <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType>. La proprietà <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> fornisce accesso diretto alla proprietà <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> di un'istanza di <xref:System.Windows.Data.BindingGroup> che raggruppa tutte le associazioni utilizzate dal controllo.  
  
     Nell'esempio seguente viene impostata la proprietà <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> in XAML. La proprietà <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> è impostata su <xref:System.Windows.Controls.ValidationStep.UpdatedValue> in modo che la convalida avvenga solo dopo l'aggiornamento dell'oggetto dati associato.  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     Quando un utente specifica una data di fine precedente alla data di inizio, nell'intestazione di riga viene visualizzato un punto esclamativo rosso (!). È possibile modificare questo feedback di convalida predefinito come descritto nella procedura seguente.  
  
### <a name="to-customize-row-validation-feedback"></a>Per personalizzare il feedback della convalida delle righe  
  
- Impostare la proprietà <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType>. Questa proprietà consente di personalizzare il feedback della convalida delle righe per i singoli controlli <xref:System.Windows.Controls.DataGrid>. È anche possibile influenzare più controlli usando uno stile di riga implicito per impostare la proprietà <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType>.  
  
     Nell'esempio seguente viene sostituito il feedback di convalida della riga predefinito con un indicatore più visibile. Quando un utente immette un valore non valido, nell'intestazione di riga viene visualizzato un cerchio rosso con un punto esclamativo bianco. Questo problema si verifica sia per gli errori di convalida di riga che di cella. Il messaggio di errore associato viene visualizzato in una descrizione comando.  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene fornita una dimostrazione completa per la convalida di celle e righe. La classe `Course` fornisce un oggetto dati di esempio che implementa <xref:System.ComponentModel.IEditableObject> per supportare le transazioni. Il controllo <xref:System.Windows.Controls.DataGrid> interagisce con <xref:System.ComponentModel.IEditableObject> per consentire agli utenti di ripristinare le modifiche premendo ESC.  
  
> [!NOTE]
> Se si usa Visual Basic, nella prima riga di MainWindow. xaml sostituire `x:Class="DataGridValidation.MainWindow"` con `x:Class="MainWindow"`.  
  
 Per testare la convalida, provare a eseguire le operazioni seguenti:  
  
- Nella colonna Course ID immettere un valore diverso da Integer.  
  
- Nella colonna Data di fine immettere una data precedente alla data di inizio.  
  
- Eliminare il valore in ID corso, data di inizio o data di fine.  
  
- Per annullare un valore di cella non valido, posizionare nuovamente il cursore nella cella e premere il tasto ESC.  
  
- Per annullare le modifiche per un'intera riga quando la cella corrente è in modalità di modifica, premere il tasto ESC due volte.  
  
- Quando si verifica un errore di convalida, spostare il puntatore del mouse sull'indicatore nell'intestazione di riga per visualizzare il messaggio di errore associato.  
  
 [!code-csharp[DataGrid_Validation#FullCode](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DataGrid>
- [DataGrid](datagrid.md)
- [Data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Implementare la convalida dell'associazione](../data/how-to-implement-binding-validation.md)
- [Implementare la logica di convalida negli oggetti personalizzati](../data/how-to-implement-validation-logic-on-custom-objects.md)
