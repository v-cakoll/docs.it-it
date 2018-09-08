---
title: 'Procedura: creare un controllo con associazione semplice in un Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: 26bc136ea2b7e5bda4a57c5dad65ec3522efcd3d
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44138370"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a>Procedura: creare un controllo con associazione semplice in un Windows Form
Con *associazione semplice*, è possibile visualizzare un singolo elemento di dati, ad esempio un valore di colonna da una tabella di set di dati, in un controllo. È possibile un'associazione semplice di qualsiasi proprietà di un controllo a un valore di dati.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-simple-bind-a-control"></a>Per un controllo di un'associazione semplice  
  
1.  Effettuare una connessione a un'origine dati. Per altre informazioni, vedere [ci si connette a un'origine dati](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).  
  
2.  Selezionare il controllo nel form e visualizzare il **proprietà** finestra.  
  
3.  Espandere la **(DataBindings)** proprietà.  
  
     Le proprietà associate in genere sono visualizzate sotto le **(DataBindings)** proprietà. Ad esempio, nella maggior parte dei controlli, il **testo** più di frequente è associata la proprietà.  
  
4.  Se la proprietà si desidera binding non è uno dei più comunemente associate, selezionare la **puntini di sospensione** pulsante (![schermata di VisualStudioEllipsesButton](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton") ) nei **(avanzate)** casella per visualizzare i **formattazione e associazione avanzata** finestra di dialogo contenente un elenco completo delle proprietà per il controllo.  
  
5.  Selezionare la proprietà si desidera eseguire il binding e fare clic sulla freccia a discesa sotto **Binding**.  
  
     Verrà visualizzato un elenco di origini dati disponibili.  
  
6.  Espandere l'origine dati da associare fino a quando non vengono visualizzati i dati desiderati. Se ad esempio si vuole associare il valore di una colonna in una tabella di set di dati, espandere il nome del set di dati, quindi espandere il nome della tabella per visualizzare i nomi delle colonne.  
  
7.  Fare clic sul nome dell'elemento a cui effettuare il binding.  
  
8.  Se si utilizza il **formattazione e associazione avanzata** della finestra di dialogo fare clic su **OK** per tornare al **proprietà** finestra.  
  
9. Se si desidera associare proprietà aggiuntive del controllo, ripetere i passaggi da 3 a 7.  
  
    > [!NOTE]
    >  Poiché i controlli con associazione semplice visualizzare solo un singolo elemento di dati, viene in genere includere logica di navigazione in un Windows Form con controlli con associazione semplice.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Binding>  
 [Data binding in Windows Form](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Data binding e Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
