---
title: 'Procedura: Impostare la proprietà di sola lettura per un controllo TextBox'
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 3784471020210f995c8bb0a377d56a2466d97da1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364537"
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
- [Cenni preliminari sul controllo RichTextBox](richtextbox-overview.md)
