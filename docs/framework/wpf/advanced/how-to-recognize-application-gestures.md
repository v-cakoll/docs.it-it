---
title: "Procedura: Riconoscere i movimenti dell'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application gestures [WPF], recognizing
- gestures [WPF], recognizing
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
ms.openlocfilehash: 647e7c9c1d785cebfdc362dc48511d865f3945dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768433"
---
# <a name="how-to-recognize-application-gestures"></a><span data-ttu-id="63b7d-102">Procedura: Riconoscere i movimenti dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="63b7d-102">How To: Recognize Application Gestures</span></span>
<span data-ttu-id="63b7d-103">Nell'esempio seguente viene illustrato come cancellare l'input penna quando un utente apporta una <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> movimenti su un' <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="63b7d-103">The following example demonstrates how to erase ink when a user makes a <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> gesture on an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="63b7d-104">Questo esempio si presuppone un' <xref:System.Windows.Controls.InkCanvas>, denominato `inkCanvas1`, viene dichiarata nel file XAML.</span><span class="sxs-lookup"><span data-stu-id="63b7d-104">This example assumes an <xref:System.Windows.Controls.InkCanvas>, called `inkCanvas1`, is declared in the XAML file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63b7d-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="63b7d-105">Example</span></span>  
 [!code-csharp[HowToRecognizeGestures#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="63b7d-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63b7d-106">See also</span></span>

- <xref:System.Windows.Ink.ApplicationGesture>
- <xref:System.Windows.Controls.InkCanvas>
- <xref:System.Windows.Controls.InkCanvas.Gesture>
