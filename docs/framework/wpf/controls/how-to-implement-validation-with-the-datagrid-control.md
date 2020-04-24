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
ms.openlocfilehash: 38b4c9cd7679f0d8da9b18fb5bd6bb729d33ed54
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646094"
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a>Procedura: implementare la convalida con il controllo DataGrid
Il <xref:System.Windows.Controls.DataGrid> controllo consente di eseguire la convalida sia a livello di cella che a livello di riga. Con la convalida a livello di cella, si convalidano le singole proprietà di un oggetto dati associato quando un utente aggiorna un valore. Con la convalida a livello di riga, si convalidano interi oggetti dati quando un utente esegue il commit delle modifiche a una riga. È inoltre possibile fornire feedback visivo personalizzato per gli errori <xref:System.Windows.Controls.DataGrid> di convalida o usare il feedback visivo predefinito fornito dal controllo.  
  
 Nelle procedure seguenti viene descritto <xref:System.Windows.Controls.DataGrid> come applicare le regole di convalida alle associazioni e personalizzare il feedback visivo.  
  
### <a name="to-validate-individual-cell-values"></a>Per convalidare singoli valori di cella  
  
- Specificare una o più regole di convalida per l'associazione utilizzata con una colonna. Questa operazione è simile alla convalida dei dati in controlli semplici, come descritto in [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md).  
  
     Nell'esempio seguente <xref:System.Windows.Controls.DataGrid> viene illustrato un controllo con quattro colonne associate a proprietà diverse di un oggetto business. Tre colonne specificano <xref:System.Windows.Controls.ExceptionValidationRule> l'oggetto impostando la <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> proprietà su `true`.  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     Quando un utente immette un valore non valido (ad esempio un numero non intero nella colonna ID corso), viene visualizzato un bordo rosso intorno alla cella. È possibile modificare questo feedback di convalida predefinito come descritto nella procedura seguente.  
  
### <a name="to-customize-cell-validation-feedback"></a>Per personalizzare il feedback sulla convalida delle celle  
  
- Impostare la <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> proprietà della colonna su uno stile appropriato per il controllo di modifica della colonna. Poiché i controlli di modifica vengono creati <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> in fase di esecuzione, non è possibile utilizzare la proprietà associata come si farebbe con i controlli semplici.  
  
     Nell'esempio seguente viene aggiornato l'esempio precedente aggiungendo uno stile di errore condiviso dalle tre colonne con regole di convalida. Quando un utente immette un valore non valido, lo stile cambia il colore di sfondo della cella e aggiunge una descrizione comando. Si noti l'utilizzo di un trigger per determinare se è presente un errore di convalida. Questa operazione è necessaria perché attualmente non è disponibile alcun modello di errore dedicato per le celle.  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     È possibile implementare una personalizzazione più estesa sostituendo l'oggetto <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> utilizzato dalla colonna.  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a>Per convalidare più valori in una singola rigaTo validate multiple values in a single row  
  
1. Implementare <xref:System.Windows.Controls.ValidationRule> una sottoclasse che controlla più proprietà dell'oggetto dati associato. Nell'implementazione <xref:System.Windows.Controls.ValidationRule.Validate%2A> del `value` metodo, eseguire <xref:System.Windows.Data.BindingGroup> il cast del valore del parametro in un'istanza. È quindi possibile accedere all'oggetto dati tramite la <xref:System.Windows.Data.BindingGroup.Items%2A> proprietà .  
  
     Nell'esempio seguente viene illustrato `StartDate` questo processo `Course` per convalidare `EndDate` se il valore della proprietà per un oggetto è precedente al relativo valore della proprietà.  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2. Aggiungere la regola <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> di convalida alla raccolta. La <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> proprietà fornisce accesso <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> diretto <xref:System.Windows.Data.BindingGroup> alla proprietà di un'istanza che raggruppa tutte le associazioni utilizzate dal controllo.  
  
     L'esempio seguente <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> imposta la proprietà in XAML. La <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> proprietà è <xref:System.Windows.Controls.ValidationStep.UpdatedValue> impostata su in modo che la convalida venga eseguita solo dopo l'aggiornamento dell'oggetto dati associato.  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     Quando un utente specifica una data di fine precedente alla data di inizio, nell'intestazione di riga viene visualizzato un punto esclamativo rosso (!). È possibile modificare questo feedback di convalida predefinito come descritto nella procedura seguente.  
  
### <a name="to-customize-row-validation-feedback"></a>Per personalizzare il feedback sulla convalida delle righeTo customize row validation feedback  
  
- Impostare la proprietà <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType>. Questa proprietà consente di personalizzare il <xref:System.Windows.Controls.DataGrid> feedback di convalida delle righe per i singoli controlli. È inoltre possibile influire su più controlli utilizzando <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> uno stile di riga implicito per impostare la proprietà.  
  
     L'esempio seguente sostituisce il feedback di convalida della riga predefinito con un indicatore più visibile. Quando un utente immette un valore non valido, nell'intestazione di riga viene visualizzato un cerchio rosso con un punto esclamativo bianco. Ciò si verifica per gli errori di convalida di righe e celle. Il messaggio di errore associato viene visualizzato in una descrizione comando.  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene fornita una dimostrazione completa per la convalida di celle e righe. La `Course` classe fornisce un oggetto <xref:System.ComponentModel.IEditableObject> dati di esempio che implementa per supportare le transazioni. Il <xref:System.Windows.Controls.DataGrid> controllo interagisce con <xref:System.ComponentModel.IEditableObject> per consentire agli utenti di annullare le modifiche premendo ESC.  
  
> [!NOTE]
> Se si utilizza Visual Basic, nella prima riga di `x:Class="DataGridValidation.MainWindow"` `x:Class="MainWindow"`MainWindow.xaml sostituire con .  
  
 Per testare la convalida, provare a eseguire le operazioni seguenti:To test the validation, try the following:  
  
- Nella colonna ID corso immettere un valore non intero.  
  
- Nella colonna Data di fine immettere una data precedente alla Data di inizio.  
  
- Eliminare il valore in ID corso, Data di inizio o Data di fine.  
  
- Per annullare un valore di cella non valido, spostare nuovamente il cursore nella cella e premere il tasto ESC.  
  
- Per annullare le modifiche per un'intera riga quando la cella corrente è in modalità di modifica, premere due volte il tasto ESC.  
  
- Quando si verifica un errore di convalida, spostare il puntatore del mouse sull'indicatore nell'intestazione di riga per visualizzare il messaggio di errore associato.  
  
 [!code-csharp[DataGrid_Validation#FullCode](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DataGrid>
- [DataGrid](datagrid.md)
- [Associazione dati](../../../desktop-wpf/data/data-binding-overview.md)
- [Implementare la convalida dell'associazioneImplement Binding Validation](../data/how-to-implement-binding-validation.md)
- [Implementare la logica di convalida negli oggetti personalizzatiImplement Validation Logic on Custom Objects](../data/how-to-implement-validation-logic-on-custom-objects.md)
