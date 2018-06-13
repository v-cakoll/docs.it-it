---
title: Importanza dell'ordine delle trasformazioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], order signficance
ms.assetid: 37d5f9dc-a5cf-4475-aa5d-34d714e808a9
ms.openlocfilehash: 943bfa73b54a1ac5d68d21d2bb6e271133db595a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526077"
---
# <a name="why-transformation-order-is-significant"></a>Importanza dell'ordine delle trasformazioni
Un singolo <xref:System.Drawing.Drawing2D.Matrix> oggetto è possibile archiviare una singola trasformazione o una sequenza di trasformazioni. Quest'ultimo viene chiamato una trasformazione composta. La matrice di una trasformazione composta viene ottenuta moltiplicando le matrici delle trasformazioni singoli.  
  
## <a name="composite-transform-examples"></a>Esempi di trasformazione composita  
 In una trasformazione composta, è importante l'ordine delle trasformazioni singoli. Ad esempio, se innanzitutto ruotare, ridimensionare e quindi convertire, si ottiene un risultato diverso che se prima si traduce, ruotare e quindi applicare la scalabilità. In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], trasformazioni composte sono compilate da sinistra a destra. Se S e R, T sono rispettivamente a matrici di scala, rotazione e conversione, quindi il prodotto SRT (in tale ordine) è la matrice di trasformazione composta tale scale prima, quindi Ruota, quindi viene convertito. La matrice prodotta dalla SRT è diverso dalla matrice prodotta dalla sequenza trs.  
  
 Uno dei motivi ordine è significativo è che le trasformazioni come rotazione e la scalabilità vengono effettuate rispetto all'origine del sistema di coordinate. Ridimensionamento di un oggetto che viene centrato all'origine produce un risultato diverso dal ridimensionamento di un oggetto che è stato spostato rispetto all'origine. Analogamente, la rotazione di un oggetto che viene centrato all'origine produce un risultato diverso da ruotare un oggetto che è stato spostato rispetto all'origine.  
  
 L'esempio seguente unisce il ridimensionamento, rotazione e conversione (in tale ordine) per formare una trasformazione composta. L'argomento <xref:System.Drawing.Drawing2D.MatrixOrder.Append> passato per il <xref:System.Drawing.Graphics.RotateTransform%2A> metodo indica che la rotazione seguirà il ridimensionamento. Analogamente, l'argomento <xref:System.Drawing.Drawing2D.MatrixOrder.Append> passato per il <xref:System.Drawing.Graphics.TranslateTransform%2A> metodo indica che la traduzione seguirà la rotazione. <xref:System.Drawing.Drawing2D.MatrixOrder.Append> e <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend> sono membri del <xref:System.Drawing.Drawing2D.MatrixOrder> enumerazione.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#21)]  
  
 Nell'esempio seguente effettua le chiamate di metodo stesso dell'esempio precedente, ma l'ordine delle chiamate è invertito. L'ordine delle operazioni è traslazione, rotazione e quindi scala che produce un risultato molto diverso rispetto a prima, quindi ruotare e quindi convertire.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#22)]  
  
 Un modo per invertire l'ordine delle singole trasformazioni in una trasformazione composita è per invertire l'ordine di una sequenza di chiamate al metodo. Un secondo modo per controllare l'ordine delle operazioni consiste nel modificare l'argomento order di matrice. Nell'esempio seguente è uguale all'esempio precedente, con la differenza che <xref:System.Drawing.Drawing2D.MatrixOrder.Append> è stato modificato in <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend>. La moltiplicazione viene eseguita nell'ordine SRT, dove T S e R sono le matrici di scala, rotazione e tradurre, rispettivamente. L'ordine della trasformazione composita prima scala, rotazione e quindi convertire.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#23)]  
  
 Il risultato dell'esempio precedente è lo stesso come il risultato del primo esempio in questo argomento. Questo avviene perché è stato invertito l'ordine delle chiamate di metodo sia l'ordine della moltiplicazione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Drawing2D.Matrix>  
 [Sistemi di coordinate e trasformazioni](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [Uso di trasformazioni nel codice gestito GDI+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
