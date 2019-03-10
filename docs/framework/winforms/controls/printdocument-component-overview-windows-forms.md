---
title: Cenni preliminari sul componente PrintDocument (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: c35c60b651dd3becfeca0f07788efab9d1619117
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715863"
---
# <a name="printdocument-component-overview-windows-forms"></a>Cenni preliminari sul componente PrintDocument (Windows Form)
Il componente [PrintDocument](printdocument-component-windows-forms.md) di Windows Forms viene usato per impostare le proprietà che descrivono cosa stampare e per stampare quindi il documento nelle applicazioni basate su Windows. Può essere usato insieme al componente [PrintDialog](printdialog-component-windows-forms.md) per controllare tutti gli aspetti della stampa dei documenti.  
  
## <a name="working-with-the-printdocument-component"></a>Utilizzo del componente PrintDocument  
 Due dei principali scenari che coinvolgono il <xref:System.Drawing.Printing.PrintDocument> componente sono:  
  
-   Processi di stampa semplici, come la stampa di un singolo file di testo. In questo caso si aggiungerà il <xref:System.Drawing.Printing.PrintDocument> componente a un modulo di Windows, quindi aggiungere la logica di programmazione che consente di stampare un file nei <xref:System.Drawing.Printing.PrintDocument.PrintPage> gestore dell'evento. La logica di programmazione deve culminare con il <xref:System.Drawing.Printing.PrintDocument.Print%2A> metodo per stampare il documento. Questo metodo invia un <xref:System.Drawing.Graphics> oggetto, incluso nel <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> proprietà del <xref:System.Drawing.Printing.PrintPageEventArgs> (classe), alla stampante. Per un esempio che illustra come stampare un documento di testo usando il <xref:System.Drawing.Printing.PrintDocument> componente, vedere [come: Stampare un File di testo con più pagine in Windows Form](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).  
  
-   Processi di stampa più complessi, come i casi in cui è necessario riutilizzare la logica di stampa creata. In tal caso derivare un nuovo componente dal <xref:System.Drawing.Printing.PrintDocument> componente ed eseguire l'override (vedere [esegue l'override](~/docs/visual-basic/language-reference/modifiers/overrides.md) per Visual Basic o [override](~/docs/csharp/language-reference/keywords/override.md) per C#) il <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento.  
  
 Quando viene aggiunto a un modulo, il <xref:System.Drawing.Printing.PrintDocument> componente è visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [Supporto per la stampa in Windows Forms](../advanced/windows-forms-print-support.md)
- [PrintDocument (componente)](printdocument-component-windows-forms.md)
