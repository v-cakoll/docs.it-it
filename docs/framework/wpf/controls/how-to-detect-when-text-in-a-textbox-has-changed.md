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
ms.openlocfilehash: 72441e53d21df47d34a0600dafdf0b4b04c11cad
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352373"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="633d0-102">Procedura: Rilevare eventuali modifiche del testo in un oggetto TextBox</span><span class="sxs-lookup"><span data-stu-id="633d0-102">How to: Detect When Text in a TextBox Has Changed</span></span>
<span data-ttu-id="633d0-103">In questo esempio illustra un modo per usare la <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> eventi di eseguire un metodo ogni volta che il testo in un <xref:System.Windows.Controls.TextBox> controllo è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="633d0-103">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>  
  
 <span data-ttu-id="633d0-104">Nella classe code-behind per il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che contiene il <xref:System.Windows.Controls.TextBox> controllo che si desidera monitorare le modifiche, inserire un metodo da chiamare ogni volta che il <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> viene generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="633d0-104">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="633d0-105">Questo metodo deve avere una firma che corrisponde a quello previsto dal <xref:System.Windows.Controls.TextChangedEventHandler> delegare.</span><span class="sxs-lookup"><span data-stu-id="633d0-105">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 <span data-ttu-id="633d0-106">Il gestore eventi viene chiamato ogni volta che il contenuto del <xref:System.Windows.Controls.TextBox> controllo vengono modificate, da un utente o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="633d0-106">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="633d0-107">**Nota:** Questo evento viene generato quando il <xref:System.Windows.Controls.TextBox> controllo viene creato e popolato inizialmente con il testo.</span><span class="sxs-lookup"><span data-stu-id="633d0-107">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="633d0-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="633d0-108">Example</span></span>  
 <span data-ttu-id="633d0-109">Nel [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] che definisce i <xref:System.Windows.Controls.TextBox> controllare, specificare il <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attributo con un valore che corrisponde al nome di metodo del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="633d0-109">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## <a name="example"></a><span data-ttu-id="633d0-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="633d0-110">Example</span></span>  
 <span data-ttu-id="633d0-111">Nella classe code-behind per il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che contiene il <xref:System.Windows.Controls.TextBox> controllo che si desidera monitorare le modifiche, inserire un metodo da chiamare ogni volta che il <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> viene generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="633d0-111">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="633d0-112">Questo metodo deve avere una firma che corrisponde a quello previsto dal <xref:System.Windows.Controls.TextChangedEventHandler> delegare.</span><span class="sxs-lookup"><span data-stu-id="633d0-112">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 <span data-ttu-id="633d0-113">Il gestore eventi viene chiamato ogni volta che il contenuto del <xref:System.Windows.Controls.TextBox> controllo vengono modificate, da un utente o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="633d0-113">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="633d0-114">**Nota:** Questo evento viene generato quando il <xref:System.Windows.Controls.TextBox> controllo viene creato e popolato inizialmente con il testo.</span><span class="sxs-lookup"><span data-stu-id="633d0-114">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
 <span data-ttu-id="633d0-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="633d0-115">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="633d0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="633d0-116">See also</span></span>
- <xref:System.Windows.Controls.TextChangedEventArgs>
- [<span data-ttu-id="633d0-117">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="633d0-117">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="633d0-118">Cenni preliminari sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="633d0-118">RichTextBox Overview</span></span>](richtextbox-overview.md)
