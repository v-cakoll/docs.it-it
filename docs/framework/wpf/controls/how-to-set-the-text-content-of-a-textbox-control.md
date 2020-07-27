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
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a>Procedura: impostare il contenuto di testo di un controllo TextBox

Questo esempio illustra come usare la <xref:System.Windows.Controls.TextBox.Text%2A> proprietà per impostare il contenuto di testo iniziale di un <xref:System.Windows.Controls.TextBox> controllo.

> [!NOTE]
> Sebbene la [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] versione dell'esempio possa usare i `<TextBox.Text>` tag intorno al testo del contenuto di ogni pulsante <xref:System.Windows.Controls.TextBox> , non è necessario perché <xref:System.Windows.Controls.TextBox> applica l' <xref:System.Windows.Markup.ContentPropertyAttribute> attributo alla <xref:System.Windows.Controls.TextBox.Text%2A> Proprietà. Per ulteriori informazioni, vedere [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).

## <a name="example"></a>Esempio

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a>Esempio

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
- [Cenni generali sul controllo RichTextBox](richtextbox-overview.md)
