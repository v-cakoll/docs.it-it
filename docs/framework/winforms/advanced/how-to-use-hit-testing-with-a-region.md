---
title: 'Procedura: eseguire l''hit testing utilizzando una regione'
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
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: adc55d137a5578dbe8649afa02ab8525d4913cd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-hit-testing-with-a-region"></a>Procedura: eseguire l'hit testing utilizzando una regione
Lo scopo del processo di hit testing consiste nel determinare se il cursore è posizionato su un oggetto specificato, ad esempio un'icona o di un pulsante.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea un'area a forma di segno più per l'unione di due aree rettangolari. Si supponga che la variabile `point` contenga la posizione di clic più recente. Il codice verifica se `point` nell'area a forma di segno più. Se il punto nell'area (un riscontro), l'area viene riempita con colore rosso opaco. In caso contrario, l'area viene riempita con rosso semitrasparente.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Region>  
 [Regioni in GDI+](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)  
 [Procedura: Definire l'area di visualizzazione usando una regione](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)
