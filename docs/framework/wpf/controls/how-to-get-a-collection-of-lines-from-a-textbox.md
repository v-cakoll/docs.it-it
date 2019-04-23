---
title: 'Procedura: Ottenere una raccolta di righe da un controllo TextBox'
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: b7b2f1c2e071388635fb50b1e3573fd7f44334dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224637"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a><span data-ttu-id="d4e2a-102">Procedura: Ottenere una raccolta di righe da un controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="d4e2a-102">How to: Get a Collection of Lines from a TextBox</span></span>
<span data-ttu-id="d4e2a-103">In questo esempio viene illustrato come ottenere una raccolta di righe di testo da un <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d4e2a-103">This example shows how to get a collection of lines of text from a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4e2a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d4e2a-104">Example</span></span>  
 <span data-ttu-id="d4e2a-105">Nell'esempio seguente illustra un semplice metodo che accetta un <xref:System.Windows.Controls.TextBox> come argomento e restituisce un <xref:System.Collections.Specialized.StringCollection> contenente le righe di testo nel **nella casella di testo**.</span><span class="sxs-lookup"><span data-stu-id="d4e2a-105">The following example shows a simple method that takes a <xref:System.Windows.Controls.TextBox> as the argument, and returns a <xref:System.Collections.Specialized.StringCollection> containing the lines of text in the **TextBox**.</span></span>  <span data-ttu-id="d4e2a-106">Il <xref:System.Windows.Controls.TextBox.LineCount%2A> proprietà viene utilizzata per determinare il numero di righe è attualmente nel **nella casella di testo**e il <xref:System.Windows.Controls.TextBox.GetLineText%2A> metodo viene quindi utilizzato per estrarre ogni riga e aggiungerlo alla raccolta di righe.</span><span class="sxs-lookup"><span data-stu-id="d4e2a-106">The <xref:System.Windows.Controls.TextBox.LineCount%2A> property is used to determine how many lines are currently in the **TextBox**, and the <xref:System.Windows.Controls.TextBox.GetLineText%2A> method is then used to extract each line and add it to the collection of lines.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a><span data-ttu-id="d4e2a-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4e2a-107">See also</span></span>

- [<span data-ttu-id="d4e2a-108">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="d4e2a-108">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="d4e2a-109">Cenni preliminari sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="d4e2a-109">RichTextBox Overview</span></span>](richtextbox-overview.md)
