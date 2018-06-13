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
ms.openlocfilehash: 460309d853f2b3b423d14a820771e0230358e3c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531222"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a>Procedura: Riprodurre un segnale acustico da un Windows Form
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
>  Il suono riprodotto nell'esempio di codice c# è determinato dal <xref:System.Media.SystemSounds.Beep%2A> suoni di sistema. Per altre informazioni, vedere <xref:System.Media.SystemSounds>.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per c#, in questo esempio richiede un riferimento al <xref:System.Media?displayProperty=nameWithType> dello spazio dei nomi.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Interaction.Beep%2A>  
 <xref:System.Media.SoundPlayer>  
 [Procedura: Riprodurre un suono del sistema da un Windows Form](../../../../docs/framework/winforms/controls/how-to-play-a-system-sound-from-a-windows-form.md)  
 [Procedura: Riprodurre un suono da un Windows Form](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
