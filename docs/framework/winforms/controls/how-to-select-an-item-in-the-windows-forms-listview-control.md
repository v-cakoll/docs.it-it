---
title: 'Procedura: Selezionare un elemento nel controllo ListView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
ms.openlocfilehash: b3cfcc6c2873dfb0eb95cf7950adc6b2bb73e74c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143182"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a>Procedura: Selezionare un elemento nel controllo ListView di Windows Forms
In questo esempio viene illustrato come selezionare a livello di programmazione un elemento in un form Windows <xref:System.Windows.Forms.ListView> controllo. Selezione di un elemento a livello di codice non cambia automaticamente lo stato attivo per il <xref:System.Windows.Forms.ListView> controllo. Per questo motivo, è anche in genere possibile impostare l'elemento come lo stato attivo quando si seleziona un elemento.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Oggetto <xref:System.Windows.Forms.ListView> controllo denominato `listView1` che contiene almeno un elemento.  
  
-   Riferimenti agli spazi dei nomi <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
