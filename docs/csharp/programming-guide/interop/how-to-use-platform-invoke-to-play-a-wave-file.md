---
title: Come usare platform invoke per riprodurre un file WAV- C# Guida alla programmazione
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: 082bd4b51e06332b0fecc633cc0501cafa8e7ff8
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635288"
---
# <a name="how-to-use-platform-invoke-to-play-a-wav-file-c-programming-guide"></a><span data-ttu-id="8246b-102">Come usare platform invoke per riprodurre un file WAV (C# guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="8246b-102">How to use platform invoke to play a WAV file (C# Programming Guide)</span></span>

<span data-ttu-id="8246b-103">Nell'esempio C# di codice seguente viene illustrato come utilizzare i servizi di Platform Invoke per riprodurre un file audio WAV nel sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="8246b-103">The following C# code example illustrates how to use platform invoke services to play a WAV sound file on the Windows operating system.</span></span>

## <a name="example"></a><span data-ttu-id="8246b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8246b-104">Example</span></span>

<span data-ttu-id="8246b-105">In questo esempio di codice viene usato <xref:System.Runtime.InteropServices.DllImportAttribute> per importare il punto di ingresso del metodo `winmm.dll` di `PlaySound` come `Form1 PlaySound()`.</span><span class="sxs-lookup"><span data-stu-id="8246b-105">This example code uses <xref:System.Runtime.InteropServices.DllImportAttribute> to import `winmm.dll`'s `PlaySound` method entry point as `Form1 PlaySound()`.</span></span> <span data-ttu-id="8246b-106">L'esempio è costituito da un semplice Windows Form con un pulsante.</span><span class="sxs-lookup"><span data-stu-id="8246b-106">The example has a simple Windows Form with a button.</span></span> <span data-ttu-id="8246b-107">Se si fa clic sul pulsante, viene visualizzata una finestra di dialogo <xref:System.Windows.Forms.OpenFileDialog> standard di Windows che consente di aprire un file da riprodurre.</span><span class="sxs-lookup"><span data-stu-id="8246b-107">Clicking the button opens a standard windows <xref:System.Windows.Forms.OpenFileDialog> dialog box so that you can open a file to play.</span></span> <span data-ttu-id="8246b-108">Quando si seleziona un file Wave, questo viene riprodotto utilizzando il metodo `PlaySound()` della libreria *winmm. dll* .</span><span class="sxs-lookup"><span data-stu-id="8246b-108">When a wave file is selected, it is played by using the `PlaySound()` method of the *winmm.dll* library.</span></span> <span data-ttu-id="8246b-109">Per altre informazioni sul metodo, vedere [Using the PlaySound function with Waveform-Audio Files ](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files) (Uso della funzione PlaySound con file audio Waveform).</span><span class="sxs-lookup"><span data-stu-id="8246b-109">For more information about this method, see [Using the PlaySound function with Waveform-Audio Files](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files).</span></span> <span data-ttu-id="8246b-110">Cercare e selezionare un file con estensione wav e fare clic su **Apri** per riprodurre il file audio usando platform invoke.</span><span class="sxs-lookup"><span data-stu-id="8246b-110">Browse and select a file that has a .wav extension, and then click **Open** to play the wave file by using platform invoke.</span></span> <span data-ttu-id="8246b-111">Il percorso completo del file selezionato verrà visualizzato in una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="8246b-111">A text box shows the full path of the file selected.</span></span>

<span data-ttu-id="8246b-112">La finestra di dialogo **File aperti** viene filtrata in modo da visualizzare solo i file con estensione wav tramite le impostazioni di filtro:</span><span class="sxs-lookup"><span data-stu-id="8246b-112">The **Open Files** dialog box is filtered to show only files that have a .wav extension through the filter settings:</span></span>

[!code-csharp[csProgGuideInterop#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#5)]

[!code-csharp[csProgGuideInterop#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#3)]

## <a name="compiling-the-code"></a><span data-ttu-id="8246b-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8246b-113">Compiling the code</span></span>

1. <span data-ttu-id="8246b-114">Creare un nuovo C# progetto di applicazione Windows Forms in Visual Studio e denominarlo **winsound**.</span><span class="sxs-lookup"><span data-stu-id="8246b-114">Create a new C# Windows Forms Application project in Visual Studio and name it **WinSound**.</span></span>

2. <span data-ttu-id="8246b-115">Copiare il codice precedente e incollarlo sul contenuto del file *Form1.cs* .</span><span class="sxs-lookup"><span data-stu-id="8246b-115">Copy the code above, and paste it over the contents of the *Form1.cs* file.</span></span>

3. <span data-ttu-id="8246b-116">Copiare il codice seguente e incollarlo nel file *Form1.designer.cs* , nel metodo `InitializeComponent()`, dopo qualsiasi codice esistente.</span><span class="sxs-lookup"><span data-stu-id="8246b-116">Copy the following code, and paste it in the *Form1.Designer.cs* file, in the `InitializeComponent()` method, after any existing code.</span></span>

     [!code-csharp[csProgGuideInterop#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#4)]

4. <span data-ttu-id="8246b-117">Compilare ed eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="8246b-117">Compile and run the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="8246b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8246b-118">See also</span></span>

- [<span data-ttu-id="8246b-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="8246b-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8246b-120">Cenni preliminari sull'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="8246b-120">Interoperability Overview</span></span>](interoperability-overview.md)
- [<span data-ttu-id="8246b-121">Informazioni dettagliate su platform invoke</span><span class="sxs-lookup"><span data-stu-id="8246b-121">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="8246b-122">Marshalling dei dati con platform invoke</span><span class="sxs-lookup"><span data-stu-id="8246b-122">Marshaling Data with Platform Invoke</span></span>](../../../framework/interop/marshaling-data-with-platform-invoke.md)
