---
title: Importanza dell'ordine delle trasformazioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], order signficance
ms.assetid: 37d5f9dc-a5cf-4475-aa5d-34d714e808a9
ms.openlocfilehash: af8c1c243a29aa08863fb793c3ebffb91f2872b1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572305"
---
# <a name="why-transformation-order-is-significant"></a>Importanza dell'ordine delle trasformazioni
Un singolo <xref:System.Drawing.Drawing2D.Matrix> oggetti possono archiviare una trasformazione o una sequenza di trasformazioni. Quest'ultimo viene chiamato una trasformazione composita. La matrice di una trasformazione composita viene ottenuta moltiplicando le matrici delle trasformazioni singoli.  
  
## <a name="composite-transform-examples"></a>Esempi di trasformazione composita  
 In una trasformazione composita, è importante l'ordine delle trasformazioni singoli. Ad esempio, se si prima di tutto ruota, quindi scalare, traslare, si ottiene un risultato diverso che se innanzitutto traslare, ruotare, quindi ridimensionare. In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], trasformazioni composte vengono compilate da sinistra a destra. Se S, R e T sono rispettivamente le matrici di scala, rotazione e traslazione, quindi il prodotto SRT (in questo ordine) è basato sulla matrice di trasformazione composta con scalabilità prima, quindi Ruota, quindi si traduce. La matrice prodotta dal prodotto SRT è diverso dalla matrice prodotta dal prodotto TRS.  
  
 Uno dei motivi ordine è significativo è che le trasformazioni, ad esempio la rotazione e ridimensionamento vengono eseguite rispetto all'origine del sistema di coordinate. Ridimensionamento di un oggetto che viene centrato in corrispondenza dell'origine produce un risultato diverso rispetto al ridimensionamento di un oggetto che è stato spostato lontano dall'origine. Analogamente, la rotazione di un oggetto che viene centrato in corrispondenza dell'origine produce un risultato diverso da ruotare un oggetto che è stato spostato lontano dall'origine.  
  
 L'esempio seguente unisce il ridimensionamento, rotazione e traslazione (in questo ordine) per formare una trasformazione composita. L'argomento <xref:System.Drawing.Drawing2D.MatrixOrder.Append> passato per il <xref:System.Drawing.Graphics.RotateTransform%2A> metodo indica che la rotazione seguirà il ridimensionamento. Analogamente, l'argomento <xref:System.Drawing.Drawing2D.MatrixOrder.Append> passato per il <xref:System.Drawing.Graphics.TranslateTransform%2A> metodo indica che la traduzione seguirà la rotazione. <xref:System.Drawing.Drawing2D.MatrixOrder.Append> e <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend> appartengono le <xref:System.Drawing.Drawing2D.MatrixOrder> enumerazione.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#21)]  
  
 Nell'esempio seguente effettua le chiamate di metodo di stesso come illustrato nell'esempio precedente, ma l'ordine delle chiamate è invertito. L'ordine risultante di operazioni di traslazione, ruotare, scalabilità, che produce un risultato molto diverso dal primo scalabilità, quindi la rotazione, quindi convertire.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#22)]  
  
 Un modo per invertire l'ordine delle trasformazioni singoli in una trasformazione composita è per invertire l'ordine di una sequenza di chiamate al metodo. Un secondo modo per controllare l'ordine delle operazioni consiste nel modificare l'argomento order di matrice. L'esempio seguente è identico a quello precedente, con la differenza che <xref:System.Drawing.Drawing2D.MatrixOrder.Append> è stato modificato in <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend>. La moltiplicazione di matrici viene eseguita nell'ordine in SRT, dove S, R e T sono le matrici per la scalabilità, ruotare e tradurre, rispettivamente. L'ordine della trasformazione composito prima scala, rotazione, quindi convertire.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#23)]  
  
 Il risultato dell'esempio immediatamente precedente è lo stesso come il risultato del primo esempio in questo argomento. Questo avviene perché è stato invertito l'ordine delle chiamate di metodo sia l'ordine della moltiplicazione di matrici.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Drawing.Drawing2D.Matrix>
- [Sistemi di coordinate e trasformazioni](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)
- [Uso di trasformazioni nel codice gestito GDI+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
