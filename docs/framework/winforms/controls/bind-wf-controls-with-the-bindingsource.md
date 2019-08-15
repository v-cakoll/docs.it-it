---
title: 'Procedura: Associare i controlli di Windows Forms al componente BindingSource usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: 180fafa9ace5927fd84ec5dc0a1b2a342f771efd
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040022"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a>Procedura: Associare i controlli di Windows Forms al componente BindingSource usando la finestra di progettazione
Dopo aver aggiunto i controlli al modulo e aver determinato l'interfaccia utente per l'applicazione, è possibile associare i controlli a un'origine dati, in modo che, in fase di esecuzione, gli utenti possano modificare e salvare i dati correlati all'applicazione.

 L'associazione di un controllo o di una serie di controlli in Windows Forms viene eseguita <xref:System.Windows.Forms.BindingSource> più facilmente utilizzando il controllo come bridge tra i controlli nel form e l'origine dati.

 Uno o più controlli in un modulo possono essere associati ai dati; nella procedura seguente un <xref:System.Windows.Forms.TextBox> controllo è associato a un'origine dati.

 Per completare la procedura, si presuppone che si eseguirà l'associazione a un'origine dati derivata da un database. Per altre informazioni sulla creazione di origini dati da altri archivi di dati, vedere [aggiungere nuove origini dati](/visualstudio/data-tools/add-new-data-sources).

## <a name="to-bind-a-control-at-design-time"></a>Per associare un controllo in fase di progettazione

1. Trascinare un <xref:System.Windows.Forms.TextBox> controllo nel form.

2. Nella finestra **Proprietà** :

    1. Espandere il nodo **(DataBindings)** .

    2. Fare clic sulla freccia accanto alla <xref:System.Windows.Forms.TextBox.Text%2A> proprietà.

         Si apre l'editor di tipo dell'interfaccia utente **DataSource** .

         Se un'origine dati è stata configurata in precedenza per il progetto o il form, verrà visualizzata.

3. Fare clic su **Aggiungi origine dati progetto** per connettersi ai dati e creare un'origine dati.

4. Nella pagina iniziale della **Configurazione guidata origine dati** fare clic su **Avanti**.

5. Nella pagina **scegliere un tipo di origine dati** selezionare **database**.

6. Nella pagina **Seleziona connessione dati** selezionare una connessione dati nell'elenco delle connessioni disponibili. Se la connessione dati desiderata non è disponibile, selezionare **nuova connessione** per creare una nuova connessione dati.

7. Selezionare **Sì, salva la connessione** per salvare la stringa di connessione nel file di configurazione dell'applicazione.

8. Selezionare gli oggetti database da inserire nell'applicazione. In questo caso, selezionare un campo in una tabella che si <xref:System.Windows.Forms.TextBox> desidera visualizzare.

9. Se si vuole, sostituire il nome predefinito del set di dati.

10. Scegliere **Fine**.

11. Nella finestra **Proprietà** fare clic sulla freccia accanto alla <xref:System.Windows.Forms.TextBox.Text%2A> proprietà. Nell'editor di tipo dell'interfaccia utente **DataSource** selezionare il nome del campo a cui associare <xref:System.Windows.Forms.TextBox> il.

     L'editor di tipo dell'interfaccia utente **DataSource** si chiude e <xref:System.Windows.Forms.BindingSource> il set di dati e l'adattatore della tabella specifici della connessione dati vengono aggiunti al form.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [Aggiungi nuova origine dati](/visualstudio/data-tools/add-new-data-sources)
- [Finestra Origini dati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))
