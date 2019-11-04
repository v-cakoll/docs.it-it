---
title: 'Procedura: impostare il contenuto di testo di un controllo TextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: 9b16f2d99295a28725255361b0be3ef7f4245fd2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459309"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="4f78e-102">Procedura: impostare il contenuto di testo di un controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="4f78e-102">How to: Set the Text Content of a TextBox Control</span></span>

<span data-ttu-id="4f78e-103">Questo esempio illustra come usare la proprietà <xref:System.Windows.Controls.TextBox.Text%2A> per impostare il contenuto di testo iniziale di un controllo <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4f78e-103">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>

> [!NOTE]
> <span data-ttu-id="4f78e-104">Sebbene la versione [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] dell'esempio possa usare i tag `<TextBox.Text>` intorno al testo del contenuto <xref:System.Windows.Controls.TextBox> di ciascun pulsante, non è necessario perché il <xref:System.Windows.Controls.TextBox> applica l'attributo <xref:System.Windows.Markup.ContentPropertyAttribute> alla proprietà <xref:System.Windows.Controls.TextBox.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f78e-104">Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="4f78e-105">Per ulteriori informazioni, vedere [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span><span class="sxs-lookup"><span data-stu-id="4f78e-105">For more information, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span></span>

## <a name="example"></a><span data-ttu-id="4f78e-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f78e-106">Example</span></span>

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a><span data-ttu-id="4f78e-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f78e-107">Example</span></span>

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a><span data-ttu-id="4f78e-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f78e-108">See also</span></span>

- [<span data-ttu-id="4f78e-109">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="4f78e-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="4f78e-110">Cenni preliminari sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="4f78e-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
