---
title: 'Procedura: Rileva quando viene premuto il tasto invio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: e2337826077c836696937f91541d6d261f1270aa
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004815"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a>Procedura: Rileva quando viene premuto il tasto invio
Questo esempio Mostra come rilevare quando il tasto <xref:System.Windows.Input.Key.Enter> è premuto sulla tastiera.  
  
 Questo esempio è costituito da un file [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e da un file code-behind.  
  
## <a name="example"></a>Esempio  
 Quando l'utente preme il tasto <xref:System.Windows.Input.Key.Enter> nella <xref:System.Windows.Controls.TextBox>, l'input nella casella di testo viene visualizzato in un'altra area del [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
 Il codice XAML seguente crea l'interfaccia utente, che è costituita da un <xref:System.Windows.Controls.StackPanel>, da un <xref:System.Windows.Controls.TextBlock> e da un <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 Il codice sottostante seguente crea il gestore dell'evento <xref:System.Windows.UIElement.KeyDown>.  Se il tasto premuto è il tasto <xref:System.Windows.Input.Key.Enter>, viene visualizzato un messaggio nel <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'input](input-overview.md)
- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
