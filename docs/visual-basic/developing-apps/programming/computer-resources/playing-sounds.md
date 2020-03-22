---
title: Riproduzione di suoni
ms.date: 07/20/2015
helpviewer_keywords:
- system sounds, playing
- system sounds
- playing sounds, Visual Basic
- sound loops
- My.Computer.Audio object, tasks
- sounds, playing
- sounds, background
- playing sounds
ms.assetid: f0d9e4ab-57c7-47b6-86d3-99ff07078040
ms.openlocfilehash: 416fedd011ff35d2b32d1b64932e3908a73ed14e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345518"
---
# <a name="playing-sounds-visual-basic"></a>Riproduzione di suoni (Visual Basic)

Il metodo `My.Computer.Audio` offre metodi per la riproduzione di suoni.  
  
## <a name="playing-sounds"></a>Riproduzione di suoni  

 La riproduzione in background consente all'applicazione di eseguire altro codice durante la riproduzione di suoni. Il metodo `My.Computer.Audio.Play` consente all'applicazione di riprodurre un solo suono di sottofondo alla volta: quando l'applicazione riproduce un nuovo suono di sottofondo, viene interrotta la riproduzione del suono di sottofondo precedente. È anche possibile riprodurre un suono e attendere il completamento della riproduzione.  
  
 Nell'esempio seguente il metodo `My.Computer.Audio.Play` riproduce un suono. Quando è specificato `AudioPlayMode.WaitToComplete`, `My.Computer.Audio.Play` attende il completamento del suono prima di continuare a chiamare codice. Quando si usa questo esempio è necessario assicurarsi che il nome file faccia riferimento a un file audio con estensione wav presente nel computer.  
  
 [!code-vb[VbVbalrMyComputer#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#15)]  
  
 Nell'esempio seguente il metodo `My.Computer.Audio.Play` riproduce un suono. Quando si usa questo esempio è necessario assicurarsi che le risorse dell'applicazione includano un file audio con estensione wav denominato Waterfall.  
  
 [!code-vb[VbVbalrMyComputer#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#16)]  
  
## <a name="playing-looping-sounds"></a>Riproduzione di file audio a ciclo continuo  

 Nell'esempio seguente il metodo `My.Computer.Audio.Play` riproduce il file audio specificato in background quando è specificato `PlayMode.BackgroundLoop`. Quando si usa questo esempio è necessario assicurarsi che il nome file faccia riferimento a un file audio con estensione wav presente nel computer.  
  
 [!code-vb[VbVbalrMyComputer#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#11)]  
  
 Nell'esempio seguente il metodo `My.Computer.Audio.Play` riproduce il file audio specificato in background quando è specificato `PlayMode.BackgroundLoop`. Quando si usa questo esempio è necessario assicurarsi che le risorse dell'applicazione includano un file audio con estensione wav denominato Waterfall.  
  
 [!code-vb[VbVbalrMyComputer#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#12)]  
  
 L'esempio di codice precedente è disponibile anche come frammento di codice IntelliSense. Nello strumento di selezione dei frammenti di codice il frammento di codice si trova in **Applicazioni Windows Form > Audio**. Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).  
  
 In generale, quando un'applicazione riproduce un file audio a ciclo continuo, la riproduzione dovrà prima o poi essere interrotta.  
  
## <a name="stopping-the-playing-of-sounds-in-the-background"></a>Interruzione della riproduzione di suoni in background  

 Usare il metodo `My.Computer.Audio.Stop` per interrompere la riproduzione di file audio in background o a ciclo continuo dell'applicazione.  
  
 In generale, quando un'applicazione riproduce un file audio a ciclo continuo, la riproduzione dovrà prima o poi essere interrotta.  
  
 L'esempio seguente interrompe la riproduzione di un file audio in background.  
  
 [!code-vb[VbVbalrMyComputer#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#18)]  
  
 L'esempio di codice precedente è disponibile anche come frammento di codice IntelliSense. Nello strumento di selezione dei frammenti di codice il frammento di codice si trova in **Applicazioni Windows Form > Audio**. Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).  
  
## <a name="playing-system-sounds"></a>Riproduzione di suoni di sistema  

 Usare il metodo `My.Computer.Audio.PlaySystemSound` per riprodurre il suono di sistema specificato.  
  
 Il metodo `My.Computer.Audio.PlaySystemSound` accetta come parametro uno dei membri condivisi della classe <xref:System.Media.SystemSound>. Il suono di sistema <xref:System.Media.SystemSounds.Asterisk%2A> indica in genere la presenza di errori.  
  
 L'esempio seguente usa il metodo `My.Computer.Audio.PlaySystemSound` per riprodurre un suono di sistema.  
  
 [!code-vb[VbVbalrMyComputer#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Devices.Audio>
- <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>
- <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>
- <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>
- <xref:Microsoft.VisualBasic.AudioPlayMode>
