---
title: 'Procedura: creare un controllo TextBox su più righe'
description: Informazioni su come utilizzare XAML per definire un controllo TextBox che si espande in modo da includere più righe di testo in un'applicazione Windows Presentation Foundation.
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: 0a88d4d768884df135afddb491431650b9ba2d24
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166246"
---
# <a name="how-to-create-a-multiline-textbox-control"></a><span data-ttu-id="1c759-103">Procedura: creare un controllo TextBox su più righe</span><span class="sxs-lookup"><span data-stu-id="1c759-103">How to: Create a Multiline TextBox Control</span></span>
<span data-ttu-id="1c759-104">Questo esempio illustra come usare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per definire un <xref:System.Windows.Controls.TextBox> controllo che si espanderà automaticamente per contenere più righe di testo.</span><span class="sxs-lookup"><span data-stu-id="1c759-104">This example shows how to use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.TextBox> control that will automatically expand to accommodate multiple lines of text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c759-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c759-105">Example</span></span>  
 <span data-ttu-id="1c759-106">Se si imposta l' <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attributo su **Wrap** , il testo immesso verrà sottoposto a wrapping in una nuova riga quando viene raggiunto il bordo del <xref:System.Windows.Controls.TextBox> controllo, espandendo automaticamente il <xref:System.Windows.Controls.TextBox> controllo in modo da includere una nuova riga, se necessario.</span><span class="sxs-lookup"><span data-stu-id="1c759-106">Setting the <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attribute to **Wrap** will cause entered text to wrap to a new line when the edge of the <xref:System.Windows.Controls.TextBox> control is reached, automatically expanding the <xref:System.Windows.Controls.TextBox> control to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="1c759-107"><xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A>Se si imposta l'attributo su **true** , viene inserita una nuova riga quando viene premuto il tasto restituito, una volta che viene nuovamente espansa automaticamente <xref:System.Windows.Controls.TextBox> per includere la stanza per una nuova riga, se necessario.</span><span class="sxs-lookup"><span data-stu-id="1c759-107">Setting the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> attribute to **true** causes a new line to be inserted when the RETURN key is pressed, once again automatically expanding the <xref:System.Windows.Controls.TextBox> to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="1c759-108">L' <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attributo aggiunge una barra di scorrimento a <xref:System.Windows.Controls.TextBox> , in modo che sia possibile scorrere il contenuto di <xref:System.Windows.Controls.TextBox> se l'oggetto <xref:System.Windows.Controls.TextBox> si espande oltre le dimensioni del frame o della finestra che lo racchiude.</span><span class="sxs-lookup"><span data-stu-id="1c759-108">The <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attribute adds a scroll bar to the <xref:System.Windows.Controls.TextBox>, so that the contents of the <xref:System.Windows.Controls.TextBox> can be scrolled through if the <xref:System.Windows.Controls.TextBox> expands beyond the size of the frame or window that encloses it.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="1c759-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c759-109">See also</span></span>

- <xref:System.Windows.TextWrapping>
- [<span data-ttu-id="1c759-110">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="1c759-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="1c759-111">Cenni generali sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="1c759-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
