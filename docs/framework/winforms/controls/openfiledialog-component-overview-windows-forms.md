---
title: Cenni preliminari sul componente OpenFileDialog (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: ad2fea74f0f3110ab2868064c588a7611d4261e3
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702906"
---
# <a name="openfiledialog-component-overview-windows-forms"></a>Cenni preliminari sul componente OpenFileDialog (Windows Form)
Il componente di Windows Form <xref:System.Windows.Forms.OpenFileDialog> è una finestra di dialogo preconfigurata. È uguale **Apri File** nella finestra di dialogo esposta dal sistema operativo Windows. Il componente eredita dalla classe <xref:System.Windows.Forms.CommonDialog>.  
  
## <a name="using-this-component"></a>Utilizzo di questo componente  
 Utilizzare questo componente all'interno dell'applicazione basata su Windows come una soluzione semplice per la selezione di file anziché configurare una propria finestra di dialogo. Basandosi sulle finestre di dialogo standard di Windows è quindi possibile creare applicazioni le cui funzionalità di base sono immediatamente familiari agli utenti. Tenere presente, tuttavia, che, quando tramite il <xref:System.Windows.Forms.OpenFileDialog> componente, è necessario scrivere la propria logica di apertura di file.  
  
 Usare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione. È possibile abilitare gli utenti di selezionare più file da aprire con il <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> proprietà. Inoltre, è possibile usare il <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> proprietà per determinare se una casella di controllo di sola lettura viene visualizzato nella finestra di dialogo. Il <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> proprietà indica se è selezionata la casella di controllo di sola lettura. Infine, il <xref:System.Windows.Forms.FileDialog.Filter%2A> proprietà imposta la stringa filtro, nome di file corrente che determina le scelte visualizzate nella finestra di "File di tipo" nella finestra di dialogo.  
  
 Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.OpenFileDialog> componente è visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.OpenFileDialog>
- [Componente OpenFileDialog](openfiledialog-component-windows-forms.md)
