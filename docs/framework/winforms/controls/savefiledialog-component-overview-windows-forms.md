---
title: Cenni preliminari sul componente SaveFileDialog
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: 7609c29b7e932ecee7dc8a289617094bd8d480e2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743108"
---
# <a name="savefiledialog-component-overview-windows-forms"></a>Cenni preliminari sul componente SaveFileDialog (Windows Form)

Il componente di Windows Form <xref:System.Windows.Forms.SaveFileDialog> è una finestra di dialogo preconfigurata. Corrisponde alla finestra di dialogo **Salva file** standard utilizzata da Windows. Il componente eredita dalla classe <xref:System.Windows.Forms.CommonDialog>.

## <a name="working-with-the-savefiledialog-component"></a>Utilizzo del componente SaveFileDialog

Usarlo come soluzione semplice per consentire agli utenti di salvare i file anziché configurare la propria finestra di dialogo. Basandosi sulle finestre di dialogo standard di Windows, le funzionalità di base delle applicazioni create sono immediatamente note agli utenti. Tenere presente, tuttavia, che quando si usa il componente <xref:System.Windows.Forms.SaveFileDialog>, è necessario scrivere una logica di salvataggio file personalizzata.

È possibile utilizzare il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> per visualizzare la finestra di dialogo in fase di esecuzione. È possibile aprire un file in modalità di lettura/scrittura usando il metodo <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>.

Quando viene aggiunto a un modulo, il componente <xref:System.Windows.Forms.SaveFileDialog> viene visualizzato nella barra delle applicazioni nella parte inferiore della Progettazione Windows Form in Visual Studio.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.SaveFileDialog>
- [Componente SaveFileDialog](savefiledialog-component-windows-forms.md)
