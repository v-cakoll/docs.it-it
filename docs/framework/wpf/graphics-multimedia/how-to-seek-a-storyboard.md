---
title: 'Procedura: Cercare uno storyboard'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], seeking
- seeking Storyboards [WPF]
ms.assetid: 887bb39a-0c2a-4ae8-956d-1d9f6f8ebbfc
ms.openlocfilehash: 7553550f406cc72603aa9f65e4233a13329223a9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354284"
---
# <a name="how-to-seek-a-storyboard"></a><span data-ttu-id="9b74f-102">Procedura: Cercare uno storyboard</span><span class="sxs-lookup"><span data-stu-id="9b74f-102">How to: Seek a Storyboard</span></span>
<span data-ttu-id="9b74f-103">Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> metodo di un <xref:System.Windows.Media.Animation.Storyboard> per passare a una posizione qualsiasi nell'animazione di uno storyboard.</span><span class="sxs-lookup"><span data-stu-id="9b74f-103">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method of a <xref:System.Windows.Media.Animation.Storyboard> to jump to any position in a storyboard animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b74f-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b74f-104">Example</span></span>  
 <span data-ttu-id="9b74f-105">Di seguito è indicato il markup XAML per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="9b74f-105">Below is the XAML markup for the sample.</span></span>  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml#seekstoryboardexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="9b74f-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b74f-106">Example</span></span>  
 <span data-ttu-id="9b74f-107">Di seguito è indicato il codice usato con il codice XAML riportato sopra.</span><span class="sxs-lookup"><span data-stu-id="9b74f-107">Below is the code used with the XAML code above.</span></span>  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml.cs#seekstoryboardcodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardExample.xaml.vb#seekstoryboardcodebehindexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="9b74f-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b74f-108">See also</span></span>
- [<span data-ttu-id="9b74f-109">Cercare uno storyboard in modo sincrono</span><span class="sxs-lookup"><span data-stu-id="9b74f-109">Seek a Storyboard Synchronously</span></span>](how-to-seek-a-storyboard-synchronously.md)
