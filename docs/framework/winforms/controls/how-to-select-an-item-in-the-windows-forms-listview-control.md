---
title: Seleziona un elemento nel controllo ListView
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
ms.openlocfilehash: 57e985af9d0347510d7d7782f68d5b414d36e077
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743226"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a>Procedura: selezionare un elemento nel controllo ListView Windows Form
In questo esempio viene illustrato come selezionare a livello di codice un elemento in un controllo Windows Forms <xref:System.Windows.Forms.ListView>. La selezione di un elemento a livello di codice non modifica automaticamente lo stato attivo sul controllo <xref:System.Windows.Forms.ListView>. Per questo motivo, in genere è necessario impostare l'elemento come attivo quando si seleziona un elemento.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Controllo <xref:System.Windows.Forms.ListView> denominato `listView1` che contiene almeno un elemento.  
  
- Riferimenti agli spazi dei nomi <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
