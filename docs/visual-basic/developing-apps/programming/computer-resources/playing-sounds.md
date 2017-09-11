---
title: Riproduzione di suoni (Visual Basic)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- system sounds, playing
- system sounds
- playing sounds, Visual Basic
- sound loops
- My.Computer.Audio object, tasks
- sounds, playing
- sounds, background
- playing sounds
ms.assetid: f0d9e4ab-57c7-47b6-86d3-99ff07078040
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a15efff54bd54fdaced6c741cd6acf5c8b544cdd
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="playing-sounds-visual-basic"></a><span data-ttu-id="1b303-102">Riproduzione di suoni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b303-102">Playing Sounds (Visual Basic)</span></span>
<span data-ttu-id="1b303-103">Il metodo `My.Computer.Audio` offre metodi per la riproduzione di suoni.</span><span class="sxs-lookup"><span data-stu-id="1b303-103">The `My.Computer.Audio` object provides methods for playing sounds.</span></span>  
  
## <a name="playing-sounds"></a><span data-ttu-id="1b303-104">Riproduzione di suoni</span><span class="sxs-lookup"><span data-stu-id="1b303-104">Playing Sounds</span></span>  
 <span data-ttu-id="1b303-105">La riproduzione in background consente all'applicazione di eseguire altro codice durante la riproduzione di suoni.</span><span class="sxs-lookup"><span data-stu-id="1b303-105">Background playing lets the application execute other code while the sound plays.</span></span> <span data-ttu-id="1b303-106">Il metodo `My.Computer.Audio.Play` consente all'applicazione di riprodurre un solo suono di sottofondo alla volta: quando l'applicazione riproduce un nuovo suono di sottofondo, viene interrotta la riproduzione del suono di sottofondo precedente.</span><span class="sxs-lookup"><span data-stu-id="1b303-106">The `My.Computer.Audio.Play` method allows the application to play only one background sound at a time; when the application plays a new background sound, it stops playing the previous background sound.</span></span> <span data-ttu-id="1b303-107">È anche possibile riprodurre un suono e attendere il completamento della riproduzione.</span><span class="sxs-lookup"><span data-stu-id="1b303-107">You can also play a sound and wait for it to complete.</span></span>  
  
 <span data-ttu-id="1b303-108">Nell'esempio seguente il metodo `My.Computer.Audio.Play` riproduce un suono.</span><span class="sxs-lookup"><span data-stu-id="1b303-108">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="1b303-109">Quando è specificato `AudioPlayMode.WaitToComplete`, `My.Computer.Audio.Play` attende il completamento del suono prima di continuare a chiamare codice.</span><span class="sxs-lookup"><span data-stu-id="1b303-109">When `AudioPlayMode.WaitToComplete` is specified, `My.Computer.Audio.Play` waits until the sound completes before calling code continues.</span></span> <span data-ttu-id="1b303-110">Quando si usa questo esempio è necessario assicurarsi che il nome file faccia riferimento a un file audio con estensione wav presente nel computer.</span><span class="sxs-lookup"><span data-stu-id="1b303-110">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer</span></span>  
  
 <span data-ttu-id="1b303-111">[!code-vb[VbVbalrMyComputer#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="1b303-111">[!code-vb[VbVbalrMyComputer#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_1.vb)]</span></span>  
  
 <span data-ttu-id="1b303-112">Nell'esempio seguente il metodo `My.Computer.Audio.Play` riproduce un suono.</span><span class="sxs-lookup"><span data-stu-id="1b303-112">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="1b303-113">Quando si usa questo esempio è necessario assicurarsi che le risorse dell'applicazione includano un file audio con estensione wav denominato Waterfall.</span><span class="sxs-lookup"><span data-stu-id="1b303-113">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 <span data-ttu-id="1b303-114">[!code-vb[VbVbalrMyComputer#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="1b303-114">[!code-vb[VbVbalrMyComputer#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_2.vb)]</span></span>  
  
## <a name="playing-looping-sounds"></a><span data-ttu-id="1b303-115">Riproduzione di file audio a ciclo continuo</span><span class="sxs-lookup"><span data-stu-id="1b303-115">Playing Looping Sounds</span></span>  
 <span data-ttu-id="1b303-116">Nell'esempio seguente il metodo `My.Computer.Audio.Play` riproduce il file audio specificato in background quando è specificato `PlayMode.BackgroundLoop`.</span><span class="sxs-lookup"><span data-stu-id="1b303-116">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="1b303-117">Quando si usa questo esempio è necessario assicurarsi che il nome file faccia riferimento a un file audio con estensione wav presente nel computer.</span><span class="sxs-lookup"><span data-stu-id="1b303-117">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer.</span></span>  
  
 <span data-ttu-id="1b303-118">[!code-vb[VbVbalrMyComputer#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="1b303-118">[!code-vb[VbVbalrMyComputer#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_3.vb)]</span></span>  
  
 <span data-ttu-id="1b303-119">Nell'esempio seguente il metodo `My.Computer.Audio.Play` riproduce il file audio specificato in background quando è specificato `PlayMode.BackgroundLoop`.</span><span class="sxs-lookup"><span data-stu-id="1b303-119">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="1b303-120">Quando si usa questo esempio è necessario assicurarsi che le risorse dell'applicazione includano un file audio con estensione wav denominato Waterfall.</span><span class="sxs-lookup"><span data-stu-id="1b303-120">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 <span data-ttu-id="1b303-121">[!code-vb[VbVbalrMyComputer#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="1b303-121">[!code-vb[VbVbalrMyComputer#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_4.vb)]</span></span>  
  
 <span data-ttu-id="1b303-122">L'esempio di codice precedente è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="1b303-122">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="1b303-123">Nello strumento di selezione dei frammenti di codice il frammento di codice si trova in **Applicazioni Windows Form > Audio**.</span><span class="sxs-lookup"><span data-stu-id="1b303-123">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="1b303-124">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="1b303-124">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="1b303-125">In generale, quando un'applicazione riproduce un file audio a ciclo continuo, la riproduzione dovrà prima o poi essere interrotta.</span><span class="sxs-lookup"><span data-stu-id="1b303-125">In general, when an application plays a looping sound, it should eventually stop the sound.</span></span>  
  
## <a name="stopping-the-playing-of-sounds-in-the-background"></a><span data-ttu-id="1b303-126">Interruzione della riproduzione di suoni in background</span><span class="sxs-lookup"><span data-stu-id="1b303-126">Stopping the Playing of Sounds in the Background</span></span>  
 <span data-ttu-id="1b303-127">Usare il metodo `My.Computer.Audio.Stop` per interrompere la riproduzione di file audio in background o a ciclo continuo dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1b303-127">Use the `My.Computer.Audio.Stop` method to stop the application's currently playing background or looping sound.</span></span>  
  
 <span data-ttu-id="1b303-128">In generale, quando un'applicazione riproduce un file audio a ciclo continuo, la riproduzione dovrà prima o poi essere interrotta.</span><span class="sxs-lookup"><span data-stu-id="1b303-128">In general, when an application plays a looping sound, it should stop the sound at some point.</span></span>  
  
 <span data-ttu-id="1b303-129">L'esempio seguente interrompe la riproduzione di un file audio in background.</span><span class="sxs-lookup"><span data-stu-id="1b303-129">The following example stops a sound that is playing in the background.</span></span>  
  
 <span data-ttu-id="1b303-130">[!code-vb[VbVbalrMyComputer#18](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="1b303-130">[!code-vb[VbVbalrMyComputer#18](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_5.vb)]</span></span>  
  
 <span data-ttu-id="1b303-131">L'esempio di codice precedente è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="1b303-131">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="1b303-132">Nello strumento di selezione dei frammenti di codice il frammento di codice si trova in **Applicazioni Windows Form > Audio**.</span><span class="sxs-lookup"><span data-stu-id="1b303-132">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="1b303-133">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="1b303-133">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="playing-system-sounds"></a><span data-ttu-id="1b303-134">Riproduzione di suoni di sistema</span><span class="sxs-lookup"><span data-stu-id="1b303-134">Playing System Sounds</span></span>  
 <span data-ttu-id="1b303-135">Usare il metodo `My.Computer.Audio.PlaySystemSound` per riprodurre il suono di sistema specificato.</span><span class="sxs-lookup"><span data-stu-id="1b303-135">Use the `My.Computer.Audio.PlaySystemSound` method to play the specified system sound.</span></span>  
  
 <span data-ttu-id="1b303-136">Il metodo `My.Computer.Audio.PlaySystemSound` accetta come parametro uno dei membri condivisi della classe <xref:System.Media.SystemSound>.</span><span class="sxs-lookup"><span data-stu-id="1b303-136">The `My.Computer.Audio.PlaySystemSound` method takes as a parameter one of the shared members from the <xref:System.Media.SystemSound> class.</span></span> <span data-ttu-id="1b303-137">Il suono di sistema <xref:System.Media.SystemSounds.Asterisk%2A> indica in genere la presenza di errori.</span><span class="sxs-lookup"><span data-stu-id="1b303-137">The system sound <xref:System.Media.SystemSounds.Asterisk%2A> generally denotes errors.</span></span>  
  
 <span data-ttu-id="1b303-138">L'esempio seguente usa il metodo `My.Computer.Audio.PlaySystemSound` per riprodurre un suono di sistema.</span><span class="sxs-lookup"><span data-stu-id="1b303-138">The following example uses the `My.Computer.Audio.PlaySystemSound` method to play a system sound.</span></span>  
  
 <span data-ttu-id="1b303-139">[!code-vb[VbVbalrMyComputer#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="1b303-139">[!code-vb[VbVbalrMyComputer#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_6.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b303-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b303-140">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Audio>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>   
 <xref:Microsoft.VisualBasic.AudioPlayMode>

