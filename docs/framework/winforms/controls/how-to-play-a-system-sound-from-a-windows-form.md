---
title: 'Procedura: Riprodurre un suono del sistema da un Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing for system events
- playing sounds [Windows Forms], Windows Forms
- system sounds [Windows Forms], playing from Windows Forms
- playing sounds [Windows Forms], system
- SoundPlayer class [Windows Forms], system sounds
- sounds [Windows Forms], playing
- examples [Windows Forms], sounds
ms.assetid: afb206ff-4824-4804-a8d4-185bf5ad8e7c
ms.openlocfilehash: d85d8cd40ff2b32cb3f2a79cf9a8221964f186c0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153231"
---
# <a name="how-to-play-a-system-sound-from-a-windows-form"></a>Procedura: Riprodurre un suono del sistema da un Windows Form
Nell'esempio di codice seguente viene riprodotto il suono del sistema `Exclamation` in fase di esecuzione. Per altre informazioni sui suoni del sistema, vedere <xref:System.Media.SystemSounds>.  
  
## <a name="example"></a>Esempio  
  
```vb  
Public Sub PlayExclamation()  
    SystemSounds.Exclamation.Play()  
End Sub  
```  
  
```csharp  
public void playExclamation()  
{  
    SystemSounds.Exclamation.Play();  
}  
```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un riferimento allo spazio dei nomi <xref:System.Media?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
- [Procedura: Riprodurre un segnale acustico da un Windows Form](how-to-play-a-beep-from-a-windows-form.md)
- [Procedura: Riprodurre un suono da un Windows Form](how-to-play-a-sound-from-a-windows-form.md)
