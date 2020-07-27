---
title: 'Procedura: impostare il contenuto di testo di un controllo TextBox'
description: Informazioni su come usare la proprietà Text per impostare il contenuto di testo iniziale di un controllo TextBox Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: 41efb69e297b3c6fdb1203c358dcc72d7a9f806f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168049"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="ff3e1-103">Procedura: impostare il contenuto di testo di un controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="ff3e1-103">How to: Set the Text Content of a TextBox Control</span></span>

<span data-ttu-id="ff3e1-104">Questo esempio illustra come usare la <xref:System.Windows.Controls.TextBox.Text%2A> proprietà per impostare il contenuto di testo iniziale di un <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="ff3e1-104">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>

> [!NOTE]
> <span data-ttu-id="ff3e1-105">Sebbene la [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] versione dell'esempio possa usare i `<TextBox.Text>` tag intorno al testo del contenuto di ogni pulsante <xref:System.Windows.Controls.TextBox> , non è necessario perché <xref:System.Windows.Controls.TextBox> applica l' <xref:System.Windows.Markup.ContentPropertyAttribute> attributo alla <xref:System.Windows.Controls.TextBox.Text%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="ff3e1-105">Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="ff3e1-106">Per ulteriori informazioni, vedere [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span><span class="sxs-lookup"><span data-stu-id="ff3e1-106">For more information, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span></span>

## <a name="example"></a><span data-ttu-id="ff3e1-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="ff3e1-107">Example</span></span>

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a><span data-ttu-id="ff3e1-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="ff3e1-108">Example</span></span>

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a><span data-ttu-id="ff3e1-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff3e1-109">See also</span></span>

- [<span data-ttu-id="ff3e1-110">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="ff3e1-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="ff3e1-111">Cenni generali sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="ff3e1-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
