---
title: "Procedura: Eseguire l'hit testing usando una regione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 136f15f1364fb2aed791b4a61d0f11411b055967
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150501"
---
# <a name="how-to-use-hit-testing-with-a-region"></a>Procedura: Eseguire l'hit testing usando una regione
Lo scopo dell'hit testing è determinare se il cursore si trova su un determinato oggetto, ad esempio un'icona o un pulsante.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea un'area a forma di segno più per formare l'unione di due aree rettangolari. Si supponga che la variabile `point` contiene la posizione di clic con il più recente. Il codice verifica se `point` nell'area a forma di segno più. Se il punto nell'area (hit), l'area viene riempita con un pennello opaco rosso. In caso contrario, l'area viene riempita con un pennello di colore rosso semitrasparente.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Region>
- [Regioni in GDI+](regions-in-gdi.md)
- [Procedura: Uso con un'area di ritaglio](how-to-use-clipping-with-a-region.md)
