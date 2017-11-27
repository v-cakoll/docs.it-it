---
title: 'Procedura: controllare il momento in cui il database di origine viene aggiornato dal testo di TextBox'
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
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c923a24f5abfdb059a436206a15181a67d03068f
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>Procedura: controllare il momento in cui il database di origine viene aggiornato dal testo di TextBox
In questo argomento viene descritto come utilizzare il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà per controllare l'intervallo degli aggiornamenti di origine di associazione. Nell'argomento viene utilizzato il <xref:System.Windows.Controls.TextBox> controllo come esempio.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> proprietà ha un valore predefinito <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>. Ciò significa che se un'applicazione dispone di un <xref:System.Windows.Controls.TextBox> con associazione a dati <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> , il testo digitato nella <xref:System.Windows.Controls.TextBox> non aggiorna l'origine finché il <xref:System.Windows.Controls.TextBox> perde lo stato attivo (ad esempio, quando fare clic all'esterno di <xref:System.Windows.Controls.TextBox>).  
  
 Se si desidera l'origine aggiornamento come si digita, impostare il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> dell'associazione <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>. Nell'esempio seguente, il `Text` le proprietà di entrambe le <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.TextBlock> sono associati alla stessa proprietà di origine. Il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà del <xref:System.Windows.Controls.TextBox> binding è impostato su <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.  
  
 [!code-xaml[SimpleBinding#USTHowTo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#usthowto)]  
  
 Di conseguenza, il <xref:System.Windows.Controls.TextBlock> Mostra lo stesso testo (perché l'origine viene modificata) quando l'utente immette testo nella <xref:System.Windows.Controls.TextBox>, come illustrato nella schermata dell'esempio seguente:  
  
 ![Schermata di esempio di data binding semplice](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")  
  
 Se si dispone di una finestra di dialogo o un form modificabili dall'utente e si desidera rinviare gli aggiornamenti dell'origine fino a quando l'utente al termine della modifica dei campi e fa clic su "OK", è possibile impostare il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore delle associazioni per <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, come nell'esempio seguente:  
  
 [!code-xaml[UpdateSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 Quando si imposta la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, il valore di origine cambia solo quando l'applicazione chiama il <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> metodo. Nell'esempio seguente viene illustrato come chiamare <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> per `itemNameTextBox`:  
  
 [!code-csharp[UpdateSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  È possibile utilizzare la stessa tecnica per le proprietà di altri controlli, ma tenere presente che la maggior parte delle altre proprietà hanno un valore predefinito <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>. Per ulteriori informazioni, vedere il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> pagina delle proprietà.  
  
> [!NOTE]
>  Il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà relativa agli aggiornamenti dell'origine e pertanto è importante solo per <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource> associazioni. Per <xref:System.Windows.Data.BindingMode.TwoWay> e <xref:System.Windows.Data.BindingMode.OneWayToSource> associazioni a funzionare, è necessario che l'oggetto di origine per fornire le notifiche di modifica delle proprietà. Per altre informazioni, è possibile fare riferimento agli esempi citati in questo argomento. È anche possibile esaminare [Implementare la notifica di modifiche alle proprietà](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Procedure relative](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
