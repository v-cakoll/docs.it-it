---
title: 'Procedura: creare un pulsante con un''immagine'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fa3aa5454629d53fd8864df6a4f204e22028208f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-button-that-has-an-image"></a>Procedura: creare un pulsante con un'immagine
In questo esempio viene illustrato come includere un'immagine in un <xref:System.Windows.Controls.Button>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea due <xref:System.Windows.Controls.Button> controlli. Uno <xref:System.Windows.Controls.Button> contiene testo e l'altro contenente un'immagine. L'immagine è in una cartella denominata dati, che sono una sottocartella della cartella del progetto dell'esempio. Quando un utente sceglie il <xref:System.Windows.Controls.Button> che contiene l'immagine, lo sfondo e il testo di altro <xref:System.Windows.Controls.Button> modificare.  
  
 Questo esempio viene creato <xref:System.Windows.Controls.Button> controlla tramite markup, ma utilizza codice per scrivere il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestori eventi.  
  
 [!code-xaml[BtnColor#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a>Vedere anche  
 [Controlli](../../../../docs/framework/wpf/controls/index.md)  
 [Libreria di controlli](../../../../docs/framework/wpf/controls/control-library.md)
