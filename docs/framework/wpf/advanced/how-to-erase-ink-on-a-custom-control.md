---
title: "Procedura: cancellare l'input penna da un controllo personalizzato"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
ms.openlocfilehash: 66c0d19b368b56821fd4034ec4c7cd397b244ab0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543247"
---
# <a name="how-to-erase-ink-on-a-custom-control"></a>Procedura: cancellare l'input penna da un controllo personalizzato
Il <xref:System.Windows.Ink.IncrementalStrokeHitTester> determina se il tratto attualmente tracciato interseca un'altra traccia.  Ciò è utile per la creazione di un controllo che consente di cancellare parti di un tratto, la modalità di un utente può su un <xref:System.Windows.Controls.InkCanvas> quando il <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> è impostato su <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un controllo personalizzato che consente di cancellare le parti dei tratti.  Questo esempio crea un controllo che contiene l'input penna quando viene inizializzato.  Per creare un controllo che raccoglie input penna, vedere [creazione di un controllo di Input penna](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).  
  
 [!code-csharp[HowToEraseInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
