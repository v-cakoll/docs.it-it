---
title: 'Procedura: Eseguire il binding a un metodo'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
ms.openlocfilehash: 6cdad46fd6d9ef3bc4ce1a13fedb6ff1d639d93e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967843"
---
# <a name="how-to-bind-to-a-method"></a>Procedura: Eseguire il binding a un metodo
Nell'esempio seguente viene illustrato come associare a un metodo usando <xref:System.Windows.Data.ObjectDataProvider>.  
  
## <a name="example"></a>Esempio  
 In questo esempio `TemperatureScale` è una classe che dispone di un metodo `ConvertTemp` che accetta due parametri, uno di tipo `double` e uno di tipo `enum` `TempType)` e converte il valore specificato da una scala della temperatura a altro. Nell'esempio seguente, un' <xref:System.Windows.Data.ObjectDataProvider> consente di creare un'istanza di `TemperatureScale` oggetto. Il metodo `ConvertTemp` viene chiamato con due parametri specificati.  
  
 [!code-xaml[BindToMethod#WindowResources](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 Ora che il metodo è disponibile come una risorsa, è possibile associare i risultati. Nell'esempio seguente, il <xref:System.Windows.Controls.TextBox.Text%2A> proprietà del <xref:System.Windows.Controls.TextBox> e il <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> del <xref:System.Windows.Controls.ComboBox> sono associati ai due parametri del metodo. Ciò consente agli utenti di specificare la temperatura da convertire e la scala della temperatura da cui eseguire la conversione. Si noti che <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> è impostata su `true` perché viene eseguita l'associazione per il <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> proprietà del <xref:System.Windows.Data.ObjectDataProvider> istanza e non alle proprietà dell'oggetto sottoposto a wrapping dal <xref:System.Windows.Data.ObjectDataProvider> (il `TemperatureScale` oggetto).  
  
 Il <xref:System.Windows.Controls.ContentControl.Content%2A> dell'ultima <xref:System.Windows.Controls.Label> Aggiorna quando l'utente modifica il contenuto delle <xref:System.Windows.Controls.TextBox> o la selezione del <xref:System.Windows.Controls.ComboBox>.  
  
 [!code-xaml[BindToMethod#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 Il convertitore `DoubleToString` accetta un valore double e lo trasforma in una stringa nel <xref:System.Windows.Data.IValueConverter.Convert%2A> direzione (dall'origine dell'associazione alla destinazione dell'associazione, ovvero il <xref:System.Windows.Controls.TextBox.Text%2A> proprietà) e converte un `string` a un `double` nel <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> direzione.  
  
 Il `InvalidationCharacterRule` è un <xref:System.Windows.Controls.ValidationRule> che verifica la presenza di caratteri non validi. Il modello di errore predefinito, ovvero un bordo rosso intorno di <xref:System.Windows.Controls.TextBox>, viene visualizzato per notificare agli utenti quando il valore di input non è un valore double.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
- [Eseguire l'associazione a un'enumerazione](how-to-bind-to-an-enumeration.md)
