---
title: 'Procedura: Emettere un segnale acustico da un Windows Form'
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
ms.openlocfilehash: 1a72f88c05fb21c11864058ffbe81c1957525375
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966515"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a>Procedura: Emettere un segnale acustico da un Windows Form
In questo esempio viene riprodotto un segnale acustico in fase di esecuzione.  
  
## <a name="example"></a>Esempio  
  
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
> Il suono riprodotto nell' C# esempio di codice è determinato dall' <xref:System.Media.SystemSounds.Beep%2A> impostazione del suono del sistema. Per altre informazioni, vedere <xref:System.Media.SystemSounds>.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per C#, questo esempio richiede un riferimento allo <xref:System.Media?displayProperty=nameWithType> spazio dei nomi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [Procedura: Riprodurre un suono di sistema da un Windows Form](how-to-play-a-system-sound-from-a-windows-form.md)
- [Procedura: Riprodurre un suono da un Windows Form](how-to-play-a-sound-from-a-windows-form.md)
