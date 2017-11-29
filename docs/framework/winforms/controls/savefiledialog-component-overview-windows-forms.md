---
title: Cenni preliminari sul componente SaveFileDialog (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cbdc1cb96234e302458cbeac6d6ae26b63c956e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="savefiledialog-component-overview-windows-forms"></a>Cenni preliminari sul componente SaveFileDialog (Windows Form)
Il componente di Windows Form <xref:System.Windows.Forms.SaveFileDialog> è una finestra di dialogo preconfigurata. Ha lo stesso come standard **Salva File** la finestra di dialogo utilizzata da Windows. Il componente eredita dalla classe <xref:System.Windows.Forms.CommonDialog>.  
  
## <a name="working-with-the-savefiledialog-component"></a>Utilizzo del componente SaveFileDialog  
 Utilizzarlo come semplice soluzione per consentire agli utenti di salvare i file invece configurare la propria finestra di dialogo. Basandosi sulle finestre di dialogo standard di Windows, la funzionalità di base delle applicazioni creati è immediatamente familiare agli utenti. Tenere presente, tuttavia, che, quando tramite il <xref:System.Windows.Forms.SaveFileDialog> componente, è necessario scrivere la propria logica di salvataggio di file.  
  
 È possibile utilizzare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione. È possibile aprire un file in modalità lettura/scrittura con la <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> metodo.  
  
 Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.SaveFileDialog> componente viene visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.SaveFileDialog>  
 [Componente SaveFileDialog](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)
