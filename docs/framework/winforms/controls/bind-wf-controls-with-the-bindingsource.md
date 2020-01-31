---
title: Associare controlli al componente BindingSource utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: 35b3fb7b9884f07dd6e2aef311a01d3090c44227
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744387"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a>Procedura: associare controlli Windows Form al componente BindingSource utilizzando la finestra di progettazione
Dopo aver aggiunto i controlli al modulo e aver determinato l'interfaccia utente per l'applicazione, è possibile associare i controlli a un'origine dati, in modo che, in fase di esecuzione, gli utenti possano modificare e salvare i dati correlati all'applicazione.

 L'associazione di un controllo o di una serie di controlli in Windows Forms viene eseguita più facilmente utilizzando il controllo <xref:System.Windows.Forms.BindingSource> come ponte tra i controlli nel form e l'origine dati.

 Uno o più controlli in un modulo possono essere associati ai dati; nella procedura seguente un controllo <xref:System.Windows.Forms.TextBox> viene associato a un'origine dati.

 Per completare la procedura, si presuppone che si eseguirà l'associazione a un'origine dati derivata da un database. Per altre informazioni sulla creazione di origini dati da altri archivi di dati, vedere [aggiungere nuove origini dati](/visualstudio/data-tools/add-new-data-sources).

## <a name="to-bind-a-control-at-design-time"></a>Per associare un controllo in fase di progettazione

1. Trascinare un controllo <xref:System.Windows.Forms.TextBox> sul form.

2. Nella finestra **Proprietà** :

    1. Espandere il nodo **(DataBindings)** .

    2. Fare clic sulla freccia accanto alla proprietà <xref:System.Windows.Forms.TextBox.Text%2A>.

         Si apre l'editor di tipo dell'interfaccia utente **DataSource** .

         Se un'origine dati è stata configurata in precedenza per il progetto o il form, verrà visualizzata.

3. Fare clic su **Aggiungi origine dati progetto** per connettersi ai dati e creare un'origine dati.

4. Nella pagina iniziale della **Configurazione guidata origine dati** fare clic su **Avanti**.

5. Nella pagina **scegliere un tipo di origine dati** selezionare **database**.

6. Nella pagina **Seleziona connessione dati** selezionare una connessione dati nell'elenco delle connessioni disponibili. Se la connessione dati desiderata non è disponibile, selezionare **nuova connessione** per creare una nuova connessione dati.

7. Selezionare **Sì, salva la connessione** per salvare la stringa di connessione nel file di configurazione dell'applicazione.

8. Selezionare gli oggetti database da inserire nell'applicazione. In questo caso, selezionare un campo in una tabella che si desidera visualizzare nel <xref:System.Windows.Forms.TextBox>.

9. Se si vuole, sostituire il nome predefinito del set di dati.

10. Scegliere **Fine**.

11. Nella finestra **Proprietà** fare clic sulla freccia accanto alla proprietà <xref:System.Windows.Forms.TextBox.Text%2A>. Nell'editor di tipo dell'interfaccia utente **DataSource** selezionare il nome del campo a cui associare il <xref:System.Windows.Forms.TextBox>.

     L'editor di tipo dell'interfaccia utente **DataSource** si chiude e il set di dati, la <xref:System.Windows.Forms.BindingSource> e l'adattatore tabella specifici della connessione dati vengono aggiunti al form.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [Aggiungi nuova origine dati](/visualstudio/data-tools/add-new-data-sources)
- [Finestra Origini dati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))
