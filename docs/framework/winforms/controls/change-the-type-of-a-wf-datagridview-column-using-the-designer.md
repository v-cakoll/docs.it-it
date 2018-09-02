---
title: 'Procedura: modificare il tipo di una colonna DataGridView di Windows Form utilizzando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 41ab0b36c5f3632ff4458d1289295ab2c9efe7c3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43420477"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a>Procedura: modificare il tipo di una colonna DataGridView di Windows Form utilizzando la finestra di progettazione
Talvolta si desidera modificare il tipo di una colonna che è già stato aggiunto a un controllo Windows Form <xref:System.Windows.Forms.DataGridView> controllo. Ad esempio, è possibile modificare i tipi di alcune delle colonne che vengono generate automaticamente quando si associa il controllo a un'origine dati. Ciò è utile quando la tabella visualizzata contiene le colonne che contengono chiavi esterne alle righe in una tabella correlata. In questo caso, è possibile sostituire le colonne di casella di testo che consentono di visualizzare le chiavi esterne con le colonne di casella combinata che visualizzano valori più significativi della tabella correlata.  
  
 La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGridView> controllo. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto di applicazione Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere i controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-change-the-type-of-a-column-using-the-designer"></a>Per modificare il tipo di una colonna utilizzando la finestra di progettazione  
  
1.  Fare clic sul glifo dello smart tag (![glifo Smart Tag](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro della <xref:System.Windows.Forms.DataGridView> controllare e quindi selezionare **Modifica colonne**.  
  
2.  Selezionare una colonna dal **colonne selezionate** elenco.  
  
3.  Nel **le proprietà delle colonne** griglia, impostare il `ColumnType` proprietà per il nuovo tipo di colonna.  
  
    > [!NOTE]
    >  Il `ColumnType` proprietà è una proprietà solo in fase di progettazione che indica la classe che rappresenta il tipo di colonna. Non è una proprietà effettivamente definita in una classe di colonna.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 [Procedura: creare un progetto di applicazione Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Procedura: Aggiungere controlli a un Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
