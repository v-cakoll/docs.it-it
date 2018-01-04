---
title: 'Procedura: rilevare eventuali modifiche del testo in un oggetto TextBox'
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
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ef1da879026d8cbefd6ef1baeb6c315e0ea1c02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="d6d30-102">Procedura: rilevare eventuali modifiche del testo in un oggetto TextBox</span><span class="sxs-lookup"><span data-stu-id="d6d30-102">How to: Detect When Text in a TextBox Has Changed</span></span>
<span data-ttu-id="d6d30-103">In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> evento per eseguire un metodo ogni volta che il testo in un <xref:System.Windows.Controls.TextBox> controllo è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="d6d30-103">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>  
  
 <span data-ttu-id="d6d30-104">Nella classe code-behind per il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che contiene il <xref:System.Windows.Controls.TextBox> controllo che si desidera monitorare per le modifiche, inserire un metodo da chiamare quando il <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> viene generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="d6d30-104">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="d6d30-105">Questo metodo deve avere una firma che corrisponde a quella prevista dal <xref:System.Windows.Controls.TextChangedEventHandler> delegato.</span><span class="sxs-lookup"><span data-stu-id="d6d30-105">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 <span data-ttu-id="d6d30-106">Il gestore eventi viene chiamato ogni volta che il contenuto del <xref:System.Windows.Controls.TextBox> controllo vengono modificati, da un utente o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="d6d30-106">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="d6d30-107">**Nota:** questo evento viene generato quando il <xref:System.Windows.Controls.TextBox> controllo viene creato e compilato inizialmente con il testo.</span><span class="sxs-lookup"><span data-stu-id="d6d30-107">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6d30-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="d6d30-108">Example</span></span>  
 <span data-ttu-id="d6d30-109">Nel [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] che definisce il <xref:System.Windows.Controls.TextBox> di controllo, specificare il <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attributo con un valore che corrisponde al nome di metodo del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="d6d30-109">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextChangedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## <a name="example"></a><span data-ttu-id="d6d30-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="d6d30-110">Example</span></span>  
 <span data-ttu-id="d6d30-111">Nella classe code-behind per il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che contiene il <xref:System.Windows.Controls.TextBox> controllo che si desidera monitorare per le modifiche, inserire un metodo da chiamare quando il <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> viene generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="d6d30-111">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="d6d30-112">Questo metodo deve avere una firma che corrisponde a quella prevista dal <xref:System.Windows.Controls.TextChangedEventHandler> delegato.</span><span class="sxs-lookup"><span data-stu-id="d6d30-112">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 <span data-ttu-id="d6d30-113">Il gestore eventi viene chiamato ogni volta che il contenuto del <xref:System.Windows.Controls.TextBox> controllo vengono modificati, da un utente o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="d6d30-113">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="d6d30-114">**Nota:** questo evento viene generato quando il <xref:System.Windows.Controls.TextBox> controllo viene creato e compilato inizialmente con il testo.</span><span class="sxs-lookup"><span data-stu-id="d6d30-114">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
 <span data-ttu-id="d6d30-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="d6d30-115">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6d30-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6d30-116">See Also</span></span>  
 <xref:System.Windows.Controls.TextChangedEventArgs>  
 [<span data-ttu-id="d6d30-117">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="d6d30-117">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="d6d30-118">Cenni preliminari sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="d6d30-118">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
