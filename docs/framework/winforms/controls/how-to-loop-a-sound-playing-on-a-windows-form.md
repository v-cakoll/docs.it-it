---
title: 'Procedura: Riprodurre un suono ripetutamente in un Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sound loops
- SoundPlayer class [Windows Forms], play looping
- sounds [Windows Forms], looping
- playing sounds [Windows Forms], looping
ms.assetid: ea95dd46-10a3-46c0-8263-4b205f00df7f
ms.openlocfilehash: a74acbbbcb5646a35de54a6000a0feae30f145a5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188513"
---
# <a name="how-to-loop-a-sound-playing-on-a-windows-form"></a><span data-ttu-id="fa918-102">Procedura: Riprodurre un suono ripetutamente in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="fa918-102">How to: Loop a Sound Playing on a Windows Form</span></span>
<span data-ttu-id="fa918-103">Nell'esempio di codice seguente un suono viene riprodotto ripetutamente.</span><span class="sxs-lookup"><span data-stu-id="fa918-103">The following code example plays a sound repeatedly.</span></span> <span data-ttu-id="fa918-104">Quando viene eseguito il codice nel gestore dell'evento `stopPlayingButton_Click`, l'eventuale riproduzione corrente di un suono viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="fa918-104">When the code in the `stopPlayingButton_Click` event handler runs, any sound currently playing stops.</span></span> <span data-ttu-id="fa918-105">Se non è in corso di riproduzione alcun suono, non accadrà nulla.</span><span class="sxs-lookup"><span data-stu-id="fa918-105">If no sound is playing, nothing happens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa918-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa918-106">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fa918-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="fa918-107">Compiling the Code</span></span>  
 <span data-ttu-id="fa918-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa918-108">This example requires:</span></span>  
  
-   <span data-ttu-id="fa918-109">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="fa918-109">References to the System and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="fa918-110">Sostituzione del nome del file `"c:\Windows\Media\chimes.wav"` con un nome file valido.</span><span class="sxs-lookup"><span data-stu-id="fa918-110">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>  
  
 <span data-ttu-id="fa918-111">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="fa918-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="fa918-112">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="fa918-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="fa918-113">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="fa918-113">Robust Programming</span></span>  
 <span data-ttu-id="fa918-114">Le operazioni sui file devono essere racchiuse tra blocchi di gestione delle eccezioni appropriati.</span><span class="sxs-lookup"><span data-stu-id="fa918-114">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="fa918-115">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="fa918-115">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="fa918-116">Il nome del percorso non è valido.</span><span class="sxs-lookup"><span data-stu-id="fa918-116">The path name is malformed.</span></span> <span data-ttu-id="fa918-117">Ad esempio, contiene caratteri non validi o solo uno spazio vuoto (classe <xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="fa918-117">For example, it contains characters that are not valid or it is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="fa918-118">Il percorso è di sola lettura (classe <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="fa918-118">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="fa918-119">Il nome del percorso è `Nothing` (classe <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="fa918-119">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="fa918-120">Il nome del percorso è troppo lungo (classe <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="fa918-120">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="fa918-121">Il percorso non è valido (classe <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="fa918-121">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="fa918-122">Il percorso contiene solo due punti ":" (classe <xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="fa918-122">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="fa918-123">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fa918-123">.NET Framework Security</span></span>  
 <span data-ttu-id="fa918-124">Non basarsi sul nome del file per prendere decisioni in merito al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="fa918-124">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="fa918-125">È possibile ad esempio che il file Form1.vb non sia un file di origine di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="fa918-125">For example, the file Form1.vb may not be a Visual Basic source file.</span></span> <span data-ttu-id="fa918-126">Prima di usare i dati nell'applicazione verificare tutti gli input.</span><span class="sxs-lookup"><span data-stu-id="fa918-126">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa918-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa918-127">See also</span></span>

- <xref:System.Media.SoundPlayer.PlayLooping%2A>
- [<span data-ttu-id="fa918-128">Procedura: Riprodurre un suono da un Windows Form</span><span class="sxs-lookup"><span data-stu-id="fa918-128">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
- [<span data-ttu-id="fa918-129">Panoramica della classe SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="fa918-129">SoundPlayer Class Overview</span></span>](soundplayer-class-overview.md)
