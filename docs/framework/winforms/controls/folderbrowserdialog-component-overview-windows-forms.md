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
ms.openlocfilehash: aae18167b29c71ad692cc6ba447457cd079374b4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074131"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a>Cenni preliminari sul componente FolderBrowserDialog (Windows Form)
I moduli di Windows <xref:System.Windows.Forms.FolderBrowserDialog> componente è una finestra di dialogo modale che viene usata per l'esplorazione e selezione di cartelle. Sono anche possibile creare nuove cartelle dall'interno di <xref:System.Windows.Forms.FolderBrowserDialog> componente.  
  
> [!NOTE]
>  Per selezionare i file, invece di cartelle, usare il [OpenFileDialog](openfiledialog-component-windows-forms.md) componente.  
  
 Il <xref:System.Windows.Forms.FolderBrowserDialog> componente è visualizzato in fase di esecuzione usando il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> (metodo). Impostare il <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> proprietà per determinare la cartella di livello superiore ed eventuali sottocartelle che verranno visualizzato all'interno della visualizzazione struttura ad albero della finestra di dialogo. Una volta visualizzata la finestra di dialogo, è possibile usare il <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> proprietà da ottenere il percorso della cartella in cui è stato selezionato.  
  
 Quando viene aggiunto a un modulo, il <xref:System.Windows.Forms.FolderBrowserDialog> componente è visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Procedura: Scegliere cartelle con il componente FolderBrowserDialog di Windows Forms](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [Componente FolderBrowserDialog](folderbrowserdialog-component-windows-forms.md)
