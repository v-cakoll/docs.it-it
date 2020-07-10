---
title: 'Procedura: stampare un Windows Form'
description: Informazioni su come stampare una copia del Windows Form corrente a livello di codice usando il metodo CopyFromScreen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
ms.openlocfilehash: b59ea4b5347903b36a166c4f8ac0d8d7db18635e
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174692"
---
# <a name="how-to-print-a-windows-form"></a>Procedura: stampare un Windows Form
Come parte del processo di sviluppo, in genere si desidera stampare una copia di Windows Form. Nell'esempio di codice riportato di seguito viene illustrato come stampare una copia del form corrente utilizzando il <xref:System.Drawing.Graphics.CopyFromScreen%2A> metodo.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
- Non si dispone delle autorizzazioni necessarie per accedere alla stampante.  
  
- Nessuna stampante installata.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Per eseguire questo esempio di codice, è necessario disporre dell'autorizzazione per accedere alla stampante utilizzata con il computer.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Printing.PrintDocument>
- [Procedura: Eseguire il rendering delle immagini con GDI+](how-to-render-images-with-gdi.md)
- [Procedura: stampare grafica in Windows Forms](how-to-print-graphics-in-windows-forms.md)
