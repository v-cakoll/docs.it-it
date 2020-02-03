---
title: Cenni preliminari sul componente PrintDocument
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: a82cc0cdcb8cfae796c9c6bf60ab73873f85a291
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728546"
---
# <a name="printdocument-component-overview-windows-forms"></a>Cenni preliminari sul componente PrintDocument (Windows Form)

Il componente [PrintDocument](printdocument-component-windows-forms.md) di Windows Forms viene usato per impostare le proprietà che descrivono cosa stampare e per stampare quindi il documento nelle applicazioni basate su Windows. Può essere usato insieme al componente [PrintDialog](printdialog-component-windows-forms.md) per controllare tutti gli aspetti della stampa dei documenti.

## <a name="working-with-the-printdocument-component"></a>Utilizzo del componente PrintDocument

Due degli scenari principali che coinvolgono il componente <xref:System.Drawing.Printing.PrintDocument> sono:

- Processi di stampa semplici, come la stampa di un singolo file di testo. In tal caso, è necessario aggiungere il componente <xref:System.Drawing.Printing.PrintDocument> a un Windows Form, quindi aggiungere la logica di programmazione che stampa un file nel gestore dell'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>. La logica di programmazione deve culminare con il metodo <xref:System.Drawing.Printing.PrintDocument.Print%2A> per stampare il documento. Questo metodo invia alla stampante un oggetto <xref:System.Drawing.Graphics>, contenuto nella proprietà <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> della classe <xref:System.Drawing.Printing.PrintPageEventArgs>. Per un esempio in cui viene illustrato come stampare un documento di testo usando il componente <xref:System.Drawing.Printing.PrintDocument>, vedere [procedura: stampare un file di testo con più pagine in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).

- Processi di stampa più complessi, come i casi in cui è necessario riutilizzare la logica di stampa creata. In tal caso, è necessario derivare un nuovo componente dal componente <xref:System.Drawing.Printing.PrintDocument> ed eseguire l'override (vedere [sostituzioni](../../../visual-basic/language-reference/modifiers/overrides.md) per Visual Basic C#o [override](../../../csharp/language-reference/keywords/override.md) per) <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento.

Quando viene aggiunto a un modulo, il componente <xref:System.Drawing.Printing.PrintDocument> viene visualizzato nella barra delle applicazioni nella parte inferiore della Progettazione Windows Form in Visual Studio.

## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [Supporto per la stampa in Windows Forms](../advanced/windows-forms-print-support.md)
- [Componente PrintDocument](printdocument-component-windows-forms.md)
