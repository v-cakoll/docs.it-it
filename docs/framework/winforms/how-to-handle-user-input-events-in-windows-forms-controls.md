---
title: 'Procedura: Gestire eventi di input utente nei controlli Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, user input
- user input [Windows Forms], Windows Forms controls
ms.assetid: 3de74dcf-fae3-42d0-92b5-bc04a61a6888
ms.openlocfilehash: 5dc1997dffc53632ce8b36bc5fe89e768871fd0f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108667"
---
# <a name="how-to-handle-user-input-events-in-windows-forms-controls"></a>Procedura: Gestire eventi di input utente nei controlli Windows Forms
In questo esempio viene illustrato come gestire la maggior parte degli eventi di convalida, stato attivo, mouse e tastiera che possono verificarsi in un controllo Windows Form. La casella di testo denominata `TextBoxInput` riceve gli eventi quando è attiva e le informazioni relative a ogni evento vengono scritte nella casella di testo denominata `TextBoxOutput` nell'ordine di generazione degli eventi. L'applicazione include anche un set di caselle di controllo che possono essere usate per filtrare gli eventi da segnalare.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  
  
## <a name="see-also"></a>Vedere anche

- [Input dell'utente in Windows Forms](user-input-in-windows-forms.md)
