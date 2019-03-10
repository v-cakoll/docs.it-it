---
title: Anti-aliasing con linee e curve
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
ms.openlocfilehash: 6ea49c591b43d3f70bfd39058fd5ee256c537ec2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725012"
---
# <a name="antialiasing-with-lines-and-curves"></a>Anti-aliasing con linee e curve
Quando si usa [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] per disegnare una linea, si forniscono i punti iniziale e finale della linea, ma non è necessario fornire informazioni sui singoli pixel nella riga. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funziona in combinazione con il software dei driver di visualizzazione per determinare i pixel che verranno attivati per visualizzare la linea in un dispositivo di visualizzazione particolare.  
  
## <a name="aliasing"></a>Aliasing  
 Prendere in considerazione la linea rossa direttamente che va da punti (4, 2) per il punto (16, 10). Si supponga il sistema di coordinate è la sua origine nell'angolo superiore sinistro e che l'unità di misura è il pixel. Si supponga anche che l'asse x punta a destra e i punti di asse y verso il basso. Nella figura seguente mostra una visualizzazione ingrandita della riga di colore rosso disegnata su uno sfondo.  
  
 ![Linea, senza antialiasing](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")  
  
 I pixel rosso usati per il rendering della linea sono opachi. Non esistono Nessun pixel parzialmente trasparente nella riga. Questo tipo di rendering fornisce la riga di un aspetto frastagliato, mentre la linea assomiglia scale. Questa tecnica di che rappresenta una riga con una scala è chiamata alias; la scala è un alias di linea teorica.  
  
## <a name="antialiasing"></a>anti-aliasing  
 Una tecnica più sofisticata per il rendering di una riga comporta l'utilizzo di pixel parzialmente trasparente insieme ai pixel opaco. Pixel sono impostati su rosso puro, o a una fusione del red team e il colore di sfondo, a seconda di quanto si avvicina sono per la riga. Questo tipo di rendering viene chiamato anti-aliasing e risultati in una riga che viene percepita come più uniforme. La figura seguente mostra come fusione di alcuni pixel con sfondo per produrre una linea con anti-aliasing.  
  
 ![Antialiasing di una linea](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")  
  
 Anti-aliasing, detto anche anti-aliasing, può essere applicato anche alle curve. Nella figura seguente mostra una visualizzazione ingrandita di un'ellisse equalizzata.  
  
 ![Antialiasing di curve](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")  
  
 Nella figura seguente viene mostrata la stessa ellisse dimensioni effettive, una volta senza anti-aliasing e una volta con anti-aliasing.  
  
 ![Esempio di antialiasing](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")  
  
 Per tracciare linee e curve che utilizzano l'anti-aliasing, creare un'istanza del <xref:System.Drawing.Graphics> classe e impostare relativi <xref:System.Drawing.Graphics.SmoothingMode%2A> proprietà <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> o <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>. Quindi chiamare uno dei metodi di disegno che stesso <xref:System.Drawing.Graphics> classe.  
  
 [!code-csharp[LinesCurvesAndShapes#81](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Procedura: Usare l'antialiasing nel testo](how-to-use-antialiasing-with-text.md)
