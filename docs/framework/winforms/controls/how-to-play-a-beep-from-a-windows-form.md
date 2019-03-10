---
title: 'Procedura: Riprodurre un segnale acustico da un Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], beep
- Windows Forms, sounds
- sounds [Windows Forms], playing
- forms [Windows Forms], sounds
- examples [Windows Forms], sounds
ms.assetid: 7ea5cded-4888-4f35-8f28-5cab1a55c973
ms.openlocfilehash: d04bf4bd45aa6ba5dfe231d5f69c2b2a13765373
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710433"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a><span data-ttu-id="4c5cf-102">Procedura: Riprodurre un segnale acustico da un Windows Form</span><span class="sxs-lookup"><span data-stu-id="4c5cf-102">How to: Play a Beep from a Windows Form</span></span>
<span data-ttu-id="4c5cf-103">In questo esempio viene riprodotto un segnale acustico in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4c5cf-103">This example plays a beep at run time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c5cf-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c5cf-104">Example</span></span>  
  
```vb  
Public Sub OnePing()  
    Beep()  
End Sub  
```  
  
```csharp  
public void onePing()  
{  
    SystemSounds.Beep.Play();  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="4c5cf-105">Il suono riprodotto nel C# esempio di codice è determinato dal <xref:System.Media.SystemSounds.Beep%2A> impostazione del suono del sistema.</span><span class="sxs-lookup"><span data-stu-id="4c5cf-105">The sound played in the C# code sample is determined by the <xref:System.Media.SystemSounds.Beep%2A> system sound setting.</span></span> <span data-ttu-id="4c5cf-106">Per altre informazioni, vedere <xref:System.Media.SystemSounds>.</span><span class="sxs-lookup"><span data-stu-id="4c5cf-106">For more information, see <xref:System.Media.SystemSounds>.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4c5cf-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4c5cf-107">Compiling the Code</span></span>  
 <span data-ttu-id="4c5cf-108">Per C#, in questo esempio richiede un riferimento per la <xref:System.Media?displayProperty=nameWithType> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="4c5cf-108">For C#, this example requires  a reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c5cf-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c5cf-109">See also</span></span>
- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="4c5cf-110">Procedura: Riprodurre un suono del sistema da un Windows Form</span><span class="sxs-lookup"><span data-stu-id="4c5cf-110">How to: Play a System Sound from a Windows Form</span></span>](how-to-play-a-system-sound-from-a-windows-form.md)
- [<span data-ttu-id="4c5cf-111">Procedura: Riprodurre un suono da un Windows Form</span><span class="sxs-lookup"><span data-stu-id="4c5cf-111">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
