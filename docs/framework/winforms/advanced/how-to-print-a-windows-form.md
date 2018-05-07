---
title: 'Procedura: stampare un Windows Form'
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
ms.openlocfilehash: 42940654a0754ac3616ca7983af07d20607f480f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-print-a-windows-form"></a>Procedura: stampare un Windows Form
Come parte del processo di sviluppo, in genere verrà da stampare una copia di Windows Form. Esempio di codice seguente viene illustrato come stampare una copia del modulo corrente utilizzando il <xref:System.Drawing.Graphics.CopyFromScreen%2A> metodo.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Questo è un esempio di codice completo che contiene un `Main` metodo.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
-   Non si dispone dell'autorizzazione per accedere alla stampante.  
  
-   Non è installata alcuna stampante.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Per eseguire questo esempio di codice, è necessario disporre dell'autorizzazione per accedere alla stampante che è utilizzare con il computer.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Printing.PrintDocument>  
 [Procedura: Eseguire il rendering delle immagini con GDI+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)  
 [Procedura: stampare grafica in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)
