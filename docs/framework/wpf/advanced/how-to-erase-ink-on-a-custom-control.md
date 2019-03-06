---
title: "Procedura: Cancellare l'input penna da un controllo personalizzato"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
ms.openlocfilehash: 60e2af64cb0c5b313f4f1201cab70da6a88f61e7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365893"
---
# <a name="how-to-erase-ink-on-a-custom-control"></a>Procedura: Cancellare l'input penna da un controllo personalizzato
Il <xref:System.Windows.Ink.IncrementalStrokeHitTester> determina se il tratto attualmente tracciato interseca un altro tratto.  Ciò è utile per la creazione di un controllo che consente di cancellare le parti di un tratto, il modo un utente può in un' <xref:System.Windows.Controls.InkCanvas> quando il <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> è impostata su <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea un controllo personalizzato che consente all'utente di cancellare le parti dei tratti.  Questo esempio crea un controllo che contiene l'input penna quando viene inizializzato.  Per creare un controllo che consente di raccogliere input penna, vedere [creazione di un controllo Input penna](creating-an-ink-input-control.md).  
  
 [!code-csharp[HowToEraseInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
