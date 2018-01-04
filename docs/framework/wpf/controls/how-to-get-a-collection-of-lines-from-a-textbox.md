---
title: 'Procedura: ottenere una raccolta di righe da un controllo TextBox'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 12d32266bb901f6ce47d19d92d6f0785277aa7c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a><span data-ttu-id="cbfac-102">Procedura: ottenere una raccolta di righe da un controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="cbfac-102">How to: Get a Collection of Lines from a TextBox</span></span>
<span data-ttu-id="cbfac-103">In questo esempio viene illustrato come ottenere una raccolta di righe di testo da un <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="cbfac-103">This example shows how to get a collection of lines of text from a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbfac-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="cbfac-104">Example</span></span>  
 <span data-ttu-id="cbfac-105">Nell'esempio seguente viene illustrato un semplice metodo che accetta un <xref:System.Windows.Controls.TextBox> come argomento e restituisce un <xref:System.Collections.Specialized.StringCollection> contenente le righe di testo di **TextBox**.</span><span class="sxs-lookup"><span data-stu-id="cbfac-105">The following example shows a simple method that takes a <xref:System.Windows.Controls.TextBox> as the argument, and returns a <xref:System.Collections.Specialized.StringCollection> containing the lines of text in the **TextBox**.</span></span>  <span data-ttu-id="cbfac-106">Il <xref:System.Windows.Controls.TextBox.LineCount%2A> proprietà viene utilizzata per determinare il numero di righe incluse nel **TextBox**e <xref:System.Windows.Controls.TextBox.GetLineText%2A> metodo viene quindi utilizzato per estrarre ciascuna riga e aggiungerlo alla raccolta di righe.</span><span class="sxs-lookup"><span data-stu-id="cbfac-106">The <xref:System.Windows.Controls.TextBox.LineCount%2A> property is used to determine how many lines are currently in the **TextBox**, and the <xref:System.Windows.Controls.TextBox.GetLineText%2A> method is then used to extract each line and add it to the collection of lines.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a><span data-ttu-id="cbfac-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbfac-107">See Also</span></span>  
 [<span data-ttu-id="cbfac-108">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="cbfac-108">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="cbfac-109">Cenni preliminari sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="cbfac-109">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
