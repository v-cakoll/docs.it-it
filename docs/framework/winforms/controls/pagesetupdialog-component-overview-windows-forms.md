---
title: Cenni preliminari sul componente PageSetupDialog (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: 989183b6152dfccb6167d89433317cea596d83c5
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211738"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a>Cenni preliminari sul componente PageSetupDialog (Windows Form)

I moduli di Windows <xref:System.Windows.Forms.PageSetupDialog> componente è una finestra di dialogo preconfigurata che consente di impostare i dettagli della pagina per la stampa nelle applicazioni basate su Windows. Usarlo all'interno dell'applicazione basata su Windows come una soluzione semplice per gli utenti per impostare preferenze delle pagine anziché configurare una propria finestra di dialogo. È possibile abilitare gli utenti di impostare i bordi e i margini, intestazioni e piè di pagina e l'orientamento verticale o orizzontale. Basandosi sulle finestre di dialogo standard di Windows è quindi possibile creare applicazioni le cui funzionalità di base sono immediatamente familiari agli utenti.

## <a name="key-properties-and-methods"></a>I metodi e proprietà chiave

Usare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione. Il componente include proprietà che è possibile impostare relative a una singola pagina (<xref:System.Drawing.Printing.PrintDocument> classe) o dei documenti (<xref:System.Drawing.Printing.PageSettings> classe). Inoltre, il <xref:System.Windows.Forms.PageSetupDialog> componente può essere utilizzato per determinare le impostazioni della stampante specifici, che vengono archiviate nel <xref:System.Drawing.Printing.PrinterSettings> classe.

Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.PageSetupDialog> componente è visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form in Visual Studio.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.PageSetupDialog>
- [Componente PageSetupDialog](pagesetupdialog-component-windows-forms.md)
