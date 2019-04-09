---
title: 'Procedura: Impostare la proprietà di sola lettura per un controllo TextBox'
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 7f24458eb98bd669d59f15c49d1d9e3beb6833b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229836"
---
# <a name="how-to-make-a-textbox-control-read-only"></a>Procedura: Impostare la proprietà di sola lettura per un controllo TextBox
In questo esempio viene illustrato come configurare un <xref:System.Windows.Controls.TextBox> controllo per non consentire l'input dell'utente o la modifica.  
  
## <a name="example"></a>Esempio  
 Per impedire agli utenti di modificare il contenuto di un <xref:System.Windows.Controls.TextBox> , impostarne il <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> dell'attributo **true**.  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 Il <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attributo interessa solo l'input dell'utente; non influenza testo impostato [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] descrizione di un <xref:System.Windows.Controls.TextBox> controllo o testo impostato a livello di codice tramite la <xref:System.Windows.Controls.TextBox.Text%2A> proprietà.  
  
 Il valore predefinito <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> viene **false**.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
- [Cenni generali sul controllo RichTextBox](richtextbox-overview.md)
