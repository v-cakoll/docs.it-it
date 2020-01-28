---
title: Panoramica del componente FolderBrowserDialog
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: 8b017ba08ae4205e930ac00177c89a89fde17d3b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745732"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a>Cenni preliminari sul componente FolderBrowserDialog (Windows Form)

Il componente Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> è una finestra di dialogo modale utilizzata per l'esplorazione e la selezione di cartelle. È anche possibile creare nuove cartelle dall'interno del componente <xref:System.Windows.Forms.FolderBrowserDialog>.

> [!NOTE]
> Per selezionare i file, anziché le cartelle, utilizzare il componente [OpenFileDialog](openfiledialog-component-windows-forms.md) .

Il componente <xref:System.Windows.Forms.FolderBrowserDialog> viene visualizzato in fase di esecuzione usando il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>. Impostare la proprietà <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> per determinare la cartella più in alto e tutte le sottocartelle che verranno visualizzate nella visualizzazione albero della finestra di dialogo. Una volta visualizzata la finestra di dialogo, è possibile utilizzare la proprietà <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> per ottenere il percorso della cartella selezionata.

Quando viene aggiunto a un modulo, il componente <xref:System.Windows.Forms.FolderBrowserDialog> viene visualizzato nella barra delle applicazioni nella parte inferiore della Progettazione Windows Form in Visual Studio.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Procedura: Scegliere cartelle con il componente FolderBrowserDialog di Windows Form](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [Componente FolderBrowserDialog](folderbrowserdialog-component-windows-forms.md)
