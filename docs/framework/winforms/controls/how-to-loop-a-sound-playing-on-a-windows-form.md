---
title: 'Procedura: riprodurre un suono ripetutamente in un Windows Form'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sound loops
- SoundPlayer class [Windows Forms], play looping
- sounds [Windows Forms], looping
- playing sounds [Windows Forms], looping
ms.assetid: ea95dd46-10a3-46c0-8263-4b205f00df7f
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e6b4e910f30a5d125fd1ec234e896828738f62c4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-loop-a-sound-playing-on-a-windows-form"></a><span data-ttu-id="0b0b9-102">Procedura: riprodurre un suono ripetutamente in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b0b9-102">How to: Loop a Sound Playing on a Windows Form</span></span>
<span data-ttu-id="0b0b9-103">Nell'esempio di codice seguente un suono viene riprodotto ripetutamente.</span><span class="sxs-lookup"><span data-stu-id="0b0b9-103">The following code example plays a sound repeatedly.</span></span> <span data-ttu-id="0b0b9-104">Quando viene eseguito il codice nel gestore dell'evento `stopPlayingButton_Click`, l'eventuale riproduzione corrente di un suono viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="0b0b9-104">When the code in the `stopPlayingButton_Click` event handler runs, any sound currently playing stops.</span></span> <span data-ttu-id="0b0b9-105">Se non è in corso di riproduzione alcun suono, non accadrà nulla.</span><span class="sxs-lookup"><span data-stu-id="0b0b9-105">If no sound is playing, nothing happens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b0b9-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b0b9-106">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0b0b9-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="0b0b9-107">Compiling the Code</span></span>  
 <span data-ttu-id="0b0b9-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b0b9-108">This example requires:</span></span>  
  
-   <span data-ttu-id="0b0b9-109">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="0b0b9-109">References to the System and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="0b0b9-110">Sostituzione del nome del file `"c:\Windows\Media\chimes.wav"` con un nome file valido.</span><span class="sxs-lookup"><span data-stu-id="0b0b9-110">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>  
  
 <span data-ttu-id="0b0b9-111">Per informazioni sulla compilazione di questo esempio dalla riga di comando per visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="0b0b9-111">For information about building this example from the command line for visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="0b0b9-112">È anche possibile compilare questo esempio in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="0b0b9-112">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="0b0b9-113">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo tramite Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="0b0b9-113">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0b0b9-114">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="0b0b9-114">Robust Programming</span></span>  
 <span data-ttu-id="0b0b9-115">Le operazioni sui file devono essere racchiuse tra blocchi di gestione delle eccezioni appropriati.</span><span class="sxs-lookup"><span data-stu-id="0b0b9-115">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="0b0b9-116">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="0b0b9-116">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="0b0b9-117">Il nome del percorso non è valido.</span><span class="sxs-lookup"><span data-stu-id="0b0b9-117">The path name is malformed.</span></span> <span data-ttu-id="0b0b9-118">Ad esempio, contiene caratteri non validi o solo uno spazio vuoto (classe <xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="0b0b9-118">For example, it contains characters that are not valid or it is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="0b0b9-119">Il percorso è di sola lettura (classe <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="0b0b9-119">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="0b0b9-120">Il nome del percorso è `Nothing` (classe <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="0b0b9-120">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="0b0b9-121">Il nome del percorso è troppo lungo (classe <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="0b0b9-121">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="0b0b9-122">Il percorso non è valido (classe <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="0b0b9-122">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="0b0b9-123">Il percorso contiene solo due punti ":" (classe <xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="0b0b9-123">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="0b0b9-124">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0b0b9-124">.NET Framework Security</span></span>  
 <span data-ttu-id="0b0b9-125">Non basarsi sul nome del file per prendere decisioni in merito al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="0b0b9-125">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="0b0b9-126">È possibile ad esempio che il file Form1.vb non sia un file di origine di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0b0b9-126">For example, the file Form1.vb may not be a Visual Basic source file.</span></span> <span data-ttu-id="0b0b9-127">Prima di usare i dati nell'applicazione verificare tutti gli input.</span><span class="sxs-lookup"><span data-stu-id="0b0b9-127">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b0b9-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b0b9-128">See Also</span></span>  
 <xref:System.Media.SoundPlayer.PlayLooping%2A>  
 [<span data-ttu-id="0b0b9-129">Procedura: Riprodurre un suono da un Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b0b9-129">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)  
 [<span data-ttu-id="0b0b9-130">Panoramica della classe SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="0b0b9-130">SoundPlayer Class Overview</span></span>](../../../../docs/framework/winforms/controls/soundplayer-class-overview.md)
