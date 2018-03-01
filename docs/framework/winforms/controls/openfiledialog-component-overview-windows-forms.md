---
title: Cenni preliminari sul componente OpenFileDialog (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d3e5dc6630d9bc7a2090a28daabbf08eeed59005
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="openfiledialog-component-overview-windows-forms"></a>Cenni preliminari sul componente OpenFileDialog (Windows Form)
Il componente di Windows Form <xref:System.Windows.Forms.OpenFileDialog> è una finestra di dialogo preconfigurata. Ha lo stesso **Apri** la finestra di dialogo esposta dal sistema operativo Windows. Il componente eredita dalla classe <xref:System.Windows.Forms.CommonDialog>.  
  
## <a name="using-this-component"></a>Utilizzando questo componente  
 Utilizzare questo componente nell'applicazione basata su Windows come semplice soluzione per la selezione di file anziché configurare la propria finestra di dialogo. Basandosi sulle finestre di dialogo standard di Windows è quindi possibile creare applicazioni le cui funzionalità di base sono immediatamente familiari agli utenti. Tenere presente, tuttavia, che, quando tramite il <xref:System.Windows.Forms.OpenFileDialog> componente, è necessario scrivere la propria logica per l'apertura di file.  
  
 Utilizzare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione. È possibile consentire agli utenti di selezionare più file da aprire con il <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> proprietà. Inoltre, è possibile utilizzare il <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> proprietà per determinare se una casella di controllo di sola lettura viene visualizzata nella finestra di dialogo. Il <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> proprietà indica se è selezionata la casella di controllo di sola lettura. Infine, il <xref:System.Windows.Forms.FileDialog.Filter%2A> proprietà imposta la stringa filtro del nome file corrente, che determina le scelte visualizzate nella finestra di "tipo file" nella finestra di dialogo.  
  
 Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.OpenFileDialog> componente viene visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [Componente OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
