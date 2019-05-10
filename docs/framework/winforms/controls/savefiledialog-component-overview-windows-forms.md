---
title: Cenni preliminari sul componente SaveFileDialog (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: 1e4269129f17c10056af2765c7a0e74537918ae5
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211613"
---
# <a name="savefiledialog-component-overview-windows-forms"></a>Cenni preliminari sul componente SaveFileDialog (Windows Form)

Il componente di Windows Form <xref:System.Windows.Forms.SaveFileDialog> è una finestra di dialogo preconfigurata. È identico allo standard **Salva File** dialogo utilizzata da Windows. Il componente eredita dalla classe <xref:System.Windows.Forms.CommonDialog>.

## <a name="working-with-the-savefiledialog-component"></a>Utilizzo del componente SaveFileDialog

Usarlo come una soluzione semplice per consentire agli utenti di salvare i file invece di configurare una propria finestra di dialogo. Basandosi sulle finestre di dialogo di Windows standard, la funzionalità di base di applicazioni create è immediatamente familiare agli utenti. Tenere presente, tuttavia, che, quando tramite il <xref:System.Windows.Forms.SaveFileDialog> componente, è necessario scrivere la propria logica di salvataggio dei file.

È possibile usare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione. È possibile aprire un file in modalità di lettura/scrittura tramite il <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> (metodo).

Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.SaveFileDialog> componente è visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form in Visual Studio.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.SaveFileDialog>
- [Componente SaveFileDialog](savefiledialog-component-windows-forms.md)
