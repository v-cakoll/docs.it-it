---
title: Cenni preliminari sul componente SaveFileDialog (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: b06c4d510cefdc7558944995594fd209b6121cb1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904670"
---
# <a name="savefiledialog-component-overview-windows-forms"></a>Cenni preliminari sul componente SaveFileDialog (Windows Form)
Il componente di Windows Form <xref:System.Windows.Forms.SaveFileDialog> è una finestra di dialogo preconfigurata. È identico allo standard **Salva File** dialogo utilizzata da Windows. Il componente eredita dalla classe <xref:System.Windows.Forms.CommonDialog>.  
  
## <a name="working-with-the-savefiledialog-component"></a>Utilizzo del componente SaveFileDialog  
 Usarlo come una soluzione semplice per consentire agli utenti di salvare i file invece di configurare una propria finestra di dialogo. Basandosi sulle finestre di dialogo di Windows standard, la funzionalità di base di applicazioni create è immediatamente familiare agli utenti. Tenere presente, tuttavia, che, quando tramite il <xref:System.Windows.Forms.SaveFileDialog> componente, è necessario scrivere la propria logica di salvataggio dei file.  
  
 È possibile usare il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo per visualizzare la finestra di dialogo in fase di esecuzione. È possibile aprire un file in modalità di lettura/scrittura tramite il <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> (metodo).  
  
 Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.SaveFileDialog> componente è visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.SaveFileDialog>
- [Componente SaveFileDialog](savefiledialog-component-windows-forms.md)
