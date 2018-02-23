---
title: 'Procedura: controllare il momento in cui il database di origine viene aggiornato dal testo di TextBox'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 00fc64938e6a063ffbda77961f967e08c169ebd7
ms.sourcegitcommit: 973a12d1e6962cd9a9c263fbfaad040ec8267fe9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/22/2018
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a><span data-ttu-id="db3bf-102">Procedura: controllare il momento in cui il database di origine viene aggiornato dal testo di TextBox</span><span class="sxs-lookup"><span data-stu-id="db3bf-102">How to: Control When the TextBox Text Updates the Source</span></span>
<span data-ttu-id="db3bf-103">In questo argomento viene descritto come utilizzare il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà per controllare l'intervallo degli aggiornamenti di origine di associazione.</span><span class="sxs-lookup"><span data-stu-id="db3bf-103">This topic describes how to use the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property to control the timing of binding source updates.</span></span> <span data-ttu-id="db3bf-104">Nell'argomento viene utilizzato il <xref:System.Windows.Controls.TextBox> controllo come esempio.</span><span class="sxs-lookup"><span data-stu-id="db3bf-104">The topic uses the <xref:System.Windows.Controls.TextBox> control as an example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db3bf-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="db3bf-105">Example</span></span>  
 <span data-ttu-id="db3bf-106">Il <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> proprietà ha un valore predefinito <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.</span><span class="sxs-lookup"><span data-stu-id="db3bf-106">The <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> property has a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.</span></span> <span data-ttu-id="db3bf-107">Ciò significa che se un'applicazione dispone di un <xref:System.Windows.Controls.TextBox> con associazione a dati <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> , il testo digitato nella <xref:System.Windows.Controls.TextBox> non aggiorna l'origine finché il <xref:System.Windows.Controls.TextBox> perde lo stato attivo (ad esempio, quando fare clic all'esterno di <xref:System.Windows.Controls.TextBox>).</span><span class="sxs-lookup"><span data-stu-id="db3bf-107">This means if an application has a <xref:System.Windows.Controls.TextBox> with a data-bound <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> property, the text you type into the <xref:System.Windows.Controls.TextBox> does not update the source until the <xref:System.Windows.Controls.TextBox> loses focus (for instance, when you click away from the <xref:System.Windows.Controls.TextBox>).</span></span>  
  
 <span data-ttu-id="db3bf-108">Se si desidera l'origine da aggiornare durante la digitazione, impostare il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> dell'associazione <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="db3bf-108">If you want the source to be updated as you type, set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> of the binding to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="db3bf-109">Nell'esempio seguente, le righe di codice evidenziate mostrano che il `Text` le proprietà di entrambe il <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.TextBlock> sono associati alla stessa proprietà di origine.</span><span class="sxs-lookup"><span data-stu-id="db3bf-109">In the following example, the highlighted lines of code show that the `Text` properties of both the <xref:System.Windows.Controls.TextBox> and the <xref:System.Windows.Controls.TextBlock> are bound to the same source property.</span></span> <span data-ttu-id="db3bf-110">Il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà del <xref:System.Windows.Controls.TextBox> binding è impostato su <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="db3bf-110">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property of the <xref:System.Windows.Controls.TextBox> binding is set to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span>  
  
 [!code-xaml[SimpleBinding#USTHowTo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]  
  
 <span data-ttu-id="db3bf-111">Di conseguenza, il <xref:System.Windows.Controls.TextBlock> Mostra lo stesso testo (perché l'origine viene modificata) quando l'utente immette testo nella <xref:System.Windows.Controls.TextBox>, come illustrato nella schermata dell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="db3bf-111">As a result, the <xref:System.Windows.Controls.TextBlock> shows the same text (because the source changes) as the user enters text into the <xref:System.Windows.Controls.TextBox>, as illustrated by the following screenshot of the sample:</span></span>  
  
 <span data-ttu-id="db3bf-112">![Schermata di esempio di data binding semplice](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")</span><span class="sxs-lookup"><span data-stu-id="db3bf-112">![Simple data binding sample screen shot](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")</span></span>  
  
 <span data-ttu-id="db3bf-113">Se si dispone di una finestra di dialogo o un form modificabili dall'utente e si desidera rinviare gli aggiornamenti dell'origine fino a quando l'utente al termine della modifica dei campi e fa clic su "OK", è possibile impostare il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore delle associazioni per <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="db3bf-113">If you have a dialog or a user-editable form and you want to defer source updates until the user is finished editing the fields and clicks "OK", you can set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of your bindings to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, as in the following example:</span></span>  
  
 [!code-xaml[UpdateSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="db3bf-114">Quando si imposta la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, il valore di origine cambia solo quando l'applicazione chiama il <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="db3bf-114">When you set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, the source value only changes when the application calls the <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> method.</span></span> <span data-ttu-id="db3bf-115">Nell'esempio seguente viene illustrato come chiamare <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> per `itemNameTextBox`:</span><span class="sxs-lookup"><span data-stu-id="db3bf-115">The following example shows how to call <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> for `itemNameTextBox`:</span></span>  
  
 [!code-csharp[UpdateSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  <span data-ttu-id="db3bf-116">È possibile utilizzare la stessa tecnica per le proprietà di altri controlli, ma tenere presente che la maggior parte delle altre proprietà hanno un valore predefinito <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="db3bf-116">You can use the same technique for properties of other controls, but keep in mind that most other properties have a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="db3bf-117">Per ulteriori informazioni, vedere il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="db3bf-117">For more information, see the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db3bf-118">Il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà relativa agli aggiornamenti dell'origine e pertanto è importante solo per <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource> associazioni.</span><span class="sxs-lookup"><span data-stu-id="db3bf-118">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property deals with source updates and therefore is only relevant for <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings.</span></span> <span data-ttu-id="db3bf-119">Per <xref:System.Windows.Data.BindingMode.TwoWay> e <xref:System.Windows.Data.BindingMode.OneWayToSource> associazioni a funzionare, è necessario che l'oggetto di origine per fornire le notifiche di modifica delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="db3bf-119">For <xref:System.Windows.Data.BindingMode.TwoWay> and <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings to work, the source object needs to provide property change notifications.</span></span> <span data-ttu-id="db3bf-120">Per altre informazioni, è possibile fare riferimento agli esempi citati in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="db3bf-120">You can refer to the samples cited in this topic for more information.</span></span> <span data-ttu-id="db3bf-121">È anche possibile esaminare [Implementare la notifica di modifiche alle proprietà](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span><span class="sxs-lookup"><span data-stu-id="db3bf-121">In addition, you can look at [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db3bf-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db3bf-122">See Also</span></span>  
 [<span data-ttu-id="db3bf-123">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="db3bf-123">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
