---
title: Cenni preliminari sul componente PageSetupDialog (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: 4e7b4548f5a178ed7b819dbc2edc37bb95e3e0f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534225"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a>Cenni preliminari sul componente PageSetupDialog (Windows Form)
Windows Form <xref:System.Windows.Forms.PageSetupDialog> componente è una finestra di dialogo preconfigurata che consentono di impostare i dettagli della pagina per la stampa nelle applicazioni basate su Windows. Utilizzarlo all'interno dell'applicazione basate su Windows come una soluzione semplice per gli utenti per impostare preferenze della pagina anziché configurare la propria finestra di dialogo. È possibile abilitare l'impostazione bordo e i margini, intestazioni e piè di pagina e l'orientamento verticale o orizzontale. Basandosi sulle finestre di dialogo standard di Windows è quindi possibile creare applicazioni le cui funzionalità di base sono immediatamente familiari agli utenti.  
  
## <a name="key-properties-and-methods"></a>Metodi e proprietà chiave  
 Utilizzare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione. Questo componente è è possibile impostare proprietà relative a una singola pagina (<xref:System.Drawing.Printing.PrintDocument> classe) o a qualsiasi documento (<xref:System.Drawing.Printing.PageSettings> classe). Inoltre, il <xref:System.Windows.Forms.PageSetupDialog> componente può essere utilizzato per determinare le impostazioni della stampante specifiche, che vengono archiviate nel <xref:System.Drawing.Printing.PrinterSettings> classe.  
  
 Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.PageSetupDialog> componente viene visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.PageSetupDialog>  
 [Componente PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)
