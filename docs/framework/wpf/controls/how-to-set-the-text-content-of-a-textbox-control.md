---
title: 'Procedura: Impostare il contenuto di testo di un controllo TextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: 2e2bc70b108991fd4e3c138bfac5bff942173e33
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856107"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a>Procedura: Impostare il contenuto di testo di un controllo TextBox

Questo esempio illustra come usare la <xref:System.Windows.Controls.TextBox.Text%2A> proprietà per impostare il contenuto di testo iniziale di un <xref:System.Windows.Controls.TextBox> controllo.

> [!NOTE]
> Sebbene la [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] versione dell'esempio possa usare i `<TextBox.Text>` Tag intorno al <xref:System.Windows.Controls.TextBox> testo del <xref:System.Windows.Controls.TextBox> contenuto di ogni pulsante, non è <xref:System.Windows.Controls.TextBox.Text%2A> necessario perché applica l' <xref:System.Windows.Markup.ContentPropertyAttribute> attributo alla proprietà . Per ulteriori informazioni, vedere [Cenni preliminari su XAML (WPF)](../advanced/xaml-overview-wpf.md).

## <a name="example"></a>Esempio

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a>Esempio

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
- [Cenni preliminari sul controllo RichTextBox](richtextbox-overview.md)
