---
title: 'Procedura: Rilevare quando il tasto premuto immettere'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: a99da5804bbc31897198b9b6d9e21da9f17dfe26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051416"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a>Procedura: Rilevare quando il tasto premuto immettere
Questo esempio viene illustrato come rilevare il momento di <xref:System.Windows.Input.Key.Enter> tasto sulla tastiera.  
  
 In questo esempio è costituito un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file e un file code-behind.  
  
## <a name="example"></a>Esempio  
 Quando l'utente preme il <xref:System.Windows.Input.Key.Enter> chiavi nel <xref:System.Windows.Controls.TextBox>, l'input nella casella di testo viene visualizzato in un'altra area della [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
 Quanto segue [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea l'interfaccia utente, che è costituito da un <xref:System.Windows.Controls.StackPanel>, un <xref:System.Windows.Controls.TextBlock>e un <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 Crea il codice seguente sotto il <xref:System.Windows.UIElement.KeyDown> gestore dell'evento.  Se la chiave che viene premuta il <xref:System.Windows.Input.Key.Enter> key, viene visualizzato un messaggio nel <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'input](input-overview.md)
- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
