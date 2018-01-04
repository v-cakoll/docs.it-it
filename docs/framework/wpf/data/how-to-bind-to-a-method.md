---
title: 'Procedura: eseguire l''associazione a un metodo'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 45f2a141b09c52085c13803b8d338fdc9eebf135
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-a-method"></a><span data-ttu-id="71015-102">Procedura: eseguire l'associazione a un metodo</span><span class="sxs-lookup"><span data-stu-id="71015-102">How to: Bind to a Method</span></span>
<span data-ttu-id="71015-103">Nell'esempio seguente viene illustrato come associare a un metodo utilizzando <xref:System.Windows.Data.ObjectDataProvider>.</span><span class="sxs-lookup"><span data-stu-id="71015-103">The following example shows how to bind to a method using <xref:System.Windows.Data.ObjectDataProvider>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71015-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="71015-104">Example</span></span>  
 <span data-ttu-id="71015-105">In questo esempio `TemperatureScale` è una classe che dispone di un metodo `ConvertTemp` che accetta due parametri, uno di tipo `double` e uno di tipo `enum` `TempType)` e converte il valore specificato da una scala della temperatura a altro.</span><span class="sxs-lookup"><span data-stu-id="71015-105">In this example, `TemperatureScale` is a class that has a method `ConvertTemp`, which takes two parameters (one of `double` and one of the `enum` type `TempType)` and converts the given value from one temperature scale to another.</span></span> <span data-ttu-id="71015-106">Nell'esempio seguente, un <xref:System.Windows.Data.ObjectDataProvider> viene utilizzato per creare un'istanza di `TemperatureScale` oggetto.</span><span class="sxs-lookup"><span data-stu-id="71015-106">In the following example, an <xref:System.Windows.Data.ObjectDataProvider> is used to instantiate the `TemperatureScale` object.</span></span> <span data-ttu-id="71015-107">Il metodo `ConvertTemp` viene chiamato con due parametri specificati.</span><span class="sxs-lookup"><span data-stu-id="71015-107">The `ConvertTemp` method is called with two specified parameters.</span></span>  
  
 [!code-xaml[BindToMethod#WindowResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 <span data-ttu-id="71015-108">Ora che il metodo è disponibile come una risorsa, è possibile associare i risultati.</span><span class="sxs-lookup"><span data-stu-id="71015-108">Now that the method is available as a resource, you can bind to its results.</span></span> <span data-ttu-id="71015-109">Nell'esempio seguente, il <xref:System.Windows.Controls.TextBox.Text%2A> proprietà del <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> del <xref:System.Windows.Controls.ComboBox> sono associati a due parametri del metodo.</span><span class="sxs-lookup"><span data-stu-id="71015-109">In the following example, the <xref:System.Windows.Controls.TextBox.Text%2A> property of the <xref:System.Windows.Controls.TextBox> and the <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> of the <xref:System.Windows.Controls.ComboBox> are bound to the two parameters of the method.</span></span> <span data-ttu-id="71015-110">Ciò consente agli utenti di specificare la temperatura da convertire e la scala della temperatura da cui eseguire la conversione.</span><span class="sxs-lookup"><span data-stu-id="71015-110">This allows users to specify the temperature to convert and the temperature scale to convert from.</span></span> <span data-ttu-id="71015-111">Si noti che <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> è impostato su `true` perché viene eseguita l'associazione per il <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> proprietà del <xref:System.Windows.Data.ObjectDataProvider> istanza e non le proprietà dell'oggetto sottoposto a wrapping dal <xref:System.Windows.Data.ObjectDataProvider> (il `TemperatureScale` oggetto).</span><span class="sxs-lookup"><span data-stu-id="71015-111">Note that <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> is set to `true` because we are binding to the <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> property of the <xref:System.Windows.Data.ObjectDataProvider> instance and not properties of the object wrapped by the <xref:System.Windows.Data.ObjectDataProvider> (the `TemperatureScale` object).</span></span>  
  
 <span data-ttu-id="71015-112">Il <xref:System.Windows.Controls.ContentControl.Content%2A> dell'ultimo <xref:System.Windows.Controls.Label> aggiornato quando l'utente modifica il contenuto del <xref:System.Windows.Controls.TextBox> o la selezione del <xref:System.Windows.Controls.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="71015-112">The <xref:System.Windows.Controls.ContentControl.Content%2A> of the last <xref:System.Windows.Controls.Label> updates when the user modifies the content of the <xref:System.Windows.Controls.TextBox> or the selection of the <xref:System.Windows.Controls.ComboBox>.</span></span>  
  
 [!code-xaml[BindToMethod#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 <span data-ttu-id="71015-113">Il convertitore `DoubleToString` accetta un valore double e lo trasforma in una stringa nel <xref:System.Windows.Data.IValueConverter.Convert%2A> direzione (dall'origine dell'associazione alla destinazione dell'associazione, ovvero il <xref:System.Windows.Controls.TextBox.Text%2A> proprietà) e converte un `string` per un `double` nel <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> direzione.</span><span class="sxs-lookup"><span data-stu-id="71015-113">The converter `DoubleToString` takes a double and turns it into a string in the <xref:System.Windows.Data.IValueConverter.Convert%2A> direction (from the binding source to binding target, which is the <xref:System.Windows.Controls.TextBox.Text%2A> property) and converts a `string` to a `double` in the <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> direction.</span></span>  
  
 <span data-ttu-id="71015-114">Il `InvalidationCharacterRule` è un <xref:System.Windows.Controls.ValidationRule> che verifica la presenza di caratteri non validi.</span><span class="sxs-lookup"><span data-stu-id="71015-114">The `InvalidationCharacterRule` is a <xref:System.Windows.Controls.ValidationRule> that checks for invalid characters.</span></span> <span data-ttu-id="71015-115">Il modello di errore predefinito, ovvero un bordo rosso intorno il <xref:System.Windows.Controls.TextBox>, viene visualizzata per notificare agli utenti quando il valore di input non è un valore double.</span><span class="sxs-lookup"><span data-stu-id="71015-115">The default error template, which is a red border around the <xref:System.Windows.Controls.TextBox>, appears to notify users when the input value is not a double value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71015-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71015-116">See Also</span></span>  
 [<span data-ttu-id="71015-117">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="71015-117">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [<span data-ttu-id="71015-118">Eseguire l'associazione a un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="71015-118">Bind to an Enumeration</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-an-enumeration.md)
