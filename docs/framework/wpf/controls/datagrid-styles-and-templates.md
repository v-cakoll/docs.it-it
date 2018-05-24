---
title: Stili e modelli di DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], DataGrid
- ControlTemplate [WPF], DataGrid
- DataGrid [WPF], styles and templates
- templates [WPF], DataGrid
- styles [WPF], DataGrid
- parts [WPF], DataGrid
ms.assetid: 9cb31d63-f148-4d25-b079-816e73f988c7
ms.openlocfilehash: 71c9b08407c6e570b42c4fbb7dc264829b5dc17c
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2018
---
# <a name="datagrid-styles-and-templates"></a>Stili e modelli di DataGrid
In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.DataGrid> controllo. È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco. Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="datagrid-parts"></a>Parti di DataGrid  
 La tabella seguente elenca le parti denominate la <xref:System.Windows.Controls.DataGrid> controllo.  
  
|Parte|Tipo|Descrizione|  
|-|-|-|  
|PART_ColumnHeadersPresenter|<xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>|La riga che contiene le intestazioni di colonna.|  
  
 Quando si crea un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.DataGrid>, il modello potrebbe contenere un <xref:System.Windows.Controls.ItemsPresenter> all'interno di un <xref:System.Windows.Controls.ScrollViewer>. (Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento nel <xref:System.Windows.Controls.DataGrid>; <xref:System.Windows.Controls.ScrollViewer> Abilita lo scorrimento all'interno del controllo).  Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario assegnare il <xref:System.Windows.Controls.ItemsPresenter> il nome, `ItemsPresenter`.  
  
 Il modello predefinito per il <xref:System.Windows.Controls.DataGrid> contiene un <xref:System.Windows.Controls.ScrollViewer> controllo. Per ulteriori informazioni sulle parti definite per il <xref:System.Windows.Controls.ScrollViewer>, vedere [ScrollViewer stili e modelli](../../../../docs/framework/wpf/controls/scrollviewer-styles-and-templates.md).  
  
## <a name="datagrid-states"></a>Stati di DataGrid  
 Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.DataGrid> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|Disabilitato|CommonStates|Il controllo è disabilitato.|  
|InvalidFocused|ValidationStates|Il controllo non è valido e ha uno stato attivo.|  
|InvalidUnfocused|ValidationStates|Il controllo non è valido e non ha uno stato attivo.|  
|Valido|ValidationStates|Il controllo è valido.|  
  
## <a name="datagridcell-parts"></a>Parti di DataGridCell  
 Il <xref:System.Windows.Controls.DataGridCell> elemento non dispone di parti denominate.  
  
## <a name="datagridcell-states"></a>Stati di DataGridCell  
 Nella tabella seguente sono elencati gli stati visivi per il <xref:System.Windows.Controls.DataGridCell> elemento.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sulla cella.|  
|Con stato attivo|FocusStates|La cella è attiva.|  
|Con stato non attivo|FocusStates|La cella non è attivo|  
|Corrente|CurrentStates|La cella è la cella corrente.|  
|Regular|CurrentStates|La cella non è la cella corrente.|  
|Visualizzazione|InteractionStates|La cella è in modalità di visualizzazione.|  
|Modifica|InteractionStates|La cella è in modalità di modifica.|  
|Selezionato|SelectionStates|La cella è selezionata.|  
|Deselezionato|SelectionStates|La cella non è selezionata.|  
|InvalidFocused|ValidationStates|La cella non è valida e ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|La cella non è valida e non è attivo.|  
|Valido|ValidationStates|La cella è valida.|  
  
## <a name="datagridrow-parts"></a>DataGridRow parti  
 Il <xref:System.Windows.Controls.DataGridRow> elemento non dispone di parti denominate.  
  
## <a name="datagridrow-states"></a>DataGridRow stati  
 Nella tabella seguente sono elencati gli stati visivi per il <xref:System.Windows.Controls.DataGridRow> elemento.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sulla riga.|  
|MouseOver_Editing|CommonStates|Il puntatore del mouse è posizionato sulla riga e la riga è in modalità di modifica.|  
|MouseOver_Selected|CommonStates|Il puntatore del mouse è posizionato sulla riga e la riga è selezionata.|  
|MouseOver_Unfocused_Editing|CommonStates|Il puntatore del mouse è posizionato sulla riga, la riga è in modalità di modifica e non è attivo.|  
|MouseOver_Unfocused_Selected|CommonStates|Il puntatore del mouse è posizionato sulla riga, la riga è selezionata e non è attivo.|  
|Normal_AlternatingRow|CommonStates|La riga è una riga alternativo.|  
|Normal_Editing|CommonStates|La riga è in modalità di modifica.|  
|Normal_Selected|CommonStates|La riga è selezionata.|  
|Unfocused_Editing|CommonStates|La riga è in modalità di modifica e non è attivo.|  
|Unfocused_Selected|CommonStates|La riga è selezionata e non è attivo.|  
|InvalidFocused|ValidationStates|Il controllo non è valido e ha uno stato attivo.|  
|InvalidUnfocused|ValidationStates|Il controllo non è valido e non ha uno stato attivo.|  
|Valido|ValidationStates|Il controllo è valido.|  
  
## <a name="datagridrowheader-parts"></a>Parti di DataGridRowHeader  
 La tabella seguente elenca le parti denominate il <xref:System.Windows.Controls.Primitives.DataGridRowHeader> elemento.  
  
|Parte|Tipo|Descrizione|  
|-|-|-|  
|PART_TopHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|L'elemento che viene utilizzato per ridimensionare l'intestazione di riga dall'inizio.|  
|PART_BottomHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|L'elemento che viene utilizzato per ridimensionare l'intestazione di riga nella parte inferiore.|  
  
## <a name="datagridrowheader-states"></a>Stati di DataGridRowHeader  
 Nella tabella seguente sono elencati gli stati visivi per il <xref:System.Windows.Controls.Primitives.DataGridRowHeader> elemento.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sulla riga.|  
|MouseOver_CurrentRow|CommonStates|Il puntatore del mouse è posizionato sulla riga e la riga è la riga corrente.|  
|MouseOver_CurrentRow_Selected|CommonStates|Il puntatore del mouse è posizionato sulla riga e la riga è selezionata e corrente.|  
|MouseOver_EditingRow|CommonStates|Il puntatore del mouse è posizionato sulla riga e la riga è in modalità di modifica.|  
|MouseOver_Selected|CommonStates|Il puntatore del mouse è posizionato sulla riga e la riga è selezionata.|  
|MouseOver_Unfocused_CurrentRow_Selected|CommonStates|Il puntatore del mouse è posizionato sulla riga, la riga è selezionata e corrente e non è attivo.|  
|MouseOver_Unfocused_EditingRow|CommonStates|Il puntatore del mouse è posizionato sulla riga, la riga è in modalità di modifica e non è attivo.|  
|MouseOver_Unfocused_Selected|CommonStates|Il puntatore del mouse è posizionato sulla riga, la riga è selezionata e non è attivo.|  
|Normal_CurrentRow|CommonStates|La riga è la riga corrente.|  
|Normal_CurrentRow_Selected|CommonStates|La riga è la riga corrente ed è selezionata.|  
|Normal_EditingRow|CommonStates|La riga è in modalità di modifica.|  
|Normal_Selected|CommonStates|La riga è selezionata.|  
|Unfocused_CurrentRow_Selected|CommonStates|La riga è la riga corrente, è selezionata e non è attivo.|  
|Unfocused_EditingRow|CommonStates|La riga è in modalità di modifica e non è attivo.|  
|Unfocused_Selected|CommonStates|La riga è selezionata e non è attivo.|  
|InvalidFocused|ValidationStates|Il controllo non è valido e ha uno stato attivo.|  
|InvalidUnfocused|ValidationStates|Il controllo non è valido e non ha uno stato attivo.|  
|Valido|ValidationStates|Il controllo è valido.|  
  
## <a name="datagridcolumnheaderspresenter-parts"></a>Parti di DataGridColumnHeadersPresenter  
 La tabella seguente elenca le parti denominate il <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter> elemento.  
  
|Parte|Tipo|Descrizione|  
|-|-|-|  
|PART_FillerColumnHeader|<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>|Segnaposto per le intestazioni di colonna.|  
  
## <a name="datagridcolumnheaderspresenter-states"></a>Stati di DataGridColumnHeadersPresenter  
 Nella tabella seguente sono elencati gli stati visivi per il <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter> elemento.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|InvalidFocused|ValidationStates|La cella non è valida e ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|La cella non è valida e non è attivo.|  
|Valido|ValidationStates|La cella è valida.|  
  
## <a name="datagridcolumnheader-parts"></a>Parti di DataGridColumnHeader  
 La tabella seguente elenca le parti denominate il <xref:System.Windows.Controls.Primitives.DataGridColumnHeader> elemento.  
  
|Parte|Tipo|Descrizione|  
|-|-|-|  
|PART_LeftHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|L'elemento che viene utilizzato per ridimensionare l'intestazione di colonna da sinistra.|  
|PART_RightHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|L'elemento che viene utilizzato per ridimensionare l'intestazione di colonna da destra.|  
  
## <a name="datagridcolumnheader-states"></a>Stati di DataGridColumnHeader  
 Nella tabella seguente sono elencati gli stati visivi per il <xref:System.Windows.Controls.Primitives.DataGridColumnHeader> elemento.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sul controllo.|  
|Premuto|CommonStates|Il controllo è premuto.|  
|SortAscending|SortStates|La colonna è ordinata in ordine crescente.|  
|SortDescending|SortStates|La colonna è ordinata in ordine decrescente.|  
|Non ordinate|SortStates|La colonna non è ordinata.|  
|InvalidFocused|ValidationStates|Il controllo non è valido e ha uno stato attivo.|  
|InvalidUnfocused|ValidationStates|Il controllo non è valido e non ha uno stato attivo.|  
|Valido|ValidationStates|Il controllo è valido.|  
  
## <a name="datagrid-controltemplate-example"></a>Esempio di ControlTemplate del controllo DataGrid  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.DataGrid> controllo e i relativi tipi associati.  
  
 [!code-xaml[ControlTemplateExamples#DataGrid](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datagrid.xaml#datagrid)]  
  
 L'esempio precedente usa una o più delle seguenti risorse.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Stili e modelli di Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Personalizzazione dei controlli](../../../../docs/framework/wpf/controls/control-customization.md)  
 [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
