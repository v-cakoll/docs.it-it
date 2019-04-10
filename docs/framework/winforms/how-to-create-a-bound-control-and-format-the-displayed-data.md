---
title: 'Procedura: Creare un controllo con associazione e formattare i dati visualizzati'
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: f7f1ed2fbca4ab8892cb6c439ae8841fa8828bf0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59302543"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a>Procedura: Creare un controllo con associazione e formattare i dati visualizzati
Con data binding in Windows Form, è possibile formattare i dati visualizzati in un controllo con associazione a dati mediante la **formattazione e associazione avanzata** nella finestra di dialogo.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-bind-a-control-and-format-the-displayed-data"></a>Per associare un controllo e formattare i dati visualizzati  
  
1. Effettuare una connessione a un'origine dati.  
  
     Per altre informazioni, vedere [ci si connette a un'origine dati](../data/adonet/connecting-to-a-data-source.md).  
  
2. Nel form selezionare il controllo e aprire la finestra Proprietà.  
  
3. Espandere la **(DataBindings)** proprietà, quindi nella **(avanzate)** fare clic sui puntini di sospensione (![schermata di VisualStudioEllipsesButton](./media/vbellipsesbutton.png " vbEllipsesButton")) per visualizzare il **formattazione e associazione avanzata** nella finestra di dialogo include un elenco completo delle proprietà per il controllo.  
  
4. Selezionare la proprietà si desidera eseguire l'associazione e quindi scegliere il **Binding** freccia.  
  
     Verrà visualizzato un elenco di origini dati disponibili.  
  
5. Espandere l'origine dati da associare fino a quando non vengono visualizzati i dati desiderati.  
  
     Se ad esempio si vuole associare il valore di una colonna in una tabella di set di dati, espandere il nome del set di dati, quindi espandere il nome della tabella per visualizzare i nomi delle colonne.  
  
6. Fare clic sul nome dell'elemento a cui effettuare il binding.  
  
7. Nel **formattare tipo** , scegliere il formato da applicare ai dati visualizzati nel controllo.  
  
     In ogni caso, è possibile specificare il valore visualizzato nel controllo se l'origine dati contiene <xref:System.DBNull>. In caso contrario, le opzioni variano leggermente, a seconda del tipo di formato scelto. La tabella seguente illustra i tipi di formato e le opzioni.  
  
    |Tipo di formato|Opzione di formattazione|  
    |-----------------|-----------------------|  
    |Nessuna formattazione|Nessuna opzione.|  
    |Numerico|Specificare il numero di posizioni decimali utilizzando **decimali** controllo di scorrimento.|  
    |Valuta|Specificare il numero di posizioni decimali utilizzando **decimali** controllo di scorrimento.|  
    |Data/Ora|Selezionare la data e ora da visualizzare selezionando uno degli elementi nel **tipo** casella di selezione.|  
    |Scientifico|Specificare il numero di posizioni decimali utilizzando **decimali** controllo di scorrimento.|  
    |Personalizzato|Specificare una stringa di formato personalizzata.<br /><br /> Per altre informazioni, vedere [Formattazione di tipi](../../standard/base-types/formatting-types.md). **Nota:**  Le stringhe di formato personalizzate non eseguono sempre correttamente il round trip tra l'origine dati e il controllo associato. Gestire invece l'evento <xref:System.Windows.Forms.Binding.Parse> o <xref:System.Windows.Forms.Binding.Format> per l'associazione e applicare la formattazione personalizzata nel codice di gestione degli eventi.|  
  
8. Fare clic su **OK** per chiudere la **formattazione e associazione avanzata** nella finestra di dialogo e tornare alla finestra Proprietà.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Creare un controllo con associazione semplice in un Windows Form](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [Convalida dell'input utente in Windows Form](user-input-validation-in-windows-forms.md)
- [Data binding di Windows Form](windows-forms-data-binding.md)
