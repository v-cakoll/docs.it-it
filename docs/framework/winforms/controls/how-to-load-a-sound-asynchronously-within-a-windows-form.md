---
title: 'Procedura: Caricare in modo asincrono un suono in un Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SoundPlayer class [Windows Forms], loading sounds asynchronously
- sounds [Windows Forms], loading on separate threads
- threading [Windows Forms], sounds
ms.assetid: 3b6a9296-1d5e-4d52-a4ba-94366d6fe302
ms.openlocfilehash: 2de2be478e81183201cc85e1a6dfd6f1a1833af6
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858278"
---
# <a name="how-to-load-a-sound-asynchronously-within-a-windows-form"></a><span data-ttu-id="db7be-102">Procedura: Caricare in modo asincrono un suono in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="db7be-102">How to: Load a Sound Asynchronously within a Windows Form</span></span>
<span data-ttu-id="db7be-103">Nell'esempio di codice seguente viene caricato un suono in modo asincrono da un URL e quindi viene riprodotto in un nuovo thread.</span><span class="sxs-lookup"><span data-stu-id="db7be-103">The following code example asynchronously loads a sound from an URL and then plays it on a new thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db7be-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="db7be-104">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="db7be-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="db7be-105">Compiling the Code</span></span>  
 <span data-ttu-id="db7be-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="db7be-106">This example requires:</span></span>  
  
-   <span data-ttu-id="db7be-107">Riferimenti agli assembly System e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="db7be-107">References to the System and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="db7be-108">Sostituzione del nome del file `"http://www.tailspintoys.com/sounds/stop.wav"` con un nome file valido.</span><span class="sxs-lookup"><span data-stu-id="db7be-108">That you replace the file name `"http://www.tailspintoys.com/sounds/stop.wav"` with a valid file name.</span></span>  
  
 <span data-ttu-id="db7be-109">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="db7be-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="db7be-110">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="db7be-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="db7be-111">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo tramite Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="db7be-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="db7be-112">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="db7be-112">Robust Programming</span></span>  
 <span data-ttu-id="db7be-113">Le operazioni sui file devono essere racchiuse tra blocchi di gestione delle eccezioni appropriati.</span><span class="sxs-lookup"><span data-stu-id="db7be-113">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="db7be-114">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="db7be-114">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="db7be-115">Il nome del percorso non è valido.</span><span class="sxs-lookup"><span data-stu-id="db7be-115">The path name is malformed.</span></span> <span data-ttu-id="db7be-116">Ad esempio, contiene caratteri non validi o solo uno spazio vuoto (classe <xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="db7be-116">For example, it contains characters that are not valid or is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="db7be-117">Il percorso è di sola lettura (classe <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="db7be-117">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="db7be-118">Il nome del percorso è `Nothing` (classe <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="db7be-118">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="db7be-119">Il nome del percorso è troppo lungo (classe <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="db7be-119">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="db7be-120">Il percorso non è valido (classe <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="db7be-120">The path is not valid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="db7be-121">Il percorso contiene solo due punti ":" (classe <xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="db7be-121">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="db7be-122">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="db7be-122">.NET Framework Security</span></span>  
 <span data-ttu-id="db7be-123">Non basarsi sul nome del file per prendere decisioni in merito al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="db7be-123">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="db7be-124">È possibile ad esempio che il file `Form1.vb` non sia un file di origine di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="db7be-124">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="db7be-125">Prima di usare i dati nell'applicazione verificare tutti gli input.</span><span class="sxs-lookup"><span data-stu-id="db7be-125">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db7be-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db7be-126">See Also</span></span>  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <xref:System.Media.SoundPlayer.LoadCompleted>  
 <xref:System.Media.SoundPlayer.Play%2A>  
 [<span data-ttu-id="db7be-127">Procedura: Riprodurre un suono da un Windows Form</span><span class="sxs-lookup"><span data-stu-id="db7be-127">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
