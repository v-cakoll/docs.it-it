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
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a>Procedura: impostare il contenuto di testo di un controllo TextBox

Questo esempio illustra come usare la proprietà <xref:System.Windows.Controls.TextBox.Text%2A> per impostare il contenuto di testo iniziale di un controllo <xref:System.Windows.Controls.TextBox>.

> [!NOTE]
> Sebbene la versione [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] dell'esempio possa usare i tag `<TextBox.Text>` intorno al testo del contenuto <xref:System.Windows.Controls.TextBox> di ciascun pulsante, non è necessario perché il <xref:System.Windows.Controls.TextBox> applica l'attributo <xref:System.Windows.Markup.ContentPropertyAttribute> alla proprietà <xref:System.Windows.Controls.TextBox.Text%2A>. Per ulteriori informazioni, vedere [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).

## <a name="example"></a>Esempio

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a>Esempio

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
- [Cenni preliminari sul controllo RichTextBox](richtextbox-overview.md)
