---
title: 'Procedura: Modificare il tipo di una colonna DataGridView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: e87017f3698bc88a123d8a0ba0df5dbe2b7bbfd9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939022"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a>Procedura: Modificare il tipo di una colonna DataGridView di Windows Forms usando la finestra di progettazione
Talvolta si desidera modificare il tipo di una colonna che è già stato aggiunto a un controllo Windows Form <xref:System.Windows.Forms.DataGridView> controllo. Ad esempio, è possibile modificare i tipi di alcune delle colonne che vengono generate automaticamente quando si associa il controllo a un'origine dati. Ciò è utile quando la tabella visualizzata contiene le colonne che contengono chiavi esterne alle righe in una tabella correlata. In questo caso, è possibile sostituire le colonne di casella di testo che consentono di visualizzare le chiavi esterne con le colonne di casella combinata che visualizzano valori più significativi della tabella correlata.  
  
 La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGridView> controllo. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-change-the-type-of-a-column-using-the-designer"></a>Per modificare il tipo di una colonna utilizzando la finestra di progettazione  
  
1. Fare clic sul glifo dello smart tag (![glifo Smart Tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro della <xref:System.Windows.Forms.DataGridView> controllare e quindi selezionare **Modifica colonne**.  
  
2. Selezionare una colonna dal **colonne selezionate** elenco.  
  
3. Nel **le proprietà delle colonne** griglia, impostare il `ColumnType` proprietà per il nuovo tipo di colonna.  
  
    > [!NOTE]
    >  Il `ColumnType` proprietà è una proprietà solo in fase di progettazione che indica la classe che rappresenta il tipo di colonna. Non è una proprietà effettivamente definita in una classe di colonna.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [Procedura: Creare un progetto di Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md)
