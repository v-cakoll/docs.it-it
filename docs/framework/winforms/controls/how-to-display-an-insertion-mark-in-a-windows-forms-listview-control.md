---
title: 'Procedura: visualizzare un segno di inserimento in un controllo ListView per Windows Form'
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
- cpp
helpviewer_keywords:
- ListView control [Windows Forms], drag operations
- graphics [Windows Forms], insertion marks
- drop and drag [Windows Forms], insertion marks
- insertion marks
ms.assetid: 88d0a15b-25fd-4dc3-a685-297351311940
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3b1a312159d548351e96fd16c32caf35a0522065
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a>Procedura: visualizzare un segno di inserimento in un controllo ListView per Windows Form
Il segno di inserimento nel controllo <xref:System.Windows.Forms.ListView> indica agli utenti il punto in cui verranno inseriti gli elementi trascinati. Quando un utente trascina un elemento in un punto intermedio tra due elementi, il segno di inserimento indica la nuova posizione prevista dell'elemento.  
  
> [!NOTE]
>  La funzionalità del segno di inserimento è disponibile solo in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] quando l'applicazione chiama il metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. Nei sistemi operativi precedenti, qualsiasi codice relativo al segno di inserimento non ha alcun effetto e il segno di inserimento non verrà visualizzato. Per altre informazioni, vedere <xref:System.Windows.Forms.ListViewInsertionMark>.  
  
 L'immagine seguente mostra un segno di inserimento:  
  
 ![Segno di inserimento di ListView](../../../../docs/framework/winforms/controls/media/listviewinsertion.gif "ListViewInsertion")  
  
 L'esempio di codice seguente illustra l'uso di questa funzionalità.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System e System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], vedere [Compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilazione dalla riga di comando con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] incollando il codice in un nuovo progetto.  Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Forms completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ListViewInsertionMark>  
 [Controllo ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Panoramica del controllo ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Funzionalità di Windows XP e controlli di Windows Forms](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [Procedura dettagliata: esecuzione di un'operazione di trascinamento in Windows Form](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)
