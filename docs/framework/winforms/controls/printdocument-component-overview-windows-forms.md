---
title: Cenni preliminari sul componente PrintDocument (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: 16a7f3a34ccb280f7bf91c52e29b20edc22130b9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928981"
---
# <a name="printdocument-component-overview-windows-forms"></a>Cenni preliminari sul componente PrintDocument (Windows Form)

Il componente [PrintDocument](printdocument-component-windows-forms.md) di Windows Forms viene usato per impostare le proprietà che descrivono cosa stampare e per stampare quindi il documento nelle applicazioni basate su Windows. Può essere usato insieme al componente [PrintDialog](printdialog-component-windows-forms.md) per controllare tutti gli aspetti della stampa dei documenti.

## <a name="working-with-the-printdocument-component"></a>Utilizzo del componente PrintDocument

Due degli scenari principali che coinvolgono il <xref:System.Drawing.Printing.PrintDocument> componente sono:

- Processi di stampa semplici, come la stampa di un singolo file di testo. In tal caso, è necessario aggiungere il <xref:System.Drawing.Printing.PrintDocument> componente a un Windows Form, quindi aggiungere la logica di programmazione che stampa un file <xref:System.Drawing.Printing.PrintDocument.PrintPage> nel gestore eventi. La logica di programmazione deve culminare con <xref:System.Drawing.Printing.PrintDocument.Print%2A> il metodo per stampare il documento. Questo metodo invia alla <xref:System.Drawing.Graphics> stampante un oggetto, contenuto <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> nella proprietà della <xref:System.Drawing.Printing.PrintPageEventArgs> classe. Per un esempio in cui viene illustrato come stampare un documento di testo <xref:System.Drawing.Printing.PrintDocument> utilizzando il componente [, vedere Procedura: Stampare un file di testo con più pagine in](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)Windows Forms.

- Processi di stampa più complessi, come i casi in cui è necessario riutilizzare la logica di stampa creata. In tal caso, è necessario derivare un nuovo componente dal <xref:System.Drawing.Printing.PrintDocument> componente ed eseguire l'override (vedere [sostituzioni](../../../visual-basic/language-reference/modifiers/overrides.md) per Visual Basic C#o <xref:System.Drawing.Printing.PrintDocument.PrintPage> [override](../../../csharp/language-reference/keywords/override.md) per) l'evento.

Quando viene aggiunto a un modulo, il <xref:System.Drawing.Printing.PrintDocument> componente viene visualizzato nella barra delle applicazioni nella parte inferiore del progettazione Windows Form in Visual Studio.

## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [Supporto per la stampa in Windows Forms](../advanced/windows-forms-print-support.md)
- [PrintDocument (componente)](printdocument-component-windows-forms.md)
