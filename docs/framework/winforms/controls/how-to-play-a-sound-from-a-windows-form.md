---
title: 'Procedura: Riprodurre un suono da un Windows Form'
description: Informazioni su come riprodurre un suono da un Windows Form in un determinato percorso in fase di esecuzione. Vengono inoltre fornite informazioni sulla compilazione del codice e del Framework di sicurezza di .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playing sounds [Windows Forms], Windows Forms
- sounds [Windows Forms], playing
- sounds
- My.Computer.Audio object [Windows Forms], playing sounds
- examples [Windows Forms], sounds
ms.assetid: 3d3350b7-1ebd-4e05-a738-48ca1160a19d
ms.openlocfilehash: beb17d994e224f41b2b590ecb1401988cdad314d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85613748"
---
# <a name="how-to-play-a-sound-from-a-windows-form"></a><span data-ttu-id="b29cf-104">Procedura: Riprodurre un suono da un Windows Form</span><span class="sxs-lookup"><span data-stu-id="b29cf-104">How to: Play a Sound from a Windows Form</span></span>
<span data-ttu-id="b29cf-105">In questo esempio viene riprodotto un suono in un percorso specificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b29cf-105">This example plays a sound at a given path at run time.</span></span>

## <a name="example"></a><span data-ttu-id="b29cf-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="b29cf-106">Example</span></span>

```vb
Sub PlaySimpleSound()
    My.Computer.Audio.Play("c:\Windows\Media\chimes.wav")
End Sub
```

```csharp
private void playSimpleSound()
{
    SoundPlayer simpleSound = new SoundPlayer(@"c:\Windows\Media\chimes.wav");
    simpleSound.Play();
}
```

## <a name="compiling-the-code"></a><span data-ttu-id="b29cf-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b29cf-107">Compiling the Code</span></span>
 <span data-ttu-id="b29cf-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b29cf-108">This example requires:</span></span>

- <span data-ttu-id="b29cf-109">Sostituzione del nome del file `"c:\Windows\Media\chimes.wav"` con un nome file valido.</span><span class="sxs-lookup"><span data-stu-id="b29cf-109">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>

- <span data-ttu-id="b29cf-110">C# Riferimento allo <xref:System.Media?displayProperty=nameWithType> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b29cf-110">(C#) A reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="b29cf-111">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="b29cf-111">Robust Programming</span></span>
 <span data-ttu-id="b29cf-112">Le operazioni sui file devono essere racchiuse tra blocchi appropriati di gestione strutturata delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="b29cf-112">File operations should be enclosed within appropriate structured exception handling blocks.</span></span>

 <span data-ttu-id="b29cf-113">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="b29cf-113">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="b29cf-114">Il nome del percorso non è valido.</span><span class="sxs-lookup"><span data-stu-id="b29cf-114">The path name is malformed.</span></span> <span data-ttu-id="b29cf-115">Ad esempio, contiene caratteri non validi o è costituito solo da spazi (classe <xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="b29cf-115">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span>

- <span data-ttu-id="b29cf-116">Il percorso è di sola lettura (classe <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="b29cf-116">The path is read-only (<xref:System.IO.IOException> class).</span></span>

- <span data-ttu-id="b29cf-117">Il nome del percorso è `null` (classe <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="b29cf-117">The path name is `null` (<xref:System.ArgumentNullException> class).</span></span>

- <span data-ttu-id="b29cf-118">Il nome del percorso è troppo lungo (classe <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="b29cf-118">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>

- <span data-ttu-id="b29cf-119">Il percorso non è valido (classe <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="b29cf-119">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>

- <span data-ttu-id="b29cf-120">Il percorso è costituito solo dai due punti, ":" ( <xref:System.NotSupportedException> classe).</span><span class="sxs-lookup"><span data-stu-id="b29cf-120">The path is only a colon, ":" (<xref:System.NotSupportedException> class).</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="b29cf-121">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b29cf-121">.NET Framework Security</span></span>
 <span data-ttu-id="b29cf-122">Non basarsi sul nome del file per prendere decisioni in merito al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="b29cf-122">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="b29cf-123">È possibile ad esempio che il file `Form1.vb` non sia un file di origine di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b29cf-123">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="b29cf-124">Prima di usare i dati nell'applicazione verificare tutti gli input.</span><span class="sxs-lookup"><span data-stu-id="b29cf-124">Verify all inputs before using the data in your application.</span></span>

## <a name="see-also"></a><span data-ttu-id="b29cf-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b29cf-125">See also</span></span>

- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="b29cf-126">Procedura: Caricare in modo asincrono un suono in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="b29cf-126">How to: Load a Sound Asynchronously within a Windows Form</span></span>](how-to-load-a-sound-asynchronously-within-a-windows-form.md)
