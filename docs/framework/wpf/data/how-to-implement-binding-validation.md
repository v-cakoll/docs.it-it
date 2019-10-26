---
title: "Procedura: implementare la convalida dell'associazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: 7a1a8df78a785066992472c7de37f958ae3467f1
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920160"
---
# <a name="how-to-implement-binding-validation"></a><span data-ttu-id="3f6ca-102">Procedura: implementare la convalida dell'associazione</span><span class="sxs-lookup"><span data-stu-id="3f6ca-102">How to: Implement Binding Validation</span></span>

<span data-ttu-id="3f6ca-103">Questo esempio illustra come usare un <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> e un trigger di stile per fornire commenti visivi per informare l'utente quando viene immesso un valore non valido, in base a una regola di convalida personalizzata.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-103">This example shows how to use an <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> and a style trigger to provide visual feedback to inform the user when an invalid value is entered, based on a custom validation rule.</span></span>

## <a name="example"></a><span data-ttu-id="3f6ca-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="3f6ca-104">Example</span></span>

<span data-ttu-id="3f6ca-105">Il contenuto di testo della <xref:System.Windows.Controls.TextBox> nell'esempio seguente è associato alla proprietà `Age` (di tipo int) di un oggetto di origine di associazione denominato `ods`.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-105">The text content of the <xref:System.Windows.Controls.TextBox> in the following example is bound to the `Age` property (of type int) of a binding source object named `ods`.</span></span> <span data-ttu-id="3f6ca-106">Il binding è configurato per l'uso di una regola di convalida denominata `AgeRangeRule` in modo che, se l'utente immette un carattere non numerico o un valore minore di 21 o maggiore di 130, appare un punto esclamativo rosso accanto alla casella di testo e viene visualizzata una descrizione comando con il messaggio di errore quando l'utente sposta il puntatore del mouse sulla casella di testo.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-106">The binding is set up to use a validation rule named `AgeRangeRule` so that if the user enters non-numeric characters or a value that is smaller than 21 or greater than 130, a red exclamation mark appears next to the text box and a tool tip with the error message appears when the user moves the mouse over the text box.</span></span>

[!code-xaml[BindValidation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]

<span data-ttu-id="3f6ca-107">Nell'esempio seguente viene illustrata l'implementazione di `AgeRangeRule`, che eredita da <xref:System.Windows.Controls.ValidationRule> ed esegue l'override del metodo <xref:System.Windows.Controls.ValidationRule.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-107">The following example shows the implementation of `AgeRangeRule`, which inherits from <xref:System.Windows.Controls.ValidationRule> and overrides the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method.</span></span> <span data-ttu-id="3f6ca-108">Il metodo `Int32.Parse` viene chiamato sul valore per assicurarsi che non contenga caratteri non validi.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-108">The `Int32.Parse` method is called on the value to make sure that it does not contain any invalid characters.</span></span> <span data-ttu-id="3f6ca-109">Il metodo <xref:System.Windows.Controls.ValidationRule.Validate%2A> restituisce un <xref:System.Windows.Controls.ValidationResult> che indica se il valore è valido in base al fatto che un'eccezione venga intercettata durante l'analisi e se il valore Age non sia compreso tra i limiti inferiore e superiore.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-109">The <xref:System.Windows.Controls.ValidationRule.Validate%2A> method returns a <xref:System.Windows.Controls.ValidationResult> that indicates if the value is valid based on whether an exception is caught during the parsing and whether the age value is outside of the lower and upper bounds.</span></span>

[!code-csharp[BindValidation#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]
[!code-vb[BindValidation#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindValidation/VisualBasic/AgeRangeRule.vb#3)]

<span data-ttu-id="3f6ca-110">Nell'esempio seguente viene illustrata la `validationTemplate` di <xref:System.Windows.Controls.ControlTemplate> personalizzata che crea un punto esclamativo rosso per notificare all'utente un errore di convalida.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-110">The following example shows the custom <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` that creates a red exclamation mark to notify the user of a validation error.</span></span> <span data-ttu-id="3f6ca-111">Vengono usati modelli specifici per ridefinire l'aspetto di un controllo.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-111">Control templates are used to redefine the appearance of a control.</span></span>

[!code-xaml[BindValidation#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]

<span data-ttu-id="3f6ca-112">Come illustrato nell'esempio seguente, il <xref:System.Windows.Controls.ToolTip> che mostra il messaggio di errore viene creato usando lo stile denominato `textBoxInError`.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-112">As shown in the following example, the <xref:System.Windows.Controls.ToolTip> that shows the error message is created using the style named `textBoxInError`.</span></span> <span data-ttu-id="3f6ca-113">Se il valore di <xref:System.Windows.Controls.Validation.HasError%2A> è `true`, il trigger imposta la descrizione comando del <xref:System.Windows.Controls.TextBox> corrente sul primo errore di convalida.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-113">If the value of <xref:System.Windows.Controls.Validation.HasError%2A> is `true`, the trigger sets the tool tip of the current <xref:System.Windows.Controls.TextBox> to its first validation error.</span></span> <span data-ttu-id="3f6ca-114">Il <xref:System.Windows.Data.Binding.RelativeSource%2A> è impostato su <xref:System.Windows.Data.RelativeSourceMode.Self>, che fa riferimento all'elemento corrente.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-114">The <xref:System.Windows.Data.Binding.RelativeSource%2A> is set to <xref:System.Windows.Data.RelativeSourceMode.Self>, referring to the current element.</span></span>

[!code-xaml[BindValidation#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]

<span data-ttu-id="3f6ca-115">Per l'esempio completo, vedere [esempio di convalida di binding](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span><span class="sxs-lookup"><span data-stu-id="3f6ca-115">For the complete example, see [Bind Validation sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span></span>
  
<span data-ttu-id="3f6ca-116">Si noti che se non si specifica un <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> personalizzato, viene visualizzato il modello di errore predefinito per fornire un feedback visivo all'utente quando si verifica un errore di convalida.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-116">Note that if you do not provide a custom <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> the default error template appears to provide visual feedback to the user when there is a validation error.</span></span> <span data-ttu-id="3f6ca-117">Per altre informazioni, vedere "Convalida dei dati" in [Panoramica sul data binding](data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3f6ca-117">See "Data Validation" in [Data Binding Overview](data-binding-overview.md) for more information.</span></span> <span data-ttu-id="3f6ca-118">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce anche una regola di convalida integrata che controlla le eccezioni generate durante l'aggiornamento della proprietà di origine del binding.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-118">Also, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] provides a built-in validation rule that catches exceptions that are thrown during the update of the binding source property.</span></span> <span data-ttu-id="3f6ca-119">Per ulteriori informazioni, vedere <xref:System.Windows.Controls.ExceptionValidationRule>.</span><span class="sxs-lookup"><span data-stu-id="3f6ca-119">For more information, see <xref:System.Windows.Controls.ExceptionValidationRule>.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f6ca-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f6ca-120">See also</span></span>

- [<span data-ttu-id="3f6ca-121">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="3f6ca-121">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="3f6ca-122">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="3f6ca-122">How-to Topics</span></span>](data-binding-how-to-topics.md)
