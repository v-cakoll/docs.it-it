---
title: 'Procedura: Riprodurre un suono da un Windows Form'
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
ms.openlocfilehash: 3b9eb6f902d0d2193f0099f8e868e4ead347ce26
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078681"
---
# <a name="how-to-play-a-sound-from-a-windows-form"></a><span data-ttu-id="0b695-102">Procedura: Riprodurre un suono da un Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b695-102">How to: Play a Sound from a Windows Form</span></span>
<span data-ttu-id="0b695-103">In questo esempio viene riprodotto un suono in un percorso specificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0b695-103">This example plays a sound at a given path at run time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b695-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b695-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="0b695-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="0b695-105">Compiling the Code</span></span>  
 <span data-ttu-id="0b695-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b695-106">This example requires:</span></span>  
  
-   <span data-ttu-id="0b695-107">Sostituzione del nome del file `"c:\Windows\Media\chimes.wav"` con un nome file valido.</span><span class="sxs-lookup"><span data-stu-id="0b695-107">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>  
  
-   <span data-ttu-id="0b695-108">(C#) Un riferimento per la <xref:System.Media?displayProperty=nameWithType> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="0b695-108">(C#) A reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0b695-109">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="0b695-109">Robust Programming</span></span>  
 <span data-ttu-id="0b695-110">Le operazioni sui file devono essere racchiuse tra blocchi appropriati di gestione strutturata delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="0b695-110">File operations should be enclosed within appropriate structured exception handling blocks.</span></span>  
  
 <span data-ttu-id="0b695-111">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="0b695-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="0b695-112">Il nome del percorso non è valido.</span><span class="sxs-lookup"><span data-stu-id="0b695-112">The path name is malformed.</span></span> <span data-ttu-id="0b695-113">Ad esempio, contiene caratteri non validi o è costituito solo da spazi (classe <xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="0b695-113">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="0b695-114">Il percorso è di sola lettura (classe <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="0b695-114">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="0b695-115">Il nome del percorso è `null` (classe <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="0b695-115">The path name is `null` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="0b695-116">Il nome del percorso è troppo lungo (classe <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="0b695-116">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="0b695-117">Il percorso non è valido (classe <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="0b695-117">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="0b695-118">Il percorso contiene solo due punti, ":" (<xref:System.NotSupportedException> classe).</span><span class="sxs-lookup"><span data-stu-id="0b695-118">The path is only a colon, ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="0b695-119">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0b695-119">.NET Framework Security</span></span>  
 <span data-ttu-id="0b695-120">Non basarsi sul nome del file per prendere decisioni in merito al relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="0b695-120">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="0b695-121">È possibile ad esempio che il file `Form1.vb` non sia un file di origine di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0b695-121">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="0b695-122">Prima di usare i dati nell'applicazione verificare tutti gli input.</span><span class="sxs-lookup"><span data-stu-id="0b695-122">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b695-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b695-123">See also</span></span>

- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="0b695-124">Procedura: Caricare in modo asincrono un suono in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="0b695-124">How to: Load a Sound Asynchronously within a Windows Form</span></span>](how-to-load-a-sound-asynchronously-within-a-windows-form.md)
