---
title: 'Procedura: Rilevare eventuali modifiche del testo in un oggetto TextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 8c7744e9e61b8ba796802e54435c0bf9fdbee50e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855616"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="6b684-102">Procedura: Rilevare eventuali modifiche del testo in un oggetto TextBox</span><span class="sxs-lookup"><span data-stu-id="6b684-102">How to: Detect When Text in a TextBox Has Changed</span></span>

<span data-ttu-id="6b684-103">Questo esempio illustra un modo per usare l' <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> evento per eseguire un metodo ogni volta che il testo <xref:System.Windows.Controls.TextBox> in un controllo viene modificato.</span><span class="sxs-lookup"><span data-stu-id="6b684-103">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>

<span data-ttu-id="6b684-104">Nella classe code-behind per l'oggetto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che contiene il <xref:System.Windows.Controls.TextBox> controllo di cui si desidera monitorare le modifiche, inserire un metodo da chiamare ogni volta <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> che l'evento viene generato.</span><span class="sxs-lookup"><span data-stu-id="6b684-104">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="6b684-105">Questo metodo deve avere una firma che corrisponda a quanto previsto dal <xref:System.Windows.Controls.TextChangedEventHandler> delegato.</span><span class="sxs-lookup"><span data-stu-id="6b684-105">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>

<span data-ttu-id="6b684-106">Il gestore eventi viene chiamato ogni volta che il contenuto <xref:System.Windows.Controls.TextBox> del controllo viene modificato da un utente o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="6b684-106">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>

> [!NOTE]
> <span data-ttu-id="6b684-107">Questo evento viene generato quando <xref:System.Windows.Controls.TextBox> il controllo viene creato e popolato inizialmente con il testo.</span><span class="sxs-lookup"><span data-stu-id="6b684-107">This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>

## <a name="example"></a><span data-ttu-id="6b684-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="6b684-108">Example</span></span>

<span data-ttu-id="6b684-109">Nell'oggetto [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] che definisce il <xref:System.Windows.Controls.TextBox> controllo, specificare l' <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attributo con un valore che corrisponda al nome del metodo del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="6b684-109">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>

[!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]

## <a name="example"></a><span data-ttu-id="6b684-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="6b684-110">Example</span></span>

<span data-ttu-id="6b684-111">Nella classe code-behind per l'oggetto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che contiene il <xref:System.Windows.Controls.TextBox> controllo di cui si desidera monitorare le modifiche, inserire un metodo da chiamare ogni volta <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> che l'evento viene generato.</span><span class="sxs-lookup"><span data-stu-id="6b684-111">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="6b684-112">Questo metodo deve avere una firma che corrisponda a quanto previsto dal <xref:System.Windows.Controls.TextChangedEventHandler> delegato.</span><span class="sxs-lookup"><span data-stu-id="6b684-112">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>

[!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
[!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]

<span data-ttu-id="6b684-113">Il gestore eventi viene chiamato ogni volta che il contenuto <xref:System.Windows.Controls.TextBox> del controllo viene modificato da un utente o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="6b684-113">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>

> [!NOTE]
> <span data-ttu-id="6b684-114">Questo evento viene generato quando <xref:System.Windows.Controls.TextBox> il controllo viene creato e popolato inizialmente con il testo.</span><span class="sxs-lookup"><span data-stu-id="6b684-114">This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>

<span data-ttu-id="6b684-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="6b684-115">Comments</span></span>

## <a name="see-also"></a><span data-ttu-id="6b684-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b684-116">See also</span></span>

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [<span data-ttu-id="6b684-117">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="6b684-117">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="6b684-118">Cenni preliminari sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="6b684-118">RichTextBox Overview</span></span>](richtextbox-overview.md)
