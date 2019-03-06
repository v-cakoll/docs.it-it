---
title: "Procedura: Creare un pulsante con un'immagine"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: fe9f35a6f83c5a839823d94c4d3c55e01b192fb1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352035"
---
# <a name="how-to-create-a-button-that-has-an-image"></a>Procedura: Creare un pulsante con un'immagine
In questo esempio viene illustrato come includere un'immagine su un <xref:System.Windows.Controls.Button>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea due <xref:System.Windows.Controls.Button> controlli. Uno <xref:System.Windows.Controls.Button> contiene testo e l'altro contenente un'immagine. L'immagine è in una cartella denominata dati, che sono una sottocartella della cartella del progetto di esempio. Quando un utente sceglie il <xref:System.Windows.Controls.Button> che contiene l'immagine, lo sfondo e il testo di altro <xref:System.Windows.Controls.Button> modificare.  
  
 Questo esempio viene creato <xref:System.Windows.Controls.Button> controllati tramite markup, ma usa il codice per scrivere il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestori eventi.  
  
 [!code-xaml[BtnColor#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a>Vedere anche
- [Controlli](index.md)
- [Libreria di controlli](control-library.md)
