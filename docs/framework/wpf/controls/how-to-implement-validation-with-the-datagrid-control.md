---
title: 'Procedura: Implementare la convalida con il controllo DataGrid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
ms.openlocfilehash: 00d09c62aae67e3438816409c95ccf96050b3206
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305956"
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a>Procedura: Implementare la convalida con il controllo DataGrid
Il <xref:System.Windows.Controls.DataGrid> controllo consente di eseguire la convalida a livello di cella e di riga. Con la convalida a livello di cella, si convalidano le singole proprietà di un oggetto dati associato quando un utente aggiorna un valore. Con la convalida a livello di riga, si convalidano gli oggetti di tutti i dati quando un utente esegue il commit delle modifiche a una riga. È anche possibile fornire feedback visivo personalizzato per gli errori di convalida o usare il feedback visivo predefinito che il <xref:System.Windows.Controls.DataGrid> fornisce controllo.  
  
 Le procedure seguenti descrivono come applicare le regole di convalida a <xref:System.Windows.Controls.DataGrid> associazioni e personalizzare il feedback visivo.  
  
### <a name="to-validate-individual-cell-values"></a>Per convalidare i valori delle singole celle  
  
-   Specificare uno o più regole di convalida sull'associazione utilizzata con una colonna. Come avviene per la convalida dei dati nei controlli semplici, come descritto in [Panoramica sul Data Binding](../data/data-binding-overview.md).  
  
     L'esempio seguente mostra un <xref:System.Windows.Controls.DataGrid> controllo con quattro colonne associate a diverse proprietà dell'oggetto business. Tre delle colonne di specificare il <xref:System.Windows.Controls.ExceptionValidationRule> impostando la <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> proprietà `true`.  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     Quando un utente immette un valore non valido (ad esempio, non integer nella colonna Course ID), viene visualizzato un bordo rosso attorno alla cella. È possibile modificare questo feedback convalida predefinita come descritto nella procedura seguente.  
  
### <a name="to-customize-cell-validation-feedback"></a>Per personalizzare il feedback di convalida di cella  
  
-   Impostare la colonna <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> proprietà a uno stile appropriato per la colonna del controllo di modifica. Poiché i controlli di modifica vengono creati in fase di esecuzione, è possibile utilizzare il <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> proprietà come si farebbe con semplici controlli associata.  
  
     L'esempio seguente aggiorna l'esempio precedente mediante l'aggiunta di uno stile di errore condiviso da tre colonne con regole di convalida. Quando un utente immette un valore non valido, lo stile di modifica il colore di sfondo della cella e aggiunge una descrizione comando. Si noti l'uso di un trigger per determinare se è presente un errore di convalida. Ciò è necessario perché non è attualmente alcun modello errori dedicato per le celle.  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     È possibile implementare la personalizzazione più estesa, sostituendo il <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> utilizzate dalla colonna.  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a>Per convalidare più valori in una singola riga  
  
1. Implementare un <xref:System.Windows.Controls.ValidationRule> sottoclasse che controlla più proprietà dell'oggetto dati associato. Nel <xref:System.Windows.Controls.ValidationRule.Validate%2A> eseguire il cast di implementazione del metodo, il `value` valore del parametro da un <xref:System.Windows.Data.BindingGroup> istanza. È quindi possibile accedere all'oggetto dati attraverso il <xref:System.Windows.Data.BindingGroup.Items%2A> proprietà.  
  
     L'esempio seguente illustra questo processo di convalida se il `StartDate` valore della proprietà per un `Course` oggetto è precedente relativo `EndDate` valore della proprietà.  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2. Aggiungere la regola di convalida per il <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> raccolta. Il <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> proprietà fornisce accesso diretto al <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> proprietà di un <xref:System.Windows.Data.BindingGroup> istanza che raggruppa tutte le associazioni utilizzate dal controllo.  
  
     L'esempio seguente imposta il <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> proprietà in XAML. Il <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> è impostata su <xref:System.Windows.Controls.ValidationStep.UpdatedValue> in modo che la convalida viene eseguita solo dopo aver aggiornato l'oggetto dati associato.  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     Quando un utente specifica una data di fine precedente alla data di inizio, viene visualizzato un punto esclamativo rosso (!) nell'intestazione di riga. È possibile modificare questo feedback convalida predefinita come descritto nella procedura seguente.  
  
### <a name="to-customize-row-validation-feedback"></a>Per personalizzare il feedback di convalida di riga  
  
-   Impostare la proprietà <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType>. Questa proprietà consente di personalizzare il feedback di convalida di riga per i singoli <xref:System.Windows.Controls.DataGrid> controlli. È inoltre possibile modificare più controlli usando uno stile di riga implicita per impostare il <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> proprietà.  
  
     Nell'esempio seguente sostituisce il feedback di convalida di riga predefinito con un indicatore di più visibile. Quando un utente immette un valore non valido, viene visualizzato un cerchio rosso con un punto esclamativo bianco nell'intestazione di riga. Ciò avviene per gli errori di convalida di righe e celle. In una descrizione comando viene visualizzato il messaggio di errore associato.  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene fornita una spiegazione completa per la convalida di celle e righe. Il `Course` classe fornisce un oggetto dati di esempio che implementa <xref:System.ComponentModel.IEditableObject> per supportare le transazioni. Il <xref:System.Windows.Controls.DataGrid> tale controllo interagisce con <xref:System.ComponentModel.IEditableObject> per consentire agli utenti di annullare le modifiche premendo ESC.  
  
> [!NOTE]
>  Se si usa Visual Basic, nella prima riga del file MainWindow. XAML, sostituire `x:Class="DataGridValidation.MainWindow"` con `x:Class="MainWindow"`.  
  
 Per testare la convalida, procedere come segue:  
  
-   Nella colonna ID del corso, immettere un valore diverso da integer.  
  
-   Nella colonna relativa alla data di fine, immettere una data precedente alla data di inizio.  
  
-   Eliminare il valore ID del corso, data di inizio o la data di fine.  
  
-   Per annullare un valore di cella non è valido, posizionare il cursore nella cella e premere il tasto ESC.  
  
-   Per annullare le modifiche per un'intera riga quando la cella corrente si trova in modalità di modifica, premere il tasto ESC due volte.  
  
-   Quando si verifica un errore di convalida, spostare il puntatore del mouse sull'indicatore nell'intestazione di riga per visualizzare il messaggio di errore associato.  
  
 [!code-csharp[DataGrid_Validation#FullCode](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DataGrid>
- [DataGrid](datagrid.md)
- [Data binding](../data/data-binding-wpf.md)
- [Implementare la convalida del binding](../data/how-to-implement-binding-validation.md)
- [Implementare la logica di convalida negli oggetti personalizzati](../data/how-to-implement-validation-logic-on-custom-objects.md)
