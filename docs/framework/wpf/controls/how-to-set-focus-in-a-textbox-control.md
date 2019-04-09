---
title: 'Procedura: Impostare lo stato attivo in un controllo TextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus [WPF], setting
- TextBox control [WPF], setting focus
ms.assetid: 24b61b45-dc2d-425e-9839-b017af7ab86f
ms.openlocfilehash: f4ba367ea9bdfcd6dbab7a5015472ec33adfe46f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115505"
---
# <a name="how-to-set-focus-in-a-textbox-control"></a><span data-ttu-id="d5e01-102">Procedura: Impostare lo stato attivo in un controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="d5e01-102">How to: Set Focus in a TextBox Control</span></span>
<span data-ttu-id="d5e01-103">Questo esempio illustra come usare il <xref:System.Windows.UIElement.Focus%2A> per impostare lo stato attivo su un <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="d5e01-103">This example shows how to use the <xref:System.Windows.UIElement.Focus%2A> method to set focus on a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5e01-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d5e01-104">Example</span></span>  
 <span data-ttu-id="d5e01-105">Quanto segue [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] esempio descrive una semplice <xref:System.Windows.Controls.TextBox> controllo denominato *tbFocusMe*</span><span class="sxs-lookup"><span data-stu-id="d5e01-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example describes a simple <xref:System.Windows.Controls.TextBox> control named *tbFocusMe*</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxFocusXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## <a name="example"></a><span data-ttu-id="d5e01-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="d5e01-106">Example</span></span>  
 <span data-ttu-id="d5e01-107">L'esempio seguente chiama il <xref:System.Windows.UIElement.Focus%2A> metodo impostare lo stato attivo per il <xref:System.Windows.Controls.TextBox> controllo con il nome *tbFocusMe*.</span><span class="sxs-lookup"><span data-stu-id="d5e01-107">The following example calls the <xref:System.Windows.UIElement.Focus%2A> method to set the focus on the <xref:System.Windows.Controls.TextBox> control with the Name *tbFocusMe*.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## <a name="see-also"></a><span data-ttu-id="d5e01-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5e01-108">See also</span></span>

- <xref:System.Windows.UIElement.Focusable%2A>
- <xref:System.Windows.UIElement.IsFocused%2A>
- [<span data-ttu-id="d5e01-109">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="d5e01-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="d5e01-110">Cenni generali sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="d5e01-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
