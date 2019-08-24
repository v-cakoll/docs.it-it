---
title: 'Procedura: Creare un controllo con associazione e formattare i dati visualizzati'
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: 543775894994c518d6069f697b145cedaa7af5b0
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015655"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a>Procedura: Creare un controllo con associazione e formattare i dati visualizzati

Con Windows Forms data binding, è possibile formattare i dati visualizzati in un controllo associato a dati utilizzando la finestra di dialogo **formattazione e associazione avanzata** .

## <a name="to-bind-a-control-and-format-the-displayed-data"></a>Per associare un controllo e formattare i dati visualizzati

1. Effettuare una connessione a un'origine dati. Per ulteriori informazioni, vedere [connessione a un'origine dati](../data/adonet/connecting-to-a-data-source.md).

2. In Visual Studio selezionare il controllo nel form, quindi aprire la finestra **Proprietà** .

3. Espandere la proprietà **(DataBindings)** , quindi nella casella **(avanzate)** fare clic sul pulsante con i puntini![di sospensione (pulsante con i puntini di sospensione (...](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png)) nella finestra proprietà di Visual Studio) per visualizzare la **formattazione e la funzionalità avanzate.** Finestra di dialogo Binding, che include un elenco completo delle proprietà per il controllo.

4. Selezionare la proprietà che si desidera associare, quindi selezionare la freccia del **Binding** .

     Verrà visualizzato un elenco di origini dati disponibili.

5. Espandere l'origine dati da associare fino a quando non vengono visualizzati i dati desiderati.

     Se ad esempio si vuole associare il valore di una colonna in una tabella di set di dati, espandere il nome del set di dati, quindi espandere il nome della tabella per visualizzare i nomi delle colonne.

6. Consente di selezionare il nome di un elemento a cui eseguire l'associazione.

7. Nella casella **tipo formato** selezionare il formato che si desidera applicare ai dati visualizzati nel controllo.

     In ogni caso, è possibile specificare il valore visualizzato nel controllo se l'origine dati contiene <xref:System.DBNull>. In caso contrario, le opzioni variano leggermente, a seconda del tipo di formato scelto. La tabella seguente illustra i tipi di formato e le opzioni.

    |Tipo di formato|Opzione di formattazione|
    |-----------------|-----------------------|
    |Nessuna formattazione|Nessuna opzione.|
    |Numeric|Specificare il numero di posizioni decimali usando il controllo di scorrimento **posizioni** decimali.|
    |Currency|Specificare il numero di posizioni decimali usando il controllo di scorrimento **posizioni** decimali.|
    |Data/Ora|Selezionare la modalità di visualizzazione della data e dell'ora selezionando uno degli elementi nella casella di selezione **tipo** .|
    |Scientifico|Specificare il numero di posizioni decimali usando il controllo di scorrimento **posizioni** decimali.|
    |Personalizzato|Specificare una stringa di formato personalizzata.<br /><br /> Per altre informazioni, vedere [Formattazione di tipi](../../standard/base-types/formatting-types.md). **Nota:**  Le stringhe di formato personalizzate non eseguono sempre correttamente il round trip tra l'origine dati e il controllo associato. Gestire invece l'evento <xref:System.Windows.Forms.Binding.Parse> o <xref:System.Windows.Forms.Binding.Format> per l'associazione e applicare la formattazione personalizzata nel codice di gestione degli eventi.|

8. Selezionare **OK** per chiudere la finestra di dialogo **formattazione e associazione avanzata** e tornare al finestra Proprietà.

## <a name="see-also"></a>Vedere anche

- [Procedura: Creare un controllo con associazione semplice in un Windows Form](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [Convalida dell'input utente in Windows Form](user-input-validation-in-windows-forms.md)
- [Data binding in Windows Form](windows-forms-data-binding.md)
