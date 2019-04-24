---
title: 'Procedura: Usare platform invoke per riprodurre un file audio - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: 29c36bd0494879b66674cf3a3c404fdaf3908f59
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59323811"
---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a><span data-ttu-id="e50ce-102">Procedura: Usare platform invoke per riprodurre un file audio (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e50ce-102">How to: Use Platform Invoke to Play a Wave File (C# Programming Guide)</span></span>
<span data-ttu-id="e50ce-103">L'esempio di codice C# seguente descrive come usare i servizi platform invoke per riprodurre un file audio con estensione wav nel sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="e50ce-103">The following C# code example illustrates how to use platform invoke services to play a wave sound file on the Windows operating system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e50ce-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e50ce-104">Example</span></span>  
 <span data-ttu-id="e50ce-105">In questo esempio di codice viene usato `DllImport` per importare il punto di ingresso del metodo `winmm.dll` di `PlaySound` come `Form1 PlaySound()`.</span><span class="sxs-lookup"><span data-stu-id="e50ce-105">This example code uses `DllImport` to import `winmm.dll`'s `PlaySound` method entry point as `Form1 PlaySound()`.</span></span> <span data-ttu-id="e50ce-106">L'esempio è costituito da un semplice Windows Form con un pulsante.</span><span class="sxs-lookup"><span data-stu-id="e50ce-106">The example has a simple Windows Form with a button.</span></span> <span data-ttu-id="e50ce-107">Se si fa clic sul pulsante, viene visualizzata una finestra di dialogo <xref:System.Windows.Forms.OpenFileDialog> standard di Windows che consente di aprire un file da riprodurre.</span><span class="sxs-lookup"><span data-stu-id="e50ce-107">Clicking the button opens a standard windows <xref:System.Windows.Forms.OpenFileDialog> dialog box so that you can open a file to play.</span></span> <span data-ttu-id="e50ce-108">Dopo averlo selezionato, il file audio viene riprodotto usando il metodo `PlaySound()` della raccolta `winmm.dll`.</span><span class="sxs-lookup"><span data-stu-id="e50ce-108">When a wave file is selected, it is played by using the `PlaySound()` method of the `winmm.dll` library.</span></span> <span data-ttu-id="e50ce-109">Per altre informazioni sul metodo, vedere [Using the PlaySound function with Waveform-Audio Files ](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files) (Uso della funzione PlaySound con file audio Waveform).</span><span class="sxs-lookup"><span data-stu-id="e50ce-109">For more information about this method, see [Using the PlaySound function with Waveform-Audio Files](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files).</span></span> <span data-ttu-id="e50ce-110">Cercare e selezionare un file con estensione wav e fare clic su **Apri** per riprodurre il file audio usando platform invoke.</span><span class="sxs-lookup"><span data-stu-id="e50ce-110">Browse and select a file that has a .wav extension, and then click **Open** to play the wave file by using platform invoke.</span></span> <span data-ttu-id="e50ce-111">Il percorso completo del file selezionato verrà visualizzato in una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="e50ce-111">A text box shows the full path of the file selected.</span></span>  
  
 <span data-ttu-id="e50ce-112">La finestra di dialogo **File aperti** viene filtrata in modo da visualizzare solo i file con estensione wav tramite le impostazioni di filtro:</span><span class="sxs-lookup"><span data-stu-id="e50ce-112">The **Open Files** dialog box is filtered to show only files that have a .wav extension through the filter settings:</span></span>  
  
 [!code-csharp[csProgGuideInterop#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#5)]  
  
 [!code-csharp[csProgGuideInterop#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e50ce-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e50ce-113">Compiling the Code</span></span>  
  
### <a name="to-compile-the-code"></a><span data-ttu-id="e50ce-114">Per compilare il codice</span><span class="sxs-lookup"><span data-stu-id="e50ce-114">To compile the code</span></span>  
  
1. <span data-ttu-id="e50ce-115">Creare un nuovo progetto di applicazione Windows C# in Visual Studio e denominarlo **WinSound**.</span><span class="sxs-lookup"><span data-stu-id="e50ce-115">Create a new C# Windows Application project in Visual Studio and name it **WinSound**.</span></span>  
  
2. <span data-ttu-id="e50ce-116">Copiare il codice precedente e incollarlo nel contenuto del file `Form1.cs`.</span><span class="sxs-lookup"><span data-stu-id="e50ce-116">Copy the code above, and paste it over the contents of the `Form1.cs` file.</span></span>  
  
3. <span data-ttu-id="e50ce-117">Copiare il codice riportato di seguito e incollarlo nel file `Form1.Designer.cs`, nel metodo `InitializeComponent()`, dopo il codice esistente.</span><span class="sxs-lookup"><span data-stu-id="e50ce-117">Copy the following code, and paste it in the `Form1.Designer.cs` file, in the `InitializeComponent()` method, after any existing code.</span></span>  
  
     [!code-csharp[csProgGuideInterop#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#4)]  
  
4. <span data-ttu-id="e50ce-118">Compilare ed eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="e50ce-118">Compile and run the code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e50ce-119">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e50ce-119">.NET Framework Security</span></span>  
 <span data-ttu-id="e50ce-120">Per altre informazioni, vedere [Sicurezza in .NET](../../../standard/security/index.md).</span><span class="sxs-lookup"><span data-stu-id="e50ce-120">For more information, see [Security in .NET](../../../standard/security/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e50ce-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e50ce-121">See also</span></span>

- [<span data-ttu-id="e50ce-122">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e50ce-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e50ce-123">Cenni preliminari sull'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="e50ce-123">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)
- [<span data-ttu-id="e50ce-124">Informazioni dettagliate su platform invoke</span><span class="sxs-lookup"><span data-stu-id="e50ce-124">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="e50ce-125">Marshalling dei dati con platform invoke</span><span class="sxs-lookup"><span data-stu-id="e50ce-125">Marshaling Data with Platform Invoke</span></span>](../../../framework/interop/marshaling-data-with-platform-invoke.md)
