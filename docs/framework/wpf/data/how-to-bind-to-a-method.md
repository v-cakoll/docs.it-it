---
title: "Procedura: eseguire l'associazione a un metodo"
description: Seguire questo esempio per scoprire come eseguire l'associazione al metodo di un oggetto nel Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
ms.openlocfilehash: 9501e6357203c21651e85f1d65059be1d70becf2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619598"
---
# <a name="how-to-bind-to-a-method"></a>Procedura: eseguire l'associazione a un metodo
Nell'esempio seguente viene illustrato come eseguire l'associazione a un metodo utilizzando <xref:System.Windows.Data.ObjectDataProvider> .  
  
## <a name="example"></a>Esempio  
 In questo esempio `TemperatureScale` è una classe che dispone di un metodo `ConvertTemp` che accetta due parametri, uno di tipo `double` e uno di tipo `enum``TempType)` e converte il valore specificato da una scala della temperatura a altro. Nell'esempio seguente <xref:System.Windows.Data.ObjectDataProvider> viene usato un oggetto per creare un'istanza dell' `TemperatureScale` oggetto. Il metodo `ConvertTemp` viene chiamato con due parametri specificati.  
  
 [!code-xaml[BindToMethod#WindowResources](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 Ora che il metodo è disponibile come una risorsa, è possibile associare i risultati. Nell'esempio seguente, la <xref:System.Windows.Controls.TextBox.Text%2A> proprietà di <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> di <xref:System.Windows.Controls.ComboBox> sono associate ai due parametri del metodo. Ciò consente agli utenti di specificare la temperatura da convertire e la scala della temperatura da cui eseguire la conversione. Si noti che <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> è impostato su perché viene eseguito `true` il binding alla <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> proprietà dell' <xref:System.Windows.Data.ObjectDataProvider> istanza e non alle proprietà dell'oggetto di cui è stato eseguito il wrapper <xref:System.Windows.Data.ObjectDataProvider> ( `TemperatureScale` oggetto).  
  
 <xref:System.Windows.Controls.ContentControl.Content%2A>Dell'ultimo <xref:System.Windows.Controls.Label> aggiornamento quando l'utente modifica il contenuto di <xref:System.Windows.Controls.TextBox> o la selezione di <xref:System.Windows.Controls.ComboBox> .  
  
 [!code-xaml[BindToMethod#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 Il convertitore `DoubleToString` accetta un valore Double e lo trasforma in una stringa nella <xref:System.Windows.Data.IValueConverter.Convert%2A> direzione (dall'origine dell'associazione alla destinazione di associazione, che è la <xref:System.Windows.Controls.TextBox.Text%2A> proprietà) e converte un oggetto `string` in un oggetto `double` nella <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> direzione.  
  
 `InvalidationCharacterRule`È un oggetto <xref:System.Windows.Controls.ValidationRule> che verifica la presenza di caratteri non validi. Il modello di errore predefinito, ovvero un bordo rosso intorno all'oggetto <xref:System.Windows.Controls.TextBox> , viene visualizzato per notificare agli utenti quando il valore di input non è un valore Double.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](data-binding-how-to-topics.md)
- [Eseguire l'associazione a un'enumerazione](how-to-bind-to-an-enumeration.md)
