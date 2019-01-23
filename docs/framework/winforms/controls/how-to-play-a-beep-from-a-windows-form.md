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
ms.openlocfilehash: b847f2f759667eed5dfb6f9168a5c2fc50909cc3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544510"
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
>  Il suono riprodotto nel C# esempio di codice è determinato dal <xref:System.Media.SystemSounds.Beep%2A> impostazione del suono del sistema. Per altre informazioni, vedere <xref:System.Media.SystemSounds>.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per C#, in questo esempio richiede un riferimento per la <xref:System.Media?displayProperty=nameWithType> dello spazio dei nomi.  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [Procedura: Riprodurre un suono del sistema da un Windows Form](../../../../docs/framework/winforms/controls/how-to-play-a-system-sound-from-a-windows-form.md)
- [Procedura: Riprodurre un suono da un Windows Form](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
