---
title: "Procedura: estrarre l'icona associata a un file"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: 28769144b0e1c631a31c3c541747a6215f861d0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742548"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a>Procedura: estrarre l'icona associata a un file in Windows Form
Molti file hanno icone incorporate che forniscono una rappresentazione visiva del tipo di file associato. Ad esempio, i documenti di Microsoft Word contengono un'icona che li identifica come documenti di Word. Quando si visualizzano i file in un controllo elenco o in un controllo tabella, potrebbe essere necessario visualizzare l'icona che rappresenta il tipo di file accanto a ogni nome file. Questa operazione può essere eseguita facilmente usando il metodo <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice riportato di seguito viene illustrato come estrarre l'icona associata a un file e visualizzare il nome del file e l'icona associata in un controllo <xref:System.Windows.Forms.ListView>.  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare l'esempio:  
  
- Incollare il codice precedente in un Windows Form e chiamare il metodo `ExtractAssociatedIconExample` dal costruttore del form o <xref:System.Windows.Forms.Form.Load> metodo di gestione degli eventi.  
  
     Sarà necessario assicurarsi che il form importi lo spazio dei nomi <xref:System.IO>.  
  
## <a name="see-also"></a>Vedere anche

- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
- [Controllo ListView](../controls/listview-control-windows-forms.md)
