---
title: 'Procedura: impostare la proprietà di sola lettura per un controllo TextBox'
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 3ba93cae5977f3c8c76f3bfa9f5732d3f0736af7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554541"
---
# <a name="how-to-make-a-textbox-control-read-only"></a><span data-ttu-id="b19b7-102">Procedura: impostare la proprietà di sola lettura per un controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="b19b7-102">How to: Make a TextBox Control Read-Only</span></span>
<span data-ttu-id="b19b7-103">In questo esempio viene illustrato come configurare un <xref:System.Windows.Controls.TextBox> controllo per non consentire l'input dell'utente o la modifica.</span><span class="sxs-lookup"><span data-stu-id="b19b7-103">This example shows how to configure a <xref:System.Windows.Controls.TextBox> control to not allow user input or modification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b19b7-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b19b7-104">Example</span></span>  
 <span data-ttu-id="b19b7-105">Per impedire agli utenti di modificare il contenuto di un <xref:System.Windows.Controls.TextBox> di controllo, impostare il <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attributo **true**.</span><span class="sxs-lookup"><span data-stu-id="b19b7-105">To prevent users from modifying the contents of a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <span data-ttu-id="b19b7-106">Il <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attributo interessa solo l'input dell'utente, non influisce sul testo di cui il [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] descrizione di un <xref:System.Windows.Controls.TextBox> controllo o testo impostate a livello di programmazione tramite le <xref:System.Windows.Controls.TextBox.Text%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b19b7-106">The <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute affects user input only; it does not affect text set in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] description of a <xref:System.Windows.Controls.TextBox> control, or text set programmatically through the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="b19b7-107">Il valore predefinito di <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> è **false**.</span><span class="sxs-lookup"><span data-stu-id="b19b7-107">The default value of <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> is **false**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b19b7-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b19b7-108">See Also</span></span>  
 [<span data-ttu-id="b19b7-109">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="b19b7-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="b19b7-110">Cenni preliminari sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="b19b7-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
