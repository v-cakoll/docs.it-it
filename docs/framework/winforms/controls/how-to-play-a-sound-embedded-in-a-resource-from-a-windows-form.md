---
title: 'Procedura: Riprodurre un suono incorporato in una risorsa da un Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing from resources
- resources [Windows Forms], playing sounds
- playing sounds [Windows Forms], from resources
- SoundPlayer class [Windows Forms], playing sounds from resources
ms.assetid: 7d148bb6-8a1e-47d7-a08d-35828d2e688f
ms.openlocfilehash: 390f70acc99d8950a23ce514d90c79c3da765f2a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631334"
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a>Procedura: Riprodurre un suono incorporato in una risorsa da un Windows Form
È possibile usare il <xref:System.Media.SoundPlayer> classe per riprodurre un suono da una risorsa incorporata.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.Sound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
 L'importazione di <xref:System.Media?displayProperty=nameWithType> dello spazio dei nomi.  
  
 Inclusione del file audio come risorsa incorporata nel progetto.  
  
 Sostituzione di "\<AssemblyName>" con il nome dell'assembly in cui è incorporato il file audio. Non includere il suffisso ". dll".  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Media.SoundPlayer>
- [Procedura: Riprodurre un suono da un Windows Form](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
- [Procedura: Riprodurre un suono ripetutamente in un Windows Form](../../../../docs/framework/winforms/controls/how-to-loop-a-sound-playing-on-a-windows-form.md)
