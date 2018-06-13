---
title: Cenni preliminari sul componente FolderBrowserDialog (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: a735749698266ac20e2ea9ee5569fd210ee9977b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525008"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a>Cenni preliminari sul componente FolderBrowserDialog (Windows Form)
Windows Form <xref:System.Windows.Forms.FolderBrowserDialog> componente è una finestra di dialogo modale che viene utilizzato per l'esplorazione e la selezione di cartelle. Inoltre è possibile creare nuove cartelle dall'interno di <xref:System.Windows.Forms.FolderBrowserDialog> componente.  
  
> [!NOTE]
>  Per selezionare i file, cartelle, invece di utilizzare il [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) componente.  
  
 Il <xref:System.Windows.Forms.FolderBrowserDialog> componente viene visualizzato in fase di esecuzione usando il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodo. Impostare il <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> proprietà per determinare la cartella di primo piano ed eventuali sottocartelle che verranno visualizzato all'interno della visualizzazione albero nella finestra di dialogo. Una volta la finestra di dialogo, è possibile utilizzare il <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> proprietà per ottenere il percorso della cartella in cui è stato selezionato.  
  
 Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.FolderBrowserDialog> componente viene visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.FolderBrowserDialog>  
 [Procedura: Scegliere cartelle con il componente FolderBrowserDialog di Windows Form](../../../../docs/framework/winforms/controls/how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)  
 [Componente FolderBrowserDialog](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
