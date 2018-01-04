---
title: Cenni preliminari sul componente PrintDialog (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b90d94165de6985b43d47809ae57bfcae204f0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="printdialog-component-overview-windows-forms"></a>Cenni preliminari sul componente PrintDialog (Windows Form)
Windows Form [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) componente è una finestra di dialogo preconfigurata che consentono di selezionare una stampante, scegliere le pagine da stampare e indicare altre impostazioni relative alla stampa nelle applicazioni basate su Windows. Questo componente può essere usato come semplice soluzione per la selezione della stampante e delle impostazioni relative alla stampa anziché configurare una propria finestra di dialogo. È possibile consentire agli utenti di stampare diverse parti dei documenti: stampare tutte, stampa di un intervallo di pagine selezionato o stampare una selezione. Basandosi sulle finestre di dialogo standard di Windows è quindi possibile creare applicazioni le cui funzionalità di base sono immediatamente familiari agli utenti. Il <xref:System.Windows.Forms.PrintDialog> componente eredita il <xref:System.Windows.Forms.CommonDialog> classe.  
  
## <a name="working-with-the-component"></a>Utilizzo del componente  
 Utilizzare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione. Il componente include proprietà relative a un singolo processo di stampa (<xref:System.Drawing.Printing.PrintDocument> classe) o le impostazioni di una singola stampante (<xref:System.Drawing.Printing.PrinterSettings> classe). Uno di questi elementi, a sua volta, può essere condiviso da più stampanti.  
  
 Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.PrintDialog> componente viene visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.PrintDialog>  
 [Componente PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)
