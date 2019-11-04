---
title: Stili e modelli di RadioButton
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], RadioButton
- RadioButton [WPF], styles and templates
- ControlTemplate [WPF], RadioButton
- states [WPF], RadioButton
- templates [WPF], RadioButton
- parts [WPF], RadioButton
ms.assetid: 9acf93f7-dd2f-4010-8ce0-1edd81c52ae2
ms.openlocfilehash: 892b4bead6ef6db3a6c007e34fb333ebf1e39850
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459857"
---
# <a name="radiobutton-styles-and-templates"></a>Stili e modelli di RadioButton
In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.RadioButton>. È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco. Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="radiobutton-parts"></a>Parti RadioButton  
 Il controllo <xref:System.Windows.Controls.RadioButton> non dispone di parti denominate.  
  
## <a name="radiobutton-states"></a>Stati di RadioButton  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.RadioButton>.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|----------------------|---------------------------|-----------------|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sul controllo.|  
|Premuto|CommonStates|Il controllo è premuto.|  
|Disabilitato|CommonStates|Il controllo è disabilitato.|  
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|  
|Selezionato con segno di spunta|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `true`.|  
|Deselezionata|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `false`.|  
|Indeterminato|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> è `true`e <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `null`.|  
|Valido|ValidationStates|Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.|  
  
## <a name="radiobutton-controltemplate-example"></a>Esempio di ControlTemplate RadioButton  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.RadioButton>.  
  
 [!code-xaml[ControlTemplateExamples#RadioButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/radiobutton.xaml#radiobutton)]  
  
 L'esempio precedente usa una o più delle seguenti risorse.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Stili e modelli di Control](control-styles-and-templates.md)
- [Personalizzazione dei controlli](control-customization.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
