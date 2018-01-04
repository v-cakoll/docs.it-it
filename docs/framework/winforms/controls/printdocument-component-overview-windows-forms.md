---
title: Cenni preliminari sul componente PrintDocument (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 414a7972550558b40403b7f4cbfd9a49194666be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="printdocument-component-overview-windows-forms"></a>Cenni preliminari sul componente PrintDocument (Windows Form)
Il componente [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) di Windows Forms viene usato per impostare le proprietà che descrivono cosa stampare e per stampare quindi il documento nelle applicazioni basate su Windows. Può essere usato insieme al componente [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) per controllare tutti gli aspetti della stampa dei documenti.  
  
## <a name="working-with-the-printdocument-component"></a>Utilizzo del componente PrintDocument  
 Due dei principali scenari che comportano la <xref:System.Drawing.Printing.PrintDocument> componente sono:  
  
-   Processi di stampa semplici, come la stampa di un singolo file di testo. In questo caso si aggiunge il <xref:System.Drawing.Printing.PrintDocument> componente a un Windows Form, quindi aggiungere la logica di programmazione che consente di stampare un file nel <xref:System.Drawing.Printing.PrintDocument.PrintPage> gestore dell'evento. La logica di programmazione dovrebbe culminare con il <xref:System.Drawing.Printing.PrintDocument.Print%2A> metodo per stampare il documento. Questo metodo invia un <xref:System.Drawing.Graphics> oggetto, contenuto nella <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> proprietà del <xref:System.Drawing.Printing.PrintPageEventArgs> (classe), alla stampante. Per un esempio che illustra come stampare un documento di testo utilizzando il <xref:System.Drawing.Printing.PrintDocument> componente, vedere [procedura: stampare un File di testo a più pagine in Windows Form](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).  
  
-   Processi di stampa più complessi, come i casi in cui è necessario riutilizzare la logica di stampa creata. In questo caso derivare un nuovo componente dal <xref:System.Drawing.Printing.PrintDocument> componente ed eseguire l'override (vedere [esegue l'override](~/docs/visual-basic/language-reference/modifiers/overrides.md) per Visual Basic o [override](~/docs/csharp/language-reference/keywords/override.md) per c#) di <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento.  
  
 Quando viene aggiunto a un modulo, il <xref:System.Drawing.Printing.PrintDocument> componente viene visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Printing.PrintDocument>  
 [Supporto per la stampa in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [PrintDocument (componente)](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)
