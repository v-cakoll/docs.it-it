---
title: 'Procedura: implementare la convalida con il controllo DataGrid'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 78846e2b6a1d73e011441b0ccb46b8aad365d5dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a>Procedura: implementare la convalida con il controllo DataGrid
Il <xref:System.Windows.Controls.DataGrid> controllo consente di eseguire la convalida al livello di riga e cella. Con la convalida a livello di cella, convalidare le singole proprietà di un oggetto dati associati quando un utente aggiorna un valore. Con la convalida a livello di riga, si convalidano gli oggetti di tutti i dati quando un utente esegue il commit delle modifiche a una riga. È anche possibile fornire feedback visivo personalizzato per gli errori di convalida o utilizzare il feedback visivo predefinito che il <xref:System.Windows.Controls.DataGrid> fornisce controllo.  
  
 Le procedure seguenti viene descritto come applicare le regole di convalida <xref:System.Windows.Controls.DataGrid> associazioni e personalizzare il feedback visivo.  
  
### <a name="to-validate-individual-cell-values"></a>Per convalidare singoli valori di cella  
  
-   Specificare uno o più regole di convalida sull'associazione utilizzata con una colonna. È simile alla convalida dei dati nei controlli semplici, come descritto in [Panoramica del Data Binding](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
     Nell'esempio seguente un <xref:System.Windows.Controls.DataGrid> controllo con quattro colonne associate a diverse proprietà di un oggetto business. Tre delle colonne specificano il <xref:System.Windows.Controls.ExceptionValidationRule> impostando il <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> proprietà `true`.  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     Quando un utente immette un valore non valido (ad esempio, un valore diverso da integer nella colonna ID corso), verrà visualizzato un bordo rosso intorno alla cella. È possibile modificare questo feedback di convalida predefinito, come descritto nella procedura seguente.  
  
### <a name="to-customize-cell-validation-feedback"></a>Per personalizzare il feedback convalida cella  
  
-   Impostare la colonna <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> proprietà uno stile appropriato per la colonna del controllo di modifica. Poiché i controlli di modifica vengono creati in fase di esecuzione, non è possibile utilizzare il <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> proprietà come si farebbe con controlli semplici associata.  
  
     Nell'esempio seguente viene aggiornato l'esempio precedente tramite l'aggiunta di uno stile di errore condiviso da tre colonne con regole di convalida. Quando un utente immette un valore non valido, lo stile modifica il colore di sfondo della cella e aggiunge una descrizione comando. Si noti l'utilizzo di un trigger per determinare se è presente un errore di convalida. Ciò è necessario perché non è attualmente alcun modello di errore dedicato per le celle.  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     È possibile implementare la personalizzazione estesa più sostituendo il <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> utilizzate dalla colonna.  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a>Per convalidare più valori in una singola riga  
  
1.  Implementare un <xref:System.Windows.Controls.ValidationRule> sottoclasse che controlla più proprietà dell'oggetto dati associato. Nel <xref:System.Windows.Controls.ValidationRule.Validate%2A> implementazione del metodo, eseguire il cast di `value` valore del parametro da un <xref:System.Windows.Data.BindingGroup> istanza. È quindi possibile accedere all'oggetto di dati tramite il <xref:System.Windows.Data.BindingGroup.Items%2A> proprietà.  
  
     Nell'esempio seguente viene illustrato il processo per convalidare se il `StartDate` valore della proprietà per un `Course` oggetto è precedente relativo `EndDate` valore della proprietà.  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2.  Aggiungere la regola di convalida per il <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> insieme. Il <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> proprietà fornisce accesso diretto al <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> proprietà di un <xref:System.Windows.Data.BindingGroup> istanza che raggruppa tutte le associazioni utilizzate dal controllo.  
  
     L'esempio seguente imposta la <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> proprietà in XAML. Il <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> è impostata su <xref:System.Windows.Controls.ValidationStep.UpdatedValue> in modo che la convalida viene eseguita solo dopo che l'oggetto di associazione viene aggiornato.  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     Quando un utente specifica una data di fine è precedente alla data di inizio, viene visualizzato un punto esclamativo rosso (!) nell'intestazione di riga. È possibile modificare questo feedback di convalida predefinito, come descritto nella procedura seguente.  
  
### <a name="to-customize-row-validation-feedback"></a>Per personalizzare il feedback convalida riga  
  
-   Impostare la proprietà <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType>. Questa proprietà consente di personalizzare i commenti e suggerimenti di convalida di riga per le singole <xref:System.Windows.Controls.DataGrid> controlli. È inoltre possibile modificare più controlli utilizzando uno stile di riga implicita per impostare il <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> proprietà.  
  
     Nell'esempio seguente sostituisce il feedback convalida di riga predefinito con un indicatore più visibile. Quando un utente immette un valore non valido, viene visualizzato un cerchio rosso con un punto esclamativo bianco nell'intestazione di riga. Ciò avviene per gli errori di convalida sia di riga e cella. In una descrizione comando viene visualizzato il messaggio di errore associato.  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene fornita una dimostrazione completa per la convalida di celle e righe. Il `Course` classe fornisce un oggetto dati di esempio che implementa <xref:System.ComponentModel.IEditableObject> per supportare le transazioni. Il <xref:System.Windows.Controls.DataGrid> controllo interagisce con <xref:System.ComponentModel.IEditableObject> per consentire agli utenti di annullare le modifiche premendo ESC.  
  
> [!NOTE]
>  Se si utilizza Visual Basic, nella prima riga di MainWindow. XAML, sostituire `x:Class="DataGridValidation.MainWindow"` con `x:Class="MainWindow"`.  
  
 Per testare la convalida, procedere come segue:  
  
-   Nella colonna ID corso, immettere un valore non intero.  
  
-   Nella colonna della data di fine, immettere una data precedente alla data di inizio.  
  
-   Eliminare il valore ID del corso, data di inizio o la data di fine.  
  
-   Per annullare un valore di cella non valido, posizionare il cursore nella cella, premere il tasto ESC.  
  
-   Per annullare le modifiche per un'intera riga quando la cella corrente è in modalità di modifica, premere due volte il tasto ESC.  
  
-   Quando si verifica un errore di convalida, spostare il puntatore del mouse sull'indicatore nell'intestazione di riga per visualizzare il messaggio di errore associato.  
  
 [!code-csharp[DataGrid_Validation#FullCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.DataGrid>  
 [DataGrid](../../../../docs/framework/wpf/controls/datagrid.md)  
 [Data binding](../../../../docs/framework/wpf/data/data-binding-wpf.md)  
 [Implementare la convalida dell'associazione](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [Implementare la logica di convalida negli oggetti personalizzati](../../../../docs/framework/wpf/data/how-to-implement-validation-logic-on-custom-objects.md)
