---
title: 'Procedura: associare controlli Windows Form al componente BindingSource utilizzando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: 95f375d8845c60441aa5eefdd37e32541ea2d5a7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43565681"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a>Procedura: associare controlli Windows Form al componente BindingSource utilizzando la finestra di progettazione
Dopo aver aggiunto i controlli al form e determinare l'interfaccia utente per l'applicazione, è possibile associare i controlli a un'origine dati, in modo che, in fase di esecuzione, gli utenti possono modificare e salvare i dati correlati all'applicazione.  
  
 Associazione di un controllo o una serie di controlli in Windows Form viene effettuata più facilmente usando le <xref:System.Windows.Forms.BindingSource> controllo che funge da ponte tra i controlli nel form e l'origine dati.  
  
 Uno o più controlli in un form possono essere associati a dati. Nella procedura seguente, un <xref:System.Windows.Forms.TextBox> è associato a un'origine dati.  
  
 Per completare la procedura, si presuppone che verrà associato a un'origine dati derivata da un database. Per altre informazioni sulla creazione di origini dati da altri archivi di dati, vedere [aggiungono nuove origini dati](/visualstudio/data-tools/add-new-data-sources).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-bind-a-control-at-design-time"></a>Per associare un controllo in fase di progettazione  
  
1.  Trascinare un <xref:System.Windows.Forms.TextBox> controllo al form.  
  
2.  Nel **proprietà** finestra:  
  
    1.  Espandere la **(DataBindings)** nodo.  
  
    2.  Fare clic sulla freccia accanto al <xref:System.Windows.Forms.TextBox.Text%2A> proprietà.  
  
         Il **DataSource** verrà aperto l'editor di tipo dell'interfaccia utente.  
  
         Se un'origine dati è stata configurata in precedenza per il progetto o un modulo, verrà visualizzata.  
  
3.  Fare clic su **Aggiungi origine dati progetto** per connettersi ai dati e creare un'origine dati.  
  
4.  Nella pagina iniziale della **Configurazione guidata origine dati** fare clic su **Avanti**.  
  
5.  Nel **scegliere un tipo di origine dati** pagina, selezionare **Database**.  
  
6.  Nel **Seleziona connessione dati** pagina, selezionare una connessione dati dall'elenco delle connessioni disponibili. Se la connessione dati desiderata non è disponibile, selezionare **nuova connessione** per creare una nuova connessione dati.  
  
7.  Selezionare **Sì, Salva la connessione** per salvare la stringa di connessione nel file di configurazione dell'applicazione.  
  
8.  Selezionare gli oggetti database da inserire nell'applicazione. In questo caso, selezionare un campo in una tabella che si desidera il <xref:System.Windows.Forms.TextBox> da visualizzare.  
  
9. Se si vuole, sostituire il nome predefinito del set di dati.  
  
10. Scegliere **Fine**.  
  
11. Nel **delle proprietà** finestra, fare clic sulla freccia accanto al <xref:System.Windows.Forms.TextBox.Text%2A> proprietà nuovamente. Nel **DataSource** editor di tipo dell'interfaccia utente, selezionare il nome del campo a cui associare il <xref:System.Windows.Forms.TextBox> a.  
  
     Il **DataSource** verrà chiuso editor e il set di dati di tipo UI <xref:System.Windows.Forms.BindingSource> e adattatore di tabella specifico di connessione dati verranno aggiunti al form.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingNavigator>  
 [Aggiungi nuova origine dati](/visualstudio/data-tools/add-new-data-sources)  
 [Finestra Origini dati](https://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)
