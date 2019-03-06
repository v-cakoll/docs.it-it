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
# <a name="how-to-erase-ink-on-a-custom-control"></a><span data-ttu-id="45325-102">Procedura: Cancellare l'input penna da un controllo personalizzato</span><span class="sxs-lookup"><span data-stu-id="45325-102">How to: Erase Ink on a Custom Control</span></span>
<span data-ttu-id="45325-103">Il <xref:System.Windows.Ink.IncrementalStrokeHitTester> determina se il tratto attualmente tracciato interseca un altro tratto.</span><span class="sxs-lookup"><span data-stu-id="45325-103">The <xref:System.Windows.Ink.IncrementalStrokeHitTester> determines whether the currently drawn stroke intersects another stroke.</span></span>  <span data-ttu-id="45325-104">Ciò è utile per la creazione di un controllo che consente di cancellare le parti di un tratto, il modo un utente può in un' <xref:System.Windows.Controls.InkCanvas> quando il <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> è impostata su <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span><span class="sxs-lookup"><span data-stu-id="45325-104">This is useful for creating a control that enables a user to erase parts of a stroke, the way a user can on an <xref:System.Windows.Controls.InkCanvas> when the <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> is set to <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45325-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="45325-105">Example</span></span>  
 <span data-ttu-id="45325-106">L'esempio seguente crea un controllo personalizzato che consente all'utente di cancellare le parti dei tratti.</span><span class="sxs-lookup"><span data-stu-id="45325-106">The following example creates a custom control that enables the user to erase parts of strokes.</span></span>  <span data-ttu-id="45325-107">Questo esempio crea un controllo che contiene l'input penna quando viene inizializzato.</span><span class="sxs-lookup"><span data-stu-id="45325-107">This example creates a control that contains ink when it is initialized.</span></span>  <span data-ttu-id="45325-108">Per creare un controllo che consente di raccogliere input penna, vedere [creazione di un controllo Input penna](creating-an-ink-input-control.md).</span><span class="sxs-lookup"><span data-stu-id="45325-108">To create a control that collects ink, see [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  
  
 [!code-csharp[HowToEraseInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
