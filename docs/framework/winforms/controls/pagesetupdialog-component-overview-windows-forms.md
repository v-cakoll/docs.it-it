---
title: Cenni preliminari sul componente PageSetupDialog
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: a891cb8cc77007d7591d41461c94f61c077eb300
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744335"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a>Cenni preliminari sul componente PageSetupDialog (Windows Form)

Il componente Windows Forms <xref:System.Windows.Forms.PageSetupDialog> è una finestra di dialogo preconfigurata utilizzata per impostare i dettagli della pagina per la stampa in applicazioni basate su Windows. Utilizzarlo all'interno dell'applicazione basata su Windows come soluzione semplice per consentire agli utenti di impostare le preferenze di pagina anziché configurare la propria finestra di dialogo. È possibile consentire agli utenti di impostare le regolazioni del bordo e del margine, le intestazioni e i piè di pagina e l'orientamento verticale o orizzontale. Basandosi sulle finestre di dialogo standard di Windows è quindi possibile creare applicazioni le cui funzionalità di base sono immediatamente familiari agli utenti.

## <a name="key-properties-and-methods"></a>Proprietà e metodi chiave

Usare il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> per visualizzare la finestra di dialogo in fase di esecuzione. Questo componente dispone di proprietà che è possibile impostare correlate a una singola pagina (<xref:System.Drawing.Printing.PrintDocument> classe) o a qualsiasi documento (classe<xref:System.Drawing.Printing.PageSettings>). Inoltre, è possibile utilizzare il componente <xref:System.Windows.Forms.PageSetupDialog> per determinare impostazioni della stampante specifiche, archiviate nella classe <xref:System.Drawing.Printing.PrinterSettings>.

Quando viene aggiunto a un modulo, il componente <xref:System.Windows.Forms.PageSetupDialog> viene visualizzato nella barra delle applicazioni nella parte inferiore della Progettazione Windows Form in Visual Studio.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.PageSetupDialog>
- [Componente PageSetupDialog](pagesetupdialog-component-windows-forms.md)
