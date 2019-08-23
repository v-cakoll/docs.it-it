---
title: 'Procedura: Controllare il momento in cui il database di origine viene aggiornato dal testo di TextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
ms.openlocfilehash: d1d624d7550a1135431b7fffc7450e3a510855a7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966457"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>Procedura: Controllare il momento in cui il database di origine viene aggiornato dal testo di TextBox
In questo argomento viene descritto come utilizzare <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> la proprietà per controllare l'intervallo degli aggiornamenti dell'origine dell'associazione. Nell'argomento viene usato <xref:System.Windows.Controls.TextBox> il controllo come esempio.  
  
## <a name="example"></a>Esempio  
 L'elemento language <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> il valore predefinito <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> della <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>proprietà è. Ciò significa che se un'applicazione dispone <xref:System.Windows.Controls.TextBox> di un oggetto con associazione <xref:System.Windows.Controls.TextBox>a dati.<xref:System.Windows.Controls.TextBox.Text%2A> il testo digitato in <xref:System.Windows.Controls.TextBox> non aggiorna l'origine <xref:System.Windows.Controls.TextBox> fino a quando non perde lo stato attivo, ad esempio quando <xref:System.Windows.Controls.TextBox>si fa clic all'interno di.  
  
 Se si desidera che l'origine venga aggiornata durante la digitazione, <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> impostare l'oggetto del <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>binding su. Nell'esempio seguente, le righe di codice evidenziate mostrano che le `Text` proprietà di <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.TextBlock> sono associate alla stessa proprietà Source. La <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>dell'associazione è impostata su. <xref:System.Windows.Controls.TextBox>  
  
 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]  
  
 Di conseguenza, <xref:System.Windows.Controls.TextBlock> Mostra lo stesso testo (poiché l'origine cambia) quando l'utente immette il testo <xref:System.Windows.Controls.TextBox>in, come illustrato nella schermata seguente dell'esempio:  
  
 ![Screenshot che Mostra data binding semplici.](./media/how-to-control-when-the-textbox-text-updates-the-source/data-binding-simple-binding-sample.png)  
  
 Se si dispone di una finestra di dialogo o di un modulo modificabile dall'utente e si desidera rinviare gli aggiornamenti delle origini fino a quando l'utente non ha terminato di modificare i <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> campi e fa clic su " <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>OK", è possibile impostare il valore dei binding su, come nell'esempio seguente:  
  
 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 Quando si imposta il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore su <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, il valore di origine viene modificato solo quando l'applicazione <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> chiama il metodo. Nell'esempio seguente viene illustrato come chiamare <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> per `itemNameTextBox`:  
  
 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
> È possibile usare la stessa tecnica per le proprietà di altri controlli, ma tenere presente che la maggior parte delle altre proprietà <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> hanno un <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>valore predefinito. Per ulteriori informazioni, vedere la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> pagina delle proprietà.  
  
> [!NOTE]
> La <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà gestisce gli aggiornamenti di origine e pertanto è pertinente <xref:System.Windows.Data.BindingMode.TwoWay> solo <xref:System.Windows.Data.BindingMode.OneWayToSource> per le associazioni o. Per <xref:System.Windows.Data.BindingMode.TwoWay> il <xref:System.Windows.Data.BindingMode.OneWayToSource> funzionamento delle associazioni e, l'oggetto di origine deve fornire le notifiche di modifica delle proprietà. Per altre informazioni, è possibile fare riferimento agli esempi citati in questo argomento. È anche possibile esaminare [Implementare la notifica di modifiche alle proprietà](how-to-implement-property-change-notification.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
