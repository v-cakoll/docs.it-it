---
title: Utilizzo di un pennello a sfumatura per il riempimento di forme
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 5771aaabd283d71f5fa6934f86a1c24a57f38dca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954468"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a>Utilizzo di un pennello a sfumatura per il riempimento di forme
È possibile usare un pennello a sfumatura per riempire una forma con un colore gradualmente. Ad esempio, è possibile utilizzare una sfumatura orizzontale per riempire una forma con il colore che cambia gradualmente quando si spostano tra il bordo sinistro della forma per il bordo destro. Si immagini un rettangolo con un bordo nero (rappresentato da componenti rosso, verde e blu 0, 0, 0) e un diritto ovvero bordo rosso (rappresentato da 255, 0, 0). Se il rettangolo è 256 pixel in larghezza, il componente rosso di un pixel specifico sarà una maggiore del componente rosso del pixel alla sua sinistra. Il pixel più a sinistra in una riga ha componenti di colore (0, 0, 0), il secondo pixel ha (1, 0, 0), il terzo pixel (2, 0, 0) e così via, fino ad arrivare al pixel più a destra, che include componenti di colore (255, 0, 0). Questi valori di colore interpolata costituiscono la sfumatura di colore.  
  
 Una sfumatura lineare cambia colore quando si sposta orizzontalmente, verticalmente o in parallelo per una riga obliqua specificata. Una sfumatura percorso cambia colore quando si sposta sulla parte interna e limiti di un percorso. È possibile personalizzare le sfumature di percorso per ottenere un'ampia gamma di effetti.  
  
 La figura seguente mostra un rettangolo riempito con un pennello sfumato lineare e un'ellisse riempito con un pennello a sfumatura.  
  
 ![Sfumatura](./media/gradient2.png "gradient2")  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Creare una sfumatura lineare](how-to-create-a-linear-gradient.md)  
 Viene illustrato come creare una sfumatura lineare utilizzando il <xref:System.Drawing.Drawing2D.LinearGradientBrush> classe.  
  
 [Procedura: Creare una sfumatura percorso](how-to-create-a-path-gradient.md)  
 Viene descritto come creare una sfumatura di percorso utilizzando il <xref:System.Drawing.Drawing2D.PathGradientBrush> classe.  
  
 [Procedura: Applicare la correzione Gamma a una sfumatura](how-to-apply-gamma-correction-to-a-gradient.md)  
 Viene illustrato come utilizzare la correzione gamma con un pennello sfumato.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 Contiene una descrizione di questa classe e include collegamenti a tutti i relativi membri.  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 Contiene una descrizione di questa classe e include collegamenti a tutti i relativi membri.
