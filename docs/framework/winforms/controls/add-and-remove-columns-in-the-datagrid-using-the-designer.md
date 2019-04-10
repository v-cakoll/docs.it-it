---
title: 'Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 80ede9b7bc5bf667e03dc0a745fbc0b5f6c2663a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343285"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: Aggiungere e rimuovere colonne nel controllo DataGridView di Windows Forms usando la finestra di progettazione
I moduli di Windows <xref:System.Windows.Forms.DataGridView> controllo deve contenere colonne per poter visualizzare i dati. Se si prevede di inserire manualmente i dati del controllo, è necessario aggiungere le colonne. In alternativa, è possibile associare il controllo a un'origine dati, che genera e compila automaticamente le colonne. Se l'origine dati contiene più colonne di quelle che si desidera visualizzare, è possibile rimuovere le colonne non desiderate.  
  
 Nelle procedure seguenti è richiesto un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGridView> controllo. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-a-column-using-the-designer"></a>Per aggiungere una colonna utilizzando la finestra di progettazione  
  
1. Fare clic sul glifo dello smart tag (![glifo Smart Tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro della <xref:System.Windows.Forms.DataGridView> controllare e quindi selezionare **Aggiungi colonna**.  
  
2. Nel **Aggiungi colonna** finestra di dialogo scegliere la **colonna associata ai dati** e selezionare una colonna dall'origine dati o scegliere il **colonna non associata** opzione e definire la colonna utilizzando gli appositi campi.  
  
3. Scegliere il **Add** pulsante per aggiungere la colonna, in modo che venga visualizzata nella finestra di progettazione se le colonne esistenti non già riempire l'area di visualizzazione del controllo.  
  
    > [!NOTE]
    >  È possibile modificare proprietà della colonna nella **Modifica colonne** nella finestra di dialogo è possibile accedere da smart tag del controllo.  
  
### <a name="to-remove-a-column-using-the-designer"></a>Per rimuovere una colonna utilizzando la finestra di progettazione  
  
1. Scegli **Modifica colonne** dallo smart tag del controllo.  
  
2. Selezionare una colonna dal **colonne selezionate** elenco.  
  
3. Scegliere il **rimuovere** pulsante per eliminare la colonna, facendo in modo che scompaiano dalla finestra di progettazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Procedura: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: Aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md)
