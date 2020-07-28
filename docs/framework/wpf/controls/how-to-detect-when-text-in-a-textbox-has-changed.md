---
title: 'Procedura: rilevare eventuali modifiche del testo in un oggetto TextBox'
description: Informazioni su come usare l'evento TextChanged per eseguire un metodo ogni volta che il testo in un controllo TextBox cambia in un'applicazione Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 1e054380a8c77d32e6bb4adbbcb032e531bbefd0
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166220"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a>Procedura: rilevare eventuali modifiche del testo in un oggetto TextBox

Questo esempio illustra un modo per usare l' <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> evento per eseguire un metodo ogni volta che il testo in un <xref:System.Windows.Controls.TextBox> controllo viene modificato.

Nella classe code-behind per l'oggetto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che contiene il <xref:System.Windows.Controls.TextBox> controllo di cui si desidera monitorare le modifiche, inserire un metodo da chiamare ogni volta che l' <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> evento viene generato.  Questo metodo deve avere una firma che corrisponda a quanto previsto dal <xref:System.Windows.Controls.TextChangedEventHandler> delegato.

Il gestore eventi viene chiamato ogni volta che il contenuto del <xref:System.Windows.Controls.TextBox> controllo viene modificato da un utente o a livello di codice.

> [!NOTE]
> Questo evento viene generato quando il <xref:System.Windows.Controls.TextBox> controllo viene creato e popolato inizialmente con il testo.

## <a name="example"></a>Esempio

Nell'oggetto [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] che definisce il <xref:System.Windows.Controls.TextBox> controllo, specificare l' <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attributo con un valore che corrisponda al nome del metodo del gestore eventi.

[!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]

## <a name="example"></a>Esempio

Nella classe code-behind per l'oggetto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che contiene il <xref:System.Windows.Controls.TextBox> controllo di cui si desidera monitorare le modifiche, inserire un metodo da chiamare ogni volta che l' <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> evento viene generato.  Questo metodo deve avere una firma che corrisponda a quanto previsto dal <xref:System.Windows.Controls.TextChangedEventHandler> delegato.

[!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
[!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]

Il gestore eventi viene chiamato ogni volta che il contenuto del <xref:System.Windows.Controls.TextBox> controllo viene modificato da un utente o a livello di codice.

> [!NOTE]
> Questo evento viene generato quando il <xref:System.Windows.Controls.TextBox> controllo viene creato e popolato inizialmente con il testo.

Commenti

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
- [Cenni generali sul controllo RichTextBox](richtextbox-overview.md)
