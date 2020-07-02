---
title: 'Procedura: controllare il momento in cui il database di origine viene aggiornato dal testo di TextBox'
description: Controllare la tempistica degli aggiornamenti dell'origine di binding usando la proprietà UpdateSourceTrigger in Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
ms.openlocfilehash: 8f6eb5beb0d14a951f6e6cf6eb81e130f5a3e194
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622783"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>Procedura: controllare il momento in cui il database di origine viene aggiornato dal testo di TextBox
In questo argomento viene descritto come utilizzare la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà per controllare l'intervallo degli aggiornamenti dell'origine dell'associazione. Nell'argomento viene usato il <xref:System.Windows.Controls.TextBox> controllo come esempio.

## <a name="example"></a>Esempio
 Il <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> valore predefinito della proprietà è <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> . Ciò significa che se un'applicazione dispone di un oggetto <xref:System.Windows.Controls.TextBox> con una proprietà associata a dati <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> , il testo digitato nell'oggetto non <xref:System.Windows.Controls.TextBox> Aggiorna l'origine fino a <xref:System.Windows.Controls.TextBox> quando non perde lo stato attivo, ad esempio quando si fa clic fuori da <xref:System.Windows.Controls.TextBox> .

 Se si desidera che l'origine venga aggiornata durante la digitazione, impostare l'oggetto <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> del binding su <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> . Nell'esempio seguente, le righe di codice evidenziate mostrano che le `Text` proprietà di <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.TextBlock> sono associate alla stessa proprietà Source. La <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà dell' <xref:System.Windows.Controls.TextBox> associazione è impostata su <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> .

 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]

 Di conseguenza, <xref:System.Windows.Controls.TextBlock> Mostra lo stesso testo (poiché l'origine cambia) quando l'utente immette il testo in <xref:System.Windows.Controls.TextBox> , come illustrato nella schermata seguente dell'esempio:

 ![Screenshot che Mostra data binding semplici.](./media/how-to-control-when-the-textbox-text-updates-the-source/data-binding-simple-binding-sample.png)

 Se si dispone di una finestra di dialogo o di un modulo modificabile dall'utente e si desidera rinviare gli aggiornamenti delle origini fino a quando l'utente non ha terminato di modificare i campi e fa clic su "OK", è possibile impostare il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore dei binding su <xref:System.Windows.Data.UpdateSourceTrigger.Explicit> , come nell'esempio seguente:

 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]

 Quando si imposta il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore su <xref:System.Windows.Data.UpdateSourceTrigger.Explicit> , il valore di origine viene modificato solo quando l'applicazione chiama il <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> metodo. Nell'esempio seguente viene illustrato come chiamare <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> per `itemNameTextBox` :

 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]

> [!NOTE]
> È possibile usare la stessa tecnica per le proprietà di altri controlli, ma tenere presente che la maggior parte delle altre proprietà hanno un <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore predefinito <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> . Per ulteriori informazioni, vedere la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> pagina delle proprietà.

> [!NOTE]
> La <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà gestisce gli aggiornamenti di origine e pertanto è pertinente solo per le <xref:System.Windows.Data.BindingMode.TwoWay> <xref:System.Windows.Data.BindingMode.OneWayToSource> associazioni o. Per <xref:System.Windows.Data.BindingMode.TwoWay> <xref:System.Windows.Data.BindingMode.OneWayToSource> il funzionamento delle associazioni e, l'oggetto di origine deve fornire le notifiche di modifica delle proprietà. Per altre informazioni, è possibile fare riferimento agli esempi citati in questo argomento. È anche possibile esaminare [Implementare la notifica di modifiche alle proprietà](how-to-implement-property-change-notification.md).

## <a name="see-also"></a>Vedere anche

- [Procedure](data-binding-how-to-topics.md)
