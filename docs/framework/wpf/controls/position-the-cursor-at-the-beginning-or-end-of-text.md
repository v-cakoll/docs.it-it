---
title: "Procedura: posizionare il cursore all'inizio o alla fine del testo in un controllo TextBox"
description: Informazioni su come posizionare il cursore all'inizio o alla fine del contenuto di testo di un controllo TextBox Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
ms.openlocfilehash: afe8b11d032b5d61fa91cbf324f02cd8415d2ea8
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167508"
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a><span data-ttu-id="8ddbf-103">Procedura: posizionare il cursore all'inizio o alla fine del testo in un controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="8ddbf-103">How to: Position the Cursor at the Beginning or End of Text in a TextBox Control</span></span>
<span data-ttu-id="8ddbf-104">In questo esempio viene illustrato come posizionare il cursore all'inizio o alla fine del contenuto di testo di un <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="8ddbf-104">This example shows how to position the cursor at the beginning or end of the text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ddbf-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ddbf-105">Example</span></span>  
 <span data-ttu-id="8ddbf-106">Nel [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] codice seguente viene descritto un <xref:System.Windows.Controls.TextBox> controllo a cui viene assegnato un nome.</span><span class="sxs-lookup"><span data-stu-id="8ddbf-106">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a <xref:System.Windows.Controls.TextBox> control and assigns it a Name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a><span data-ttu-id="8ddbf-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ddbf-107">Example</span></span>  
 <span data-ttu-id="8ddbf-108">Per posizionare il cursore all'inizio del contenuto di un <xref:System.Windows.Controls.TextBox> controllo, chiamare il <xref:System.Windows.Controls.TextBox.Select%2A> metodo e specificare la posizione iniziale della selezione 0 e una lunghezza di selezione pari a 0.</span><span class="sxs-lookup"><span data-stu-id="8ddbf-108">To position the cursor at the beginning of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position of 0, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a><span data-ttu-id="8ddbf-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ddbf-109">Example</span></span>  
 <span data-ttu-id="8ddbf-110">Per posizionare il cursore alla fine del contenuto di un <xref:System.Windows.Controls.TextBox> controllo, chiamare il <xref:System.Windows.Controls.TextBox.Select%2A> metodo e specificare la posizione iniziale della selezione uguale alla lunghezza del contenuto di testo e una lunghezza di selezione pari a 0.</span><span class="sxs-lookup"><span data-stu-id="8ddbf-110">To position the cursor at the end of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position equal to the  length of the text content, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a><span data-ttu-id="8ddbf-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ddbf-111">See also</span></span>

- [<span data-ttu-id="8ddbf-112">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="8ddbf-112">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="8ddbf-113">Cenni generali sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="8ddbf-113">RichTextBox Overview</span></span>](richtextbox-overview.md)
