---
title: 'Procedura: rilevare il momento in cui è stato premuto il tasto INVIO'
description: Rilevare quando il tasto invio è selezionato sulla tastiera in Windows Presentation Foundation. Questo esempio è costituito da XAML e da un file code-behind.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: a955f52ec7bf93b32c70259b27fb51747664ac2e
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163181"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a>Procedura: rilevare il momento in cui è stato premuto il tasto INVIO
Questo esempio Mostra come rilevare quando il <xref:System.Windows.Input.Key.Enter> tasto è premuto sulla tastiera.  
  
 Questo esempio è costituito da un file [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e da un file code-behind.  
  
## <a name="example"></a>Esempio  
 Quando l'utente preme il <xref:System.Windows.Input.Key.Enter> tasto in <xref:System.Windows.Controls.TextBox> , l'input nella casella di testo viene visualizzato in un'altra area del [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] .  
  
 Il codice XAML seguente crea l'interfaccia utente, che è costituita da un oggetto, da un oggetto <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.TextBlock> e da un oggetto <xref:System.Windows.Controls.TextBox> .  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 Il codice sottostante seguente crea il <xref:System.Windows.UIElement.KeyDown> gestore eventi.  Se il tasto premuto è la <xref:System.Windows.Input.Key.Enter> chiave, viene visualizzato un messaggio in <xref:System.Windows.Controls.TextBlock> .  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'input](input-overview.md)
- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
