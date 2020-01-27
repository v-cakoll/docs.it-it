---
title: Panoramica del componente PrintDialog
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0ed7f7a1f9770f71b75ae744a056b6943335c852
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728672"
---
# <a name="printdialog-component-overview-windows-forms"></a>Cenni preliminari sul componente PrintDialog (Windows Form)

Il Windows Forms componente [PrintDialog](printdialog-component-windows-forms.md) è una finestra di dialogo preconfigurata utilizzata per selezionare una stampante, scegliere le pagine da stampare e determinare altre impostazioni relative alla stampa nelle applicazioni basate su Windows. Questo componente può essere usato come semplice soluzione per la selezione della stampante e delle impostazioni relative alla stampa anziché configurare una propria finestra di dialogo. È possibile consentire agli utenti di stampare molte parti dei documenti: stampa tutto, stampa un intervallo di pagine selezionato o stampa una selezione. Basandosi sulle finestre di dialogo standard di Windows è quindi possibile creare applicazioni le cui funzionalità di base sono immediatamente familiari agli utenti. Il componente <xref:System.Windows.Forms.PrintDialog> eredita dalla classe <xref:System.Windows.Forms.CommonDialog>.

## <a name="working-with-the-component"></a>Utilizzo del componente

Utilizzare il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> per visualizzare la finestra di dialogo in fase di esecuzione. Questo componente dispone di proprietà correlate a un singolo processo di stampa (classe<xref:System.Drawing.Printing.PrintDocument>) o alle impostazioni di una singola stampante (<xref:System.Drawing.Printing.PrinterSettings> classe). Uno di questi, a sua volta, può essere condiviso da più stampanti.

Quando viene aggiunto a un modulo, il componente <xref:System.Windows.Forms.PrintDialog> viene visualizzato nella barra delle applicazioni nella parte inferiore della Progettazione Windows Form in Visual Studio.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.PrintDialog>
- [Componente PrintDialog](printdialog-component-windows-forms.md)
