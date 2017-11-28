---
title: 'Procedura: stampare un Windows Form'
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
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9149b90317036c7c62c5fca3056bb697df56e543
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
