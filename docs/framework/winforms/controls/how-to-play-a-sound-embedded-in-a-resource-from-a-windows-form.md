---
title: 'Procedura: Riprodurre un suono incorporato in una risorsa da un Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing from resources
- resources [Windows Forms], playing sounds
- playing sounds [Windows Forms], from resources
- SoundPlayer class [Windows Forms], playing sounds from resources
ms.assetid: 7d148bb6-8a1e-47d7-a08d-35828d2e688f
ms.openlocfilehash: f52cac4ca16adee232fae6fe2c1540bf5d3cb8cf
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708184"
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a><span data-ttu-id="5a960-102">Procedura: Riprodurre un suono incorporato in una risorsa da un Windows Form</span><span class="sxs-lookup"><span data-stu-id="5a960-102">How to: Play a Sound Embedded in a Resource from a Windows Form</span></span>
<span data-ttu-id="5a960-103">È possibile usare il <xref:System.Media.SoundPlayer> classe per riprodurre un suono da una risorsa incorporata.</span><span class="sxs-lookup"><span data-stu-id="5a960-103">You can use the <xref:System.Media.SoundPlayer> class to play a sound from an embedded resource.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a960-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="5a960-104">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Sound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5a960-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="5a960-105">Compiling the Code</span></span>  
 <span data-ttu-id="5a960-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a960-106">This example requires:</span></span>  
  
 <span data-ttu-id="5a960-107">L'importazione di <xref:System.Media?displayProperty=nameWithType> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5a960-107">Importing the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="5a960-108">Inclusione del file audio come risorsa incorporata nel progetto.</span><span class="sxs-lookup"><span data-stu-id="5a960-108">Including the sound file as an embedded resource in your project.</span></span>  
  
 <span data-ttu-id="5a960-109">Sostituzione di "\<AssemblyName>" con il nome dell'assembly in cui è incorporato il file audio.</span><span class="sxs-lookup"><span data-stu-id="5a960-109">Replacing "\<AssemblyName>" with the name of the assembly in which the sound file is embedded.</span></span> <span data-ttu-id="5a960-110">Non includere il suffisso ". dll".</span><span class="sxs-lookup"><span data-stu-id="5a960-110">Do not include the ".dll" suffix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a960-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a960-111">See also</span></span>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="5a960-112">Procedura: Riprodurre un suono da un Windows Form</span><span class="sxs-lookup"><span data-stu-id="5a960-112">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
- [<span data-ttu-id="5a960-113">Procedura: Riprodurre un suono ripetutamente in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="5a960-113">How to: Loop a Sound Playing on a Windows Form</span></span>](how-to-loop-a-sound-playing-on-a-windows-form.md)
