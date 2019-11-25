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
ms.openlocfilehash: 066e8c9ce1112399be8128d0821498f0d56a3dc3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283797"
---
# <a name="datagrid-styles-and-templates"></a>Stili e modelli di DataGrid
In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.DataGrid>. È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco. Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="datagrid-parts"></a>Parti DataGrid  
 Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.DataGrid>.  
  
|Parte|Digitare|description|  
|-|-|-|  
|PART_ColumnHeadersPresenter|<xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>|Riga che contiene le intestazioni di colonna.|  
  
 Quando si crea un <xref:System.Windows.Controls.ControlTemplate> per una <xref:System.Windows.Controls.DataGrid>, il modello potrebbe contenere un <xref:System.Windows.Controls.ItemsPresenter> all'interno di una <xref:System.Windows.Controls.ScrollViewer>. Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento del <xref:System.Windows.Controls.DataGrid>. il <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo.  Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario assegnare al <xref:System.Windows.Controls.ItemsPresenter> il nome `ItemsPresenter`.  
  
 Il modello predefinito per il <xref:System.Windows.Controls.DataGrid> contiene un controllo <xref:System.Windows.Controls.ScrollViewer>. Per altre informazioni sulle parti definite dalla <xref:System.Windows.Controls.ScrollViewer>, vedere [stili e modelli di ScrollViewer](scrollviewer-styles-and-templates.md).  
  
## <a name="datagrid-states"></a>Stati DataGrid  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.DataGrid>.  
  
|Nome VisualState|Nome VisualStateGroup|description|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|Disabilitato|CommonStates|Il controllo è disabilitato.|  
|InvalidFocused|ValidationStates|Il controllo non è valido e ha uno stato attivo.|  
|InvalidUnfocused|ValidationStates|Il controllo non è valido e non ha uno stato attivo.|  
|Valido|ValidationStates|Il controllo è valido.|  
  
## <a name="datagridcell-parts"></a>Parti DataGridCell  
 L'elemento <xref:System.Windows.Controls.DataGridCell> non dispone di parti denominate.  
  
## <a name="datagridcell-states"></a>Stati di DataGridCell  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per l'elemento <xref:System.Windows.Controls.DataGridCell>.  
  
|Nome VisualState|Nome VisualStateGroup|description|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse viene posizionato sulla cella.|  
|Con stato attivo|FocusStates|La cella ha lo stato attivo.|  
|Con stato non attivo|FocusStates|La cella non ha lo stato attivo|  
|Corrente|CurrentStates|La cella è la cella corrente.|  
|Regular|CurrentStates|La cella non è la cella corrente.|  
|Display|InteractionStates|La cella è in modalità di visualizzazione.|  
|Modifica|InteractionStates|La cella è in modalità di modifica.|  
|Selezionato|SelectionStates|La cella è selezionata.|  
|Deselezionato|SelectionStates|La cella non è selezionata.|  
|InvalidFocused|ValidationStates|La cella non è valida e ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|La cella non è valida e non ha lo stato attivo.|  
|Valido|ValidationStates|La cella è valida.|  
  
## <a name="datagridrow-parts"></a>Parti DataGridRow  
 L'elemento <xref:System.Windows.Controls.DataGridRow> non dispone di parti denominate.  
  
## <a name="datagridrow-states"></a>Stati di DataGridRow  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per l'elemento <xref:System.Windows.Controls.DataGridRow>.  
  
|Nome VisualState|Nome VisualStateGroup|description|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse viene posizionato sulla riga.|  
|MouseOver_Editing|CommonStates|Il puntatore del mouse viene posizionato sulla riga e la riga è in modalità di modifica.|  
|MouseOver_Selected|CommonStates|Il puntatore del mouse viene posizionato sulla riga e la riga è selezionata.|  
|MouseOver_Unfocused_Editing|CommonStates|Il puntatore del mouse viene posizionato sulla riga, la riga è in modalità di modifica e non ha lo stato attivo.|  
|MouseOver_Unfocused_Selected|CommonStates|Il puntatore del mouse viene posizionato sulla riga, la riga è selezionata e non ha lo stato attivo.|  
|Normal_AlternatingRow|CommonStates|La riga è una riga alternata.|  
|Normal_Editing|CommonStates|La riga è in modalità di modifica.|  
|Normal_Selected|CommonStates|La riga è selezionata.|  
|Unfocused_Editing|CommonStates|La riga è in modalità di modifica e non ha lo stato attivo.|  
|Unfocused_Selected|CommonStates|La riga è selezionata e non ha lo stato attivo.|  
|InvalidFocused|ValidationStates|Il controllo non è valido e ha uno stato attivo.|  
|InvalidUnfocused|ValidationStates|Il controllo non è valido e non ha uno stato attivo.|  
|Valido|ValidationStates|Il controllo è valido.|  
  
## <a name="datagridrowheader-parts"></a>Parti DataGridRowHeader  
 Nella tabella seguente sono elencate le parti denominate per l'elemento <xref:System.Windows.Controls.Primitives.DataGridRowHeader>.  
  
|Parte|Digitare|description|  
|-|-|-|  
|PART_TopHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Elemento utilizzato per ridimensionare l'intestazione di riga dalla parte superiore.|  
|PART_BottomHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Elemento utilizzato per ridimensionare l'intestazione di riga dalla parte inferiore.|  
  
## <a name="datagridrowheader-states"></a>Stati DataGridRowHeader  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per l'elemento <xref:System.Windows.Controls.Primitives.DataGridRowHeader>.  
  
|Nome VisualState|Nome VisualStateGroup|description|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse viene posizionato sulla riga.|  
|MouseOver_CurrentRow|CommonStates|Il puntatore del mouse viene posizionato sulla riga e la riga è la riga corrente.|  
|MouseOver_CurrentRow_Selected|CommonStates|Il puntatore del mouse viene posizionato sulla riga e la riga è corrente e selezionata.|  
|MouseOver_EditingRow|CommonStates|Il puntatore del mouse viene posizionato sulla riga e la riga è in modalità di modifica.|  
|MouseOver_Selected|CommonStates|Il puntatore del mouse viene posizionato sulla riga e la riga è selezionata.|  
|MouseOver_Unfocused_CurrentRow_Selected|CommonStates|Il puntatore del mouse viene posizionato sulla riga, la riga è corrente e selezionata e non ha lo stato attivo.|  
|MouseOver_Unfocused_EditingRow|CommonStates|Il puntatore del mouse viene posizionato sulla riga, la riga è in modalità di modifica e non ha lo stato attivo.|  
|MouseOver_Unfocused_Selected|CommonStates|Il puntatore del mouse viene posizionato sulla riga, la riga è selezionata e non ha lo stato attivo.|  
|Normal_CurrentRow|CommonStates|La riga è la riga corrente.|  
|Normal_CurrentRow_Selected|CommonStates|La riga è la riga corrente ed è selezionata.|  
|Normal_EditingRow|CommonStates|La riga è in modalità di modifica.|  
|Normal_Selected|CommonStates|La riga è selezionata.|  
|Unfocused_CurrentRow_Selected|CommonStates|La riga è la riga corrente, è selezionata e non ha lo stato attivo.|  
|Unfocused_EditingRow|CommonStates|La riga è in modalità di modifica e non ha lo stato attivo.|  
|Unfocused_Selected|CommonStates|La riga è selezionata e non ha lo stato attivo.|  
|InvalidFocused|ValidationStates|Il controllo non è valido e ha uno stato attivo.|  
|InvalidUnfocused|ValidationStates|Il controllo non è valido e non ha uno stato attivo.|  
|Valido|ValidationStates|Il controllo è valido.|  
  
## <a name="datagridcolumnheaderspresenter-parts"></a>Parti DataGridColumnHeadersPresenter  
 Nella tabella seguente sono elencate le parti denominate per l'elemento <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>.  
  
|Parte|Digitare|description|  
|-|-|-|  
|PART_FillerColumnHeader|<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>|Segnaposto per le intestazioni di colonna.|  
  
## <a name="datagridcolumnheaderspresenter-states"></a>Stati DataGridColumnHeadersPresenter  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per l'elemento <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>.  
  
|Nome VisualState|Nome VisualStateGroup|description|  
|-|-|-|  
|InvalidFocused|ValidationStates|La cella non è valida e ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|La cella non è valida e non ha lo stato attivo.|  
|Valido|ValidationStates|La cella è valida.|  
  
## <a name="datagridcolumnheader-parts"></a>Parti DataGridColumnHeader  
 Nella tabella seguente sono elencate le parti denominate per l'elemento <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.  
  
|Parte|Digitare|description|  
|-|-|-|  
|PART_LeftHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Elemento utilizzato per ridimensionare l'intestazione di colonna da sinistra.|  
|PART_RightHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Elemento utilizzato per ridimensionare l'intestazione di colonna da destra.|  
  
## <a name="datagridcolumnheader-states"></a>Stati DataGridColumnHeader  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per l'elemento <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.  
  
|Nome VisualState|Nome VisualStateGroup|description|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sul controllo.|  
|Premuto|CommonStates|Il controllo è premuto.|  
|SortAscending|SortStates|La colonna viene ordinata in ordine crescente.|  
|SortDescending|SortStates|La colonna viene ordinata in ordine decrescente.|  
|Indifferenziati|SortStates|La colonna non è ordinata.|  
|InvalidFocused|ValidationStates|Il controllo non è valido e ha uno stato attivo.|  
|InvalidUnfocused|ValidationStates|Il controllo non è valido e non ha uno stato attivo.|  
|Valido|ValidationStates|Il controllo è valido.|  
  
## <a name="datagrid-controltemplate-example"></a>Esempio di ControlTemplate DataGrid  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.DataGrid> e i relativi tipi associati.  
  
 [!code-xaml[ControlTemplateExamples#DataGrid](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datagrid.xaml#datagrid)]  
  
 L'esempio precedente usa una o più delle seguenti risorse.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Stili e modelli di Control](control-styles-and-templates.md)
- [Personalizzazione dei controlli](control-customization.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md)
