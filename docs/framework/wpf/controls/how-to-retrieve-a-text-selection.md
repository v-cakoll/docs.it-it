---
title: 'Procedura: recuperare un testo selezionato'
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
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 32be79811de4b8056449c2c6d6c53eca8cc063f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-retrieve-a-text-selection"></a><span data-ttu-id="8f095-102">Procedura: recuperare un testo selezionato</span><span class="sxs-lookup"><span data-stu-id="8f095-102">How to: Retrieve a Text Selection</span></span>
<span data-ttu-id="8f095-103">In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Controls.TextBox.SelectedText%2A> proprietà per recuperare il testo che l'utente ha selezionato in un <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="8f095-103">This example shows one way to use the <xref:System.Windows.Controls.TextBox.SelectedText%2A> property to retrieve text that the user has selected in a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f095-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8f095-104">Example</span></span>  
 <span data-ttu-id="8f095-105">Le operazioni seguenti [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] riportato di seguito viene illustrata la definizione di un <xref:System.Windows.Controls.TextBox> controllo che contiene del testo da selezionare, e un <xref:System.Windows.Controls.Button> controllo con un oggetto specificato <xref:System.Windows.Controls.Button.OnClick%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="8f095-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example shows the definition of a <xref:System.Windows.Controls.TextBox> control that contains some text to select, and a <xref:System.Windows.Controls.Button> control with a specified <xref:System.Windows.Controls.Button.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="8f095-106">In questo esempio, un pulsante con un oggetto associato <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi viene utilizzato per recuperare il testo selezionato.</span><span class="sxs-lookup"><span data-stu-id="8f095-106">In this example, a button with an associated <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler is used to retrieve the text selection.</span></span> <span data-ttu-id="8f095-107">Quando l'utente fa clic sul pulsante, il <xref:System.Windows.Controls.Button.OnClick%2A> metodo copia testo selezionato nella casella di testo in una stringa.</span><span class="sxs-lookup"><span data-stu-id="8f095-107">When the user clicks the button, the <xref:System.Windows.Controls.Button.OnClick%2A> method copies any selected text in the textbox into a string.</span></span> <span data-ttu-id="8f095-108">Particolari circostanze per cui la selezione di testo viene recuperata (facendo clic su un pulsante), nonché l'azione eseguita su tale selezione (copia la selezione di testo in una stringa), possono essere facilmente modificati per supportare un'ampia gamma di scenari.</span><span class="sxs-lookup"><span data-stu-id="8f095-108">The particular circumstances by which the text selection is retrieved (clicking a button), as well as the action taken with that selection (copying the text selection to a string), can easily be modified to accommodate a wide variety of scenarios.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a><span data-ttu-id="8f095-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="8f095-109">Example</span></span>  
 <span data-ttu-id="8f095-110">Le operazioni seguenti [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] esempio viene illustrato un <xref:System.Windows.Controls.Button.OnClick%2A> gestore eventi per il pulsante definito nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="8f095-110">The following [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] example shows an <xref:System.Windows.Controls.Button.OnClick%2A> event handler for the button defined in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for this example.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a><span data-ttu-id="8f095-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f095-111">See Also</span></span>  
 [<span data-ttu-id="8f095-112">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="8f095-112">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="8f095-113">Cenni preliminari sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="8f095-113">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
