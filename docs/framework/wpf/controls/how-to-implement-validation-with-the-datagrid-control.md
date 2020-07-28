---
title: 'Procedura: Implementare la convalida con il controllo DataGrid'
description: Informazioni sul modo in cui il controllo DataGrid Windows Presentation Foundation può eseguire la convalida a livello di cella e di riga e fornire commenti e suggerimenti sugli errori di convalida.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
ms.openlocfilehash: a6fe3693f94c3f554e96bc167b572cf854a1a34a
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167607"
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a>Procedura: Implementare la convalida con il controllo DataGrid
Il <xref:System.Windows.Controls.DataGrid> controllo consente di eseguire la convalida a livello di cella e di riga. Con la convalida a livello di cella, le singole proprietà di un oggetto dati associato vengono convalidate quando un utente aggiorna un valore. Con la convalida a livello di riga, è possibile convalidare interi oggetti dati quando un utente esegue il commit delle modifiche a una riga. È inoltre possibile fornire un feedback visivo personalizzato per gli errori di convalida oppure utilizzare il feedback visivo predefinito <xref:System.Windows.Controls.DataGrid> fornito dal controllo.  
  
 Nelle procedure seguenti viene descritto come applicare regole di convalida alle <xref:System.Windows.Controls.DataGrid> associazioni e personalizzare il feedback visivo.  
  
### <a name="to-validate-individual-cell-values"></a>Per convalidare i valori delle singole celle  
  
- Specificare una o più regole di convalida nell'associazione utilizzata con una colonna. Questa operazione è simile alla convalida dei dati nei controlli semplici, come descritto in [Cenni preliminari sul data binding](../../../desktop-wpf/data/data-binding-overview.md).  
  
     Nell'esempio seguente viene illustrato un <xref:System.Windows.Controls.DataGrid> controllo con quattro colonne associate a proprietà diverse di un oggetto business. Tre delle colonne specificano l'oggetto impostando <xref:System.Windows.Controls.ExceptionValidationRule> la <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> proprietà su `true` .  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     Quando un utente immette un valore non valido, ad esempio un valore non integer nella colonna Course ID, viene visualizzato un bordo rosso intorno alla cella. È possibile modificare questo feedback di convalida predefinito come descritto nella procedura seguente.  
  
### <a name="to-customize-cell-validation-feedback"></a>Per personalizzare il feedback sulla convalida delle celle  
  
- Impostare la proprietà della colonna <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> su uno stile appropriato per il controllo di modifica della colonna. Poiché i controlli di modifica vengono creati in fase di esecuzione, non è possibile usare la <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> proprietà associata come per i controlli semplici.  
  
     Nell'esempio seguente viene aggiornato l'esempio precedente aggiungendo uno stile di errore condiviso dalle tre colonne con regole di convalida. Quando un utente immette un valore non valido, lo stile modifica il colore di sfondo della cella e aggiunge una descrizione comando. Si noti l'uso di un trigger per determinare se si è verificato un errore di convalida. Questa operazione è necessaria perché non è attualmente disponibile un modello di errore dedicato per le celle.  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     È possibile implementare una personalizzazione più estesa sostituendo l'oggetto <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> utilizzato dalla colonna.  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a>Per convalidare più valori in una singola riga  
  
1. Implementare una <xref:System.Windows.Controls.ValidationRule> sottoclasse che controlla più proprietà dell'oggetto dati associato. Nell' <xref:System.Windows.Controls.ValidationRule.Validate%2A> implementazione del metodo, eseguire il cast del `value` valore del parametro a un' <xref:System.Windows.Data.BindingGroup> istanza di. È quindi possibile accedere all'oggetto dati tramite la <xref:System.Windows.Data.BindingGroup.Items%2A> Proprietà.  
  
     Nell'esempio seguente viene illustrato questo processo per verificare se il `StartDate` valore della proprietà per un `Course` oggetto è precedente rispetto al `EndDate` valore della proprietà.  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2. Aggiungere la regola di convalida alla <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> raccolta. La <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> proprietà fornisce l'accesso diretto alla <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> proprietà di un' <xref:System.Windows.Data.BindingGroup> istanza di che raggruppa tutte le associazioni utilizzate dal controllo.  
  
     Nell'esempio seguente viene impostata la <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> Proprietà in XAML. La <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> proprietà è impostata su in <xref:System.Windows.Controls.ValidationStep.UpdatedValue> modo che la convalida avvenga solo dopo l'aggiornamento dell'oggetto dati associato.  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     Quando un utente specifica una data di fine precedente alla data di inizio, nell'intestazione di riga viene visualizzato un punto esclamativo rosso (!). È possibile modificare questo feedback di convalida predefinito come descritto nella procedura seguente.  
  
### <a name="to-customize-row-validation-feedback"></a>Per personalizzare il feedback della convalida delle righe  
  
- Impostare la proprietà <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType>. Questa proprietà consente di personalizzare il feedback di convalida delle righe per i singoli <xref:System.Windows.Controls.DataGrid> controlli. È anche possibile influenzare più controlli usando uno stile di riga implicito per impostare la <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> Proprietà.  
  
     Nell'esempio seguente viene sostituito il feedback di convalida della riga predefinito con un indicatore più visibile. Quando un utente immette un valore non valido, nell'intestazione di riga viene visualizzato un cerchio rosso con un punto esclamativo bianco. Questo problema si verifica sia per gli errori di convalida di riga che di cella. Il messaggio di errore associato viene visualizzato in una descrizione comando.  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene fornita una dimostrazione completa per la convalida di celle e righe. La `Course` classe fornisce un oggetto dati di esempio che implementa <xref:System.ComponentModel.IEditableObject> per supportare le transazioni. Il <xref:System.Windows.Controls.DataGrid> controllo interagisce con <xref:System.ComponentModel.IEditableObject> per consentire agli utenti di ripristinare le modifiche premendo ESC.  
  
> [!NOTE]
> Se si usa Visual Basic, nella prima riga di MainWindow. xaml sostituire `x:Class="DataGridValidation.MainWindow"` con `x:Class="MainWindow"` .  
  
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
- [Data Binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Implementare la convalida dell'associazione](../data/how-to-implement-binding-validation.md)
- [Implementare la logica di convalida negli oggetti personalizzati](../data/how-to-implement-validation-logic-on-custom-objects.md)
