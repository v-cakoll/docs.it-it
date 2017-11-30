---
title: 'Procedura: Riprodurre un suono da un Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3ed5335108e010ed61d8a96e3169353133e9ddd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-play-a-sound-from-a-windows-form"></a>Procedura: Riprodurre un suono da un Windows Form
In questo esempio viene riprodotto un suono in un percorso specificato in fase di esecuzione.  
  
## <a name="example"></a>Esempio  
  
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
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Sostituzione del nome del file `"c:\Windows\Media\chimes.wav"` con un nome file valido.  
  
-   (C#) Un riferimento di <xref:System.Media?displayProperty=nameWithType> dello spazio dei nomi.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le operazioni sui file devono essere racchiuse tra blocchi appropriati di gestione strutturata delle eccezioni.  
  
 Le seguenti condizioni possono generare un'eccezione:  
  
-   Il nome del percorso non è valido. Ad esempio, contiene caratteri non validi o è costituito solo da spazi (classe <xref:System.ArgumentException>).  
  
-   Il percorso è di sola lettura (classe <xref:System.IO.IOException>).  
  
-   Il nome del percorso è `null` (classe <xref:System.ArgumentNullException>).  
  
-   Il nome del percorso è troppo lungo (classe <xref:System.IO.PathTooLongException>).  
  
-   Il percorso non è valido (classe <xref:System.IO.DirectoryNotFoundException>).  
  
-   Il percorso contiene solo due punti, ":" (<xref:System.NotSupportedException> classe).  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Non basarsi sul nome del file per prendere decisioni in merito al relativo contenuto. È possibile ad esempio che il file `Form1.vb` non sia un file di origine di Visual Basic. Prima di usare i dati nell'applicazione verificare tutti gli input.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Media.SoundPlayer>  
 [Procedura: Caricare in modo asincrono un suono in un Windows Form](../../../../docs/framework/winforms/controls/how-to-load-a-sound-asynchronously-within-a-windows-form.md)  
 
