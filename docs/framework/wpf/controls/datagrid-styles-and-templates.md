---
title: Stili e modelli di DataGrid
description: Informazioni sugli stili e i modelli per il controllo DataGrid Windows Presentation Foundation. Modificare il ControlTemplate per dare al controllo un aspetto univoco.
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], DataGrid
- ControlTemplate [WPF], DataGrid
- DataGrid [WPF], styles and templates
- templates [WPF], DataGrid
- styles [WPF], DataGrid
- parts [WPF], DataGrid
ms.assetid: 9cb31d63-f148-4d25-b079-816e73f988c7
ms.openlocfilehash: dd526ec64d5077dad58f31c004f47e63c57ec9de
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168328"
---
# <a name="datagrid-styles-and-templates"></a>Stili e modelli di DataGrid
In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.DataGrid> controllo. È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco. Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="datagrid-parts"></a>Parti DataGrid  
 Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.DataGrid> controllo.  
  
|Parte|Type|Descrizione|  
|-|-|-|  
|PART_ColumnHeadersPresenter|<xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>|Riga che contiene le intestazioni di colonna.|  
  
 Quando si crea un oggetto <xref:System.Windows.Controls.ControlTemplate> per un oggetto <xref:System.Windows.Controls.DataGrid> , il modello potrebbe contenere un oggetto <xref:System.Windows.Controls.ItemsPresenter> all'interno di un oggetto <xref:System.Windows.Controls.ScrollViewer> . ( <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento in <xref:System.Windows.Controls.DataGrid> ; <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo).  Se <xref:System.Windows.Controls.ItemsPresenter> non è l'elemento figlio diretto di <xref:System.Windows.Controls.ScrollViewer> , è necessario assegnare al <xref:System.Windows.Controls.ItemsPresenter> nome `ItemsPresenter` .  
  
 Il modello predefinito per l'oggetto <xref:System.Windows.Controls.DataGrid> contiene un <xref:System.Windows.Controls.ScrollViewer> controllo. Per ulteriori informazioni sulle parti definite da <xref:System.Windows.Controls.ScrollViewer> , vedere [stili e modelli di ScrollViewer](scrollviewer-styles-and-templates.md).  
  
## <a name="datagrid-states"></a>Stati DataGrid  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.DataGrid> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|Disabled|CommonStates|Il controllo è disabilitato.|  
|InvalidFocused|ValidationStates|Il controllo non è valido e ha uno stato attivo.|  
|InvalidUnfocused|ValidationStates|Il controllo non è valido e non ha uno stato attivo.|  
|Valido|ValidationStates|Il controllo è valido.|  
  
## <a name="datagridcell-parts"></a>Parti DataGridCell  
 L' <xref:System.Windows.Controls.DataGridCell> elemento non dispone di parti denominate.  
  
## <a name="datagridcell-states"></a>Stati di DataGridCell  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per l' <xref:System.Windows.Controls.DataGridCell> elemento.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse viene posizionato sulla cella.|  
|Con stato attivo|FocusStates|La cella ha lo stato attivo.|  
|Con stato non attivo|FocusStates|La cella non ha lo stato attivo|  
|Corrente|CurrentStates|La cella è la cella corrente.|  
|Normale|CurrentStates|La cella non è la cella corrente.|  
|Schermo|InteractionStates|La cella è in modalità di visualizzazione.|  
|In fase di modifica|InteractionStates|La cella è in modalità di modifica.|  
|Selezionato|SelectionStates|La cella è selezionata.|  
|Deselezionato|SelectionStates|La cella non è selezionata.|  
|InvalidFocused|ValidationStates|La cella non è valida e ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|La cella non è valida e non ha lo stato attivo.|  
|Valido|ValidationStates|La cella è valida.|  
  
## <a name="datagridrow-parts"></a>Parti DataGridRow  
 L' <xref:System.Windows.Controls.DataGridRow> elemento non dispone di parti denominate.  
  
## <a name="datagridrow-states"></a>Stati di DataGridRow  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per l' <xref:System.Windows.Controls.DataGridRow> elemento.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
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
 Nella tabella seguente sono elencate le parti denominate per l' <xref:System.Windows.Controls.Primitives.DataGridRowHeader> elemento.  
  
|Parte|Type|Descrizione|  
|-|-|-|  
|PART_TopHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Elemento utilizzato per ridimensionare l'intestazione di riga dalla parte superiore.|  
|PART_BottomHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Elemento utilizzato per ridimensionare l'intestazione di riga dalla parte inferiore.|  
  
## <a name="datagridrowheader-states"></a>Stati DataGridRowHeader  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per l' <xref:System.Windows.Controls.Primitives.DataGridRowHeader> elemento.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
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
 Nella tabella seguente sono elencate le parti denominate per l' <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter> elemento.  
  
|Parte|Type|Descrizione|  
|-|-|-|  
|PART_FillerColumnHeader|<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>|Segnaposto per le intestazioni di colonna.|  
  
## <a name="datagridcolumnheaderspresenter-states"></a>Stati DataGridColumnHeadersPresenter  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per l' <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter> elemento.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|InvalidFocused|ValidationStates|La cella non è valida e ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|La cella non è valida e non ha lo stato attivo.|  
|Valido|ValidationStates|La cella è valida.|  
  
## <a name="datagridcolumnheader-parts"></a>Parti DataGridColumnHeader  
 Nella tabella seguente sono elencate le parti denominate per l' <xref:System.Windows.Controls.Primitives.DataGridColumnHeader> elemento.  
  
|Parte|Type|Descrizione|  
|-|-|-|  
|PART_LeftHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Elemento utilizzato per ridimensionare l'intestazione di colonna da sinistra.|  
|PART_RightHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Elemento utilizzato per ridimensionare l'intestazione di colonna da destra.|  
  
## <a name="datagridcolumnheader-states"></a>Stati DataGridColumnHeader  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per l' <xref:System.Windows.Controls.Primitives.DataGridColumnHeader> elemento.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
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
 Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.DataGrid> controllo e i tipi associati.  
  
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
