---
title: "Procedura: Estrarre l'icona associata a un file in Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: d754dc5e8a57b3c4e2e5439bb2524a22d44813c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004042"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a>Procedura: Estrarre l'icona associata a un file in Windows Form
Numero di file è incorporati icone che forniscono una rappresentazione visiva del tipo di file associato. Documenti di Microsoft Word, ad esempio, contengono un'icona che li identifica come documenti di Word. Quando si visualizzano i file in un controllo di elenco o tabella, è possibile visualizzare l'icona che rappresenta il tipo di file accanto a ogni nome di file. È possibile farlo facilmente usando le <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> (metodo).  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come estrarre l'icona associata a un file e visualizzare il nome del file e l'icona associata in un <xref:System.Windows.Forms.ListView> controllo.  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare l'esempio:  
  
- Incollare il codice precedente in un Windows Form e chiamare il `ExtractAssociatedIconExample` metodo dal costruttore del form o <xref:System.Windows.Forms.Form.Load> metodo di gestione degli eventi.  
  
     È necessario assicurarsi che il modulo Importa la <xref:System.IO> dello spazio dei nomi.  
  
## <a name="see-also"></a>Vedere anche

- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
- [Controllo ListView](../controls/listview-control-windows-forms.md)
