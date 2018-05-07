---
title: 'Procedura: modificare le opzioni tipografiche del testo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting Typography attributes [WPF]
- Typography attribute [WPF], setting
ms.assetid: 19a3b49b-60a2-4c11-a786-e26b4c965588
ms.openlocfilehash: fcc9c894970934bb5a69debef2f4e38297f82198
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-alter-the-typography-of-text"></a>Procedura: modificare le opzioni tipografiche del testo
Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.Documents.TextElement.Typography%2A> attributo, mediante <xref:System.Windows.Documents.Paragraph> come elemento di esempio.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 La figura seguente illustra il rendering di questo esempio.  
  
 ![Screenshot: testo con proprietà tipografiche modificate](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement_Typog")  
  
 La figura seguente mostra invece il rendering dello stesso esempio con le proprietà tipografiche predefinite.  
  
 ![Screenshot: testo con le opzioni tipografiche predefinite](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement_Typog_Default")  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.Controls.TextBox.Typography%2A> proprietà a livello di codice.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sui documenti dinamici](../../../../docs/framework/wpf/advanced/flow-document-overview.md)
