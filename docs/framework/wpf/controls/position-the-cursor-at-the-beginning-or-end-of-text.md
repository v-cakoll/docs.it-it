---
title: "Procedura: Posizionare il cursore all'inizio o alla fine del testo in un controllo TextBox"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
ms.openlocfilehash: 2b280c6ea74a4b7a896f33a3552997a730d24a39
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54497618"
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a><span data-ttu-id="4e46d-102">Procedura: Posizionare il cursore all'inizio o alla fine del testo in un controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="4e46d-102">How to: Position the Cursor at the Beginning or End of Text in a TextBox Control</span></span>
<span data-ttu-id="4e46d-103">Questo esempio illustra come posizionare il cursore all'inizio o alla fine del contenuto di testo di un <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="4e46d-103">This example shows how to position the cursor at the beginning or end of the text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e46d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4e46d-104">Example</span></span>  
 <span data-ttu-id="4e46d-105">Quanto segue [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] codice descrive un <xref:System.Windows.Controls.TextBox> controllano e assegna un nome.</span><span class="sxs-lookup"><span data-stu-id="4e46d-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a <xref:System.Windows.Controls.TextBox> control and assigns it a Name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a><span data-ttu-id="4e46d-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="4e46d-106">Example</span></span>  
 <span data-ttu-id="4e46d-107">Posizionare il cursore all'inizio del contenuto di un <xref:System.Windows.Controls.TextBox> controllo, chiamare il <xref:System.Windows.Controls.TextBox.Select%2A> (metodo) e specificare la posizione iniziale pari a 0 e una lunghezza pari a 0.</span><span class="sxs-lookup"><span data-stu-id="4e46d-107">To position the cursor at the beginning of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position of 0, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a><span data-ttu-id="4e46d-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="4e46d-108">Example</span></span>  
 <span data-ttu-id="4e46d-109">Posizionare il cursore alla fine del contenuto di un <xref:System.Windows.Controls.TextBox> controllo, chiamare il <xref:System.Windows.Controls.TextBox.Select%2A> (metodo) e specificare la posizione iniziale uguale alla lunghezza del contenuto di testo e una lunghezza pari a 0.</span><span class="sxs-lookup"><span data-stu-id="4e46d-109">To position the cursor at the end of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position equal to the  length of the text content, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a><span data-ttu-id="4e46d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e46d-110">See also</span></span>
- [<span data-ttu-id="4e46d-111">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="4e46d-111">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [<span data-ttu-id="4e46d-112">Cenni preliminari sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="4e46d-112">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
