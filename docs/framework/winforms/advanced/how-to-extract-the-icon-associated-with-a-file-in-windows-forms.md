---
title: 'Procedura: estrarre l''icona associata a un file in Windows Form'
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
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a5153f6389c4477a18c647d7cdaf7b49b43bb7ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a>Procedura: estrarre l'icona associata a un file in Windows Form
Numero di file è incorporati icone che forniscono una rappresentazione visiva del tipo di file associato. Ad esempio, documenti di Microsoft Word contengono un'icona che li identifica come documenti di Word. Quando si visualizzano i file in un controllo elenco o tabella, si desidera visualizzare l'icona che rappresenta il tipo di file accanto a ogni nome di file. È possibile farlo facilmente tramite il <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> metodo.  
  
## <a name="example"></a>Esempio  
 Esempio di codice riportato di seguito viene illustrato come estrarre l'icona associata a un file e visualizzare il nome del file e l'icona associata in un <xref:System.Windows.Forms.ListView> controllo.  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare l'esempio:  
  
-   Incollare il codice precedente in un Windows Form e chiamare il `ExtractAssociatedIconExample` metodo dal costruttore del form o <xref:System.Windows.Forms.Form.Load> il metodo di gestione degli eventi.  
  
     È necessario assicurarsi che il modulo Importa il <xref:System.IO> dello spazio dei nomi.  
  
## <a name="see-also"></a>Vedere anche  
 [Immagini, bitmap e metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Controllo ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
