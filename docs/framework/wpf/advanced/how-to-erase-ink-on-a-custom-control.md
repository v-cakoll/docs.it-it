---
title: 'Procedura: cancellare l''input penna da un controllo personalizzato'
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
helpviewer_keywords:
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 23d234d97d6b25394df87016f0671d86b10a2853
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-erase-ink-on-a-custom-control"></a><span data-ttu-id="52ff1-102">Procedura: cancellare l'input penna da un controllo personalizzato</span><span class="sxs-lookup"><span data-stu-id="52ff1-102">How to: Erase Ink on a Custom Control</span></span>
<span data-ttu-id="52ff1-103">Il <xref:System.Windows.Ink.IncrementalStrokeHitTester> determina se il tratto attualmente tracciato interseca un'altra traccia.</span><span class="sxs-lookup"><span data-stu-id="52ff1-103">The <xref:System.Windows.Ink.IncrementalStrokeHitTester> determines whether the currently drawn stroke intersects another stroke.</span></span>  <span data-ttu-id="52ff1-104">Ciò è utile per la creazione di un controllo che consente di cancellare parti di un tratto, la modalità di un utente può su un <xref:System.Windows.Controls.InkCanvas> quando il <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> è impostato su <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span><span class="sxs-lookup"><span data-stu-id="52ff1-104">This is useful for creating a control that enables a user to erase parts of a stroke, the way a user can on an <xref:System.Windows.Controls.InkCanvas> when the <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> is set to <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52ff1-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="52ff1-105">Example</span></span>  
 <span data-ttu-id="52ff1-106">Nell'esempio seguente viene creato un controllo personalizzato che consente di cancellare le parti dei tratti.</span><span class="sxs-lookup"><span data-stu-id="52ff1-106">The following example creates a custom control that enables the user to erase parts of strokes.</span></span>  <span data-ttu-id="52ff1-107">Questo esempio crea un controllo che contiene l'input penna quando viene inizializzato.</span><span class="sxs-lookup"><span data-stu-id="52ff1-107">This example creates a control that contains ink when it is initialized.</span></span>  <span data-ttu-id="52ff1-108">Per creare un controllo che raccoglie input penna, vedere [creazione di un controllo di Input penna](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).</span><span class="sxs-lookup"><span data-stu-id="52ff1-108">To create a control that collects ink, see [Creating an Ink Input Control](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).</span></span>  
  
 [!code-csharp[HowToEraseInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
