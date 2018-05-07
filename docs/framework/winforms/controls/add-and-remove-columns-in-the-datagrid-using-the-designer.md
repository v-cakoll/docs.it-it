---
title: 'Procedura: aggiungere e rimuovere colonne nel controllo DataGridView di Windows Form utilizzando Progettazione Windows Form'
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: f98d0e530f502655b9a48819d266a604581d22de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: aggiungere e rimuovere colonne nel controllo DataGridView di Windows Form utilizzando Progettazione Windows Form
Windows Form <xref:System.Windows.Forms.DataGridView> controllo deve contenere colonne per visualizzare i dati. Se si prevede di popolare il controllo manualmente, è necessario aggiungere le colonne. In alternativa, è possibile associare il controllo a un'origine dati, che genera l'errore e popola le colonne automaticamente. Se l'origine dati contiene più colonne che si desidera visualizzare, è possibile rimuovere le colonne non desiderate.  
  
 Le procedure seguenti richiedono un **applicazione Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGridView> controllo. Per informazioni sull'impostazione di un progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-a-column-using-the-designer"></a>Per aggiungere una colonna utilizzando la finestra di progettazione  
  
1.  Fare clic sul glifo smart tag (![Smart Tag glifo](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) nell'angolo superiore destro del <xref:System.Windows.Forms.DataGridView> controllare e quindi selezionare **Aggiungi colonna**.  
  
2.  Nel **Aggiungi colonna** finestra di dialogo scegliere la **colonna associata ai dati** opzione e selezionare una colonna dall'origine dati o scegliere il **colonna non associata** opzione e definire la colonna utilizzando gli appositi campi.  
  
3.  Fare clic su di **Aggiungi** pulsante per aggiungere la colonna, che viene visualizzata nella finestra di progettazione se le colonne esistenti non occupano già l'area di visualizzazione del controllo.  
  
    > [!NOTE]
    >  È possibile modificare le proprietà di colonna nel **Modifica colonne** nella finestra di dialogo è possibile accedere da smart tag del controllo.  
  
### <a name="to-remove-a-column-using-the-designer"></a>Per rimuovere una colonna utilizzando la finestra di progettazione  
  
1.  Scegliere **Modifica colonne** da smart tag del controllo.  
  
2.  Selezionare una colonna dal **colonne selezionate** elenco.  
  
3.  Fare clic su di **rimuovere** pulsante per eliminare la colonna dalla finestra di progettazione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 [Procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Procedura: Aggiungere controlli a un Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
