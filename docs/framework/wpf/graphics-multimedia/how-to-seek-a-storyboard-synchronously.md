---
title: 'Procedura: cercare uno storyboard in modo sincrono'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- seeking Storyboards synchronously [WPF]
- Storyboards [WPF], seeking synchronously
ms.assetid: 03e06271-a946-4810-88ea-3fb4cfa9e0f1
ms.openlocfilehash: 9557563dc1ae0392ad6a47063e43a8949e5f9922
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560006"
---
# <a name="how-to-seek-a-storyboard-synchronously"></a><span data-ttu-id="06585-102">Procedura: cercare uno storyboard in modo sincrono</span><span class="sxs-lookup"><span data-stu-id="06585-102">How to: Seek a Storyboard Synchronously</span></span>
<span data-ttu-id="06585-103">Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A> metodo di un <xref:System.Windows.Media.Animation.Storyboard> per cercare in qualsiasi posizione dell'animazione di uno storyboard in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="06585-103">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A> method of a <xref:System.Windows.Media.Animation.Storyboard> to seek to any position in a storyboard animation synchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06585-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="06585-104">Example</span></span>  
 <span data-ttu-id="06585-105">Di seguito è indicato il markup XAML per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="06585-105">The following is the XAML markup for the sample.</span></span>  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardSynchronouslyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardSynchronouslyExample.xaml#seekstoryboardsynchronouslyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="06585-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="06585-106">Example</span></span>  
 <span data-ttu-id="06585-107">Di seguito è indicato il codice usato con il codice XAML riportato sopra.</span><span class="sxs-lookup"><span data-stu-id="06585-107">The following is the code used with the XAML code above.</span></span>  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardSynchronouslyCodeBehindExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardSynchronouslyExample.xaml.cs#seekstoryboardsynchronouslycodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardSynchronouslyCodeBehindExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardSynchronouslyExample.xaml.vb#seekstoryboardsynchronouslycodebehindexamplewholepage)]
