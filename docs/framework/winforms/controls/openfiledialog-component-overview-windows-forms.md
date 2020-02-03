---
title: Cenni preliminari sul componente OpenFileDialog
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: c519b373150a49ee41dbb0c503f7d5a4862477d5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728444"
---
# <a name="openfiledialog-component-overview-windows-forms"></a>Cenni preliminari sul componente OpenFileDialog (Windows Form)

Il componente di Windows Form <xref:System.Windows.Forms.OpenFileDialog> è una finestra di dialogo preconfigurata. Si tratta della stessa finestra di dialogo **Apri file** esposta dal sistema operativo Windows. Il componente eredita dalla classe <xref:System.Windows.Forms.CommonDialog>.

## <a name="use-this-component"></a>Usa questo componente

Usare questo componente nell'applicazione basata su Windows come soluzione semplice per la selezione dei file anziché configurare la propria finestra di dialogo. Basandosi sulle finestre di dialogo standard di Windows è quindi possibile creare applicazioni le cui funzionalità di base sono immediatamente familiari agli utenti. Tenere presente, tuttavia, che quando si usa il componente <xref:System.Windows.Forms.OpenFileDialog>, è necessario scrivere una logica di apertura dei file personalizzata.

Usare il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> per visualizzare la finestra di dialogo in fase di esecuzione. È possibile consentire agli utenti di selezionare più file da aprire con la proprietà <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A>. Inoltre, è possibile utilizzare la proprietà <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> per determinare se nella finestra di dialogo viene visualizzata una casella di controllo di sola lettura. La proprietà <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> indica se è selezionata la casella di controllo di sola lettura. Infine, la proprietà <xref:System.Windows.Forms.FileDialog.Filter%2A> imposta la stringa di filtro del nome file corrente, che determina le scelte visualizzate nella casella "file di tipo" nella finestra di dialogo.

Quando viene aggiunto a un modulo, il componente <xref:System.Windows.Forms.OpenFileDialog> viene visualizzato nella barra delle applicazioni nella parte inferiore della Progettazione Windows Form in Visual Studio.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.OpenFileDialog>
- [Componente OpenFileDialog](openfiledialog-component-windows-forms.md)
