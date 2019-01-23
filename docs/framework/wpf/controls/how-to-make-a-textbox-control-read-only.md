---
title: 'Procedura: Impostare la proprietà di sola lettura per un controllo TextBox'
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 1e9d333f22099d9593e58b4087f185b2988215ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517175"
---
# <a name="how-to-make-a-textbox-control-read-only"></a><span data-ttu-id="7163d-102">Procedura: Impostare la proprietà di sola lettura per un controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="7163d-102">How to: Make a TextBox Control Read-Only</span></span>
<span data-ttu-id="7163d-103">In questo esempio viene illustrato come configurare un <xref:System.Windows.Controls.TextBox> controllo per non consentire l'input dell'utente o la modifica.</span><span class="sxs-lookup"><span data-stu-id="7163d-103">This example shows how to configure a <xref:System.Windows.Controls.TextBox> control to not allow user input or modification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7163d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="7163d-104">Example</span></span>  
 <span data-ttu-id="7163d-105">Per impedire agli utenti di modificare il contenuto di un <xref:System.Windows.Controls.TextBox> , impostarne il <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> dell'attributo **true**.</span><span class="sxs-lookup"><span data-stu-id="7163d-105">To prevent users from modifying the contents of a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <span data-ttu-id="7163d-106">Il <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attributo interessa solo l'input dell'utente; non influenza testo impostato [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] descrizione di un <xref:System.Windows.Controls.TextBox> controllo o testo impostato a livello di codice tramite la <xref:System.Windows.Controls.TextBox.Text%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="7163d-106">The <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute affects user input only; it does not affect text set in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] description of a <xref:System.Windows.Controls.TextBox> control, or text set programmatically through the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="7163d-107">Il valore predefinito <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> viene **false**.</span><span class="sxs-lookup"><span data-stu-id="7163d-107">The default value of <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> is **false**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7163d-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7163d-108">See also</span></span>
- [<span data-ttu-id="7163d-109">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="7163d-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [<span data-ttu-id="7163d-110">Cenni preliminari sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="7163d-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
