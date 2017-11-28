---
title: 'Procedura: selezionare un elemento nel controllo ListView Windows Form'
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
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e7acbda541000655ff96b70a2188169b7e8ccd9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a>Procedura: selezionare un elemento nel controllo ListView Windows Form
In questo esempio viene illustrato come selezionare a livello di programmazione un elemento in un Windows Form <xref:System.Windows.Forms.ListView> controllo. Selezione di un elemento a livello di codice non cambia automaticamente lo stato attivo per il <xref:System.Windows.Forms.ListView> controllo. Per questo motivo, si sarà in genere consigliabile impostare l'elemento, come lo stato attivo quando si seleziona un elemento.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Oggetto <xref:System.Windows.Forms.ListView> controllo denominato `listView1` che contiene almeno un elemento.  
  
-   Riferimenti agli spazi dei nomi <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
