---
title: 'Procedura: condividere dati associati tra form tramite il componente BindingSource'
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
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 95fd7583e6d86aa84c53f6cee7056f1d631e948b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a>Procedura: condividere dati associati tra form tramite il componente BindingSource
È possibile condividere facilmente i dati tra i form con il componente <xref:System.Windows.Forms.BindingSource>. Ad esempio, è possibile visualizzare un form di sola lettura che riepiloga i dati dell'origine dati e un altro form modificabile che contiene informazioni dettagliate sull'elemento attualmente selezionato nell'origine dati. L'esempio illustra questo scenario.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente illustra come condividere un oggetto <xref:System.Windows.Forms.BindingSource> e i dati associati tra i form. In questo esempio, l'oggetto <xref:System.Windows.Forms.BindingSource> condiviso viene passato al costruttore del form figlio. Il form figlio consente all'utente di modificare i dati per l'elemento attualmente selezionato nel form principale.  
  
> [!NOTE]
>  Nell'esempio viene gestito l'evento <xref:System.Windows.Forms.BindingSource.BindingComplete> del componente <xref:System.Windows.Forms.BindingSource> per essere certi che i due form rimangano sincronizzati Per altre informazioni sul motivo per cui questa operazione viene eseguita, vedere [Procedura: Garantire la sincronizzazione di più controlli associati alla stessa origine dati](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md).  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System, System.Windows.Forms, System.Drawing, System.Data e System.Xml.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], vedere [Compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilazione dalla riga di comando con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] incollando il codice in un nuovo progetto.  Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Forms completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vedere anche  
 [Componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [Data binding in Windows Form](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Procedura: gestire gli errori e le eccezioni che si verificano con l'associazione dati](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
