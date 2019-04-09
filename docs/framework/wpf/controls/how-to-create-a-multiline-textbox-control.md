---
title: 'Procedura: Creare un controllo TextBox a più righe'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: 29fb4c9498fe163c36e71680242d3ef8cf98c089
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181168"
---
# <a name="how-to-create-a-multiline-textbox-control"></a><span data-ttu-id="92abb-102">Procedura: Creare un controllo TextBox a più righe</span><span class="sxs-lookup"><span data-stu-id="92abb-102">How to: Create a Multiline TextBox Control</span></span>
<span data-ttu-id="92abb-103">In questo esempio viene illustrato come utilizzare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per definire un <xref:System.Windows.Controls.TextBox> controllo che si espanderà automaticamente per inserire più righe di testo.</span><span class="sxs-lookup"><span data-stu-id="92abb-103">This example shows how to use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.TextBox> control that will automatically expand to accommodate multiple lines of text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92abb-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="92abb-104">Example</span></span>  
 <span data-ttu-id="92abb-105">Impostando il <xref:System.Windows.Controls.TextBox.TextWrapping%2A> dell'attributo **eseguire il wrapping** causerà il testo immesso eseguire il wrapping in una nuova riga quando il bordo del <xref:System.Windows.Controls.TextBox> controllo viene raggiunto, si espande automaticamente il <xref:System.Windows.Controls.TextBox> controllo per includere una nuova riga, se necessario.</span><span class="sxs-lookup"><span data-stu-id="92abb-105">Setting the <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attribute to **Wrap** will cause entered text to wrap to a new line when the edge of the <xref:System.Windows.Controls.TextBox> control is reached, automatically expanding the <xref:System.Windows.Controls.TextBox> control to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="92abb-106">Impostando il <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> dell'attributo **true** fa sì che una nuova riga deve essere inserito quando viene premuto il tasto INVIO, espande automaticamente il <xref:System.Windows.Controls.TextBox> per inserire una nuova riga, se necessario.</span><span class="sxs-lookup"><span data-stu-id="92abb-106">Setting the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> attribute to **true** causes a new line to be inserted when the RETURN key is pressed, once again automatically expanding the <xref:System.Windows.Controls.TextBox> to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="92abb-107">Il <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attributo aggiunge una barra di scorrimento per il <xref:System.Windows.Controls.TextBox>, in modo che il contenuto del <xref:System.Windows.Controls.TextBox> se è possibile scorrere il <xref:System.Windows.Controls.TextBox> espande oltre la dimensione della cornice o finestra che lo racchiude.</span><span class="sxs-lookup"><span data-stu-id="92abb-107">The <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attribute adds a scroll bar to the <xref:System.Windows.Controls.TextBox>, so that the contents of the <xref:System.Windows.Controls.TextBox> can be scrolled through if the <xref:System.Windows.Controls.TextBox> expands beyond the size of the frame or window that encloses it.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="92abb-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92abb-108">See also</span></span>

- <xref:System.Windows.TextWrapping>
- [<span data-ttu-id="92abb-109">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="92abb-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="92abb-110">Cenni generali sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="92abb-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
