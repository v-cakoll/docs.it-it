---
title: "Procedura: riconoscere i movimenti dell'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application gestures [WPF], recognizing
- gestures [WPF], recognizing
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
ms.openlocfilehash: 82ca91fc9e3745012d82357991b67f398079f1f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543693"
---
# <a name="how-to-recognize-application-gestures"></a><span data-ttu-id="02701-102">Procedura: riconoscere i movimenti dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="02701-102">How To: Recognize Application Gestures</span></span>
<span data-ttu-id="02701-103">Nell'esempio riportato di seguito viene illustrato come cancellare l'input penna quando un utente apporta una <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> movimento in un <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="02701-103">The following example demonstrates how to erase ink when a user makes a <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> gesture on an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="02701-104">Questo esempio si presuppone un <xref:System.Windows.Controls.InkCanvas>, denominato `inkCanvas1`, viene dichiarata nel file XAML.</span><span class="sxs-lookup"><span data-stu-id="02701-104">This example assumes an <xref:System.Windows.Controls.InkCanvas>, called `inkCanvas1`, is declared in the XAML file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02701-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="02701-105">Example</span></span>  
 [!code-csharp[HowToRecognizeGestures#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="02701-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02701-106">See Also</span></span>  
 <xref:System.Windows.Ink.ApplicationGesture>  
 <xref:System.Windows.Controls.InkCanvas>  
 <xref:System.Windows.Controls.InkCanvas.Gesture>
