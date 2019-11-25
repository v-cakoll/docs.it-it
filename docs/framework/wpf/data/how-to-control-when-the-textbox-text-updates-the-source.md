---
title: 'Procedura: controllare il momento in cui il database di origine viene aggiornato dal testo di TextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
ms.openlocfilehash: b211eb67e3bac95f74255935a39cc0d6aec61531
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974792"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>Procedura: controllare il momento in cui il database di origine viene aggiornato dal testo di TextBox
Questo argomento descrive come usare la proprietà <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> per controllare la tempistica degli aggiornamenti dell'origine dell'associazione. Nell'argomento viene usato il controllo <xref:System.Windows.Controls.TextBox> come esempio.

## <a name="example"></a>Esempio
 Il valore <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> predefinito della proprietà <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> è <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>. Ciò significa che se un'applicazione dispone di un <xref:System.Windows.Controls.TextBox> con una proprietà <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> associata ai dati, il testo digitato nel <xref:System.Windows.Controls.TextBox> non aggiornerà l'origine finché il <xref:System.Windows.Controls.TextBox> non perderà lo stato attivo (ad esempio, quando si fa clic fuori dal <xref:System.Windows.Controls.TextBox>).

 Se si desidera che l'origine venga aggiornata durante la digitazione, impostare il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> dell'associazione su <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>. Nell'esempio seguente, le righe di codice evidenziate mostrano che le proprietà `Text` sia del <xref:System.Windows.Controls.TextBox> che del <xref:System.Windows.Controls.TextBlock> sono associate alla stessa proprietà Source. La proprietà <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> dell'associazione <xref:System.Windows.Controls.TextBox> è impostata su <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.

 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]

 Di conseguenza, il <xref:System.Windows.Controls.TextBlock> Mostra lo stesso testo (poiché l'origine cambia) quando l'utente immette il testo nella <xref:System.Windows.Controls.TextBox>, come illustrato nella schermata seguente dell'esempio:

 ![Screenshot che Mostra data binding semplici.](./media/how-to-control-when-the-textbox-text-updates-the-source/data-binding-simple-binding-sample.png)

 Se si dispone di una finestra di dialogo o di un modulo modificabile dall'utente e si desidera rinviare gli aggiornamenti delle origini fino a quando l'utente non ha terminato di modificare i campi e fa clic su "OK", è possibile impostare il valore <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> dei binding su <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, come nell'esempio seguente:

 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]

 Quando si imposta il valore di <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> su <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, il valore di origine viene modificato solo quando l'applicazione chiama il metodo di <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>. Nell'esempio seguente viene illustrato come chiamare <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> per `itemNameTextBox`:

 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]

> [!NOTE]
> È possibile usare la stessa tecnica per le proprietà di altri controlli, ma tenere presente che la maggior parte delle altre proprietà hanno un valore <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> predefinito di <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>. Per ulteriori informazioni, vedere la pagina delle proprietà <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.

> [!NOTE]
> La proprietà <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> gestisce gli aggiornamenti dell'origine e pertanto è pertinente solo per le associazioni <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource>. Per il funzionamento delle associazioni <xref:System.Windows.Data.BindingMode.TwoWay> e <xref:System.Windows.Data.BindingMode.OneWayToSource>, l'oggetto di origine deve fornire le notifiche di modifica delle proprietà. Per altre informazioni, è possibile fare riferimento agli esempi citati in questo argomento. È anche possibile esaminare [Implementare la notifica di modifiche alle proprietà](how-to-implement-property-change-notification.md).

## <a name="see-also"></a>Vedere anche

- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
