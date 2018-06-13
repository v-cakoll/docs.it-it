---
title: 'Procedura: creare un controllo con associazione semplice in un Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: ce4585a1c5c2b9acbdb7ec33c62a1e91851b720e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538832"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a>Procedura: creare un controllo con associazione semplice in un Windows Form
Con *associazione semplice*, è possibile visualizzare un singolo elemento dati, ad esempio un valore di colonna da una tabella di set di dati, in un controllo. È possibile un'associazione semplice di qualsiasi proprietà di un controllo a un valore di dati.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-simple-bind-a-control"></a>Per un controllo con associazione a semplice  
  
1.  Effettuare una connessione a un'origine dati. Per ulteriori informazioni, vedere [la connessione a un'origine dati](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).  
  
2.  Selezionare il controllo nel form e visualizzare il **proprietà** finestra.  
  
3.  Espandere il **(DataBindings)** proprietà.  
  
     Le proprietà più frequentemente associate vengono visualizzate sotto il **(DataBindings)** proprietà. Ad esempio, nella maggior parte dei controlli, la **testo** proprietà è associata più di frequente.  
  
4.  Se la proprietà che si desidera associare non fa parte di più comunemente associate, fare clic su di **i puntini di sospensione** pulsante (![schermata VisualStudioEllipsesButton](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton") ) nei **(avanzate)** casella per visualizzare il **formattazione e associazione avanzata** la finestra di dialogo con un elenco completo delle proprietà per tale controllo.  
  
5.  Selezionare la proprietà che si desidera associare e fare clic sulla freccia a discesa sotto **associazione**.  
  
     Verrà visualizzato un elenco di origini dati disponibili.  
  
6.  Espandere l'origine dati da associare fino a quando non vengono visualizzati i dati desiderati. Se ad esempio si vuole associare il valore di una colonna in una tabella di set di dati, espandere il nome del set di dati, quindi espandere il nome della tabella per visualizzare i nomi delle colonne.  
  
7.  Fare clic sul nome dell'elemento a cui effettuare il binding.  
  
8.  Se si utilizza il **formattazione e associazione avanzata** la finestra di dialogo, fare clic su **OK** per tornare al **proprietà** finestra.  
  
9. Se si desidera associare proprietà aggiuntive del controllo, ripetere i passaggi da 3 a 7.  
  
    > [!NOTE]
    >  Poiché i controlli con associazione semplice visualizzare solo un singolo elemento dati, viene in genere includere logica di spostamento in un Windows Form con controlli con associazione semplice.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Binding>  
 [Data binding in Windows Form](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Data binding e Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
