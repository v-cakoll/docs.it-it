---
title: Cenni preliminari sul componente PageSetupDialog (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 082dbff66c8a0f06635936011f802c99b88e41df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a>Cenni preliminari sul componente PageSetupDialog (Windows Form)
Windows Form <xref:System.Windows.Forms.PageSetupDialog> componente è una finestra di dialogo preconfigurata che consentono di impostare i dettagli della pagina per la stampa nelle applicazioni basate su Windows. Utilizzarlo all'interno dell'applicazione basate su Windows come una soluzione semplice per gli utenti per impostare preferenze della pagina anziché configurare la propria finestra di dialogo. È possibile abilitare l'impostazione bordo e i margini, intestazioni e piè di pagina e l'orientamento verticale o orizzontale. Basandosi sulle finestre di dialogo standard di Windows è quindi possibile creare applicazioni le cui funzionalità di base sono immediatamente familiari agli utenti.  
  
## <a name="key-properties-and-methods"></a>Metodi e proprietà chiave  
 Utilizzare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione. Questo componente è è possibile impostare proprietà relative a una singola pagina (<xref:System.Drawing.Printing.PrintDocument> classe) o a qualsiasi documento (<xref:System.Drawing.Printing.PageSettings> classe). Inoltre, il <xref:System.Windows.Forms.PageSetupDialog> componente può essere utilizzato per determinare le impostazioni della stampante specifiche, che vengono archiviate nel <xref:System.Drawing.Printing.PrinterSettings> classe.  
  
 Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.PageSetupDialog> componente viene visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.PageSetupDialog>  
 [Componente PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)
