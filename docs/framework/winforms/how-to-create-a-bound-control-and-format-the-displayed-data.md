---
title: 'Procedura: creare un controllo con associazione e formattare i dati visualizzati'
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: 9055ec9c4b646e0c86819e4e72db8ce20086bace
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a>Procedura: creare un controllo con associazione e formattare i dati visualizzati
Con l'associazione di dati di Windows Form, è possibile formattare i dati visualizzati in un controllo con associazione a dati mediante il **formattazione e associazione avanzata** la finestra di dialogo.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-bind-a-control-and-format-the-displayed-data"></a>Per associare un controllo e formattare i dati visualizzati  
  
1.  Effettuare una connessione a un'origine dati.  
  
     Per ulteriori informazioni, vedere [la connessione a un'origine dati](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).  
  
2.  Nel form selezionare il controllo e aprire la finestra Proprietà.  
  
3.  Espandere il **(DataBindings)** proprietà e quindi la **(avanzate)** fare clic sul pulsante con i puntini di sospensione (![schermata VisualStudioEllipsesButton] (../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) per visualizzare il **formattazione e associazione avanzata** nella finestra di dialogo dispone di un elenco completo delle proprietà per tale controllo.  
  
4.  Selezionare la proprietà che si desidera associare e quindi fare clic su di **associazione** freccia.  
  
     Verrà visualizzato un elenco di origini dati disponibili.  
  
5.  Espandere l'origine dati da associare fino a quando non vengono visualizzati i dati desiderati.  
  
     Se ad esempio si vuole associare il valore di una colonna in una tabella di set di dati, espandere il nome del set di dati, quindi espandere il nome della tabella per visualizzare i nomi delle colonne.  
  
6.  Fare clic sul nome dell'elemento a cui effettuare il binding.  
  
7.  Nel **il tipo di formato** fare clic sul formato da applicare ai dati visualizzati nel controllo.  
  
     In ogni caso, è possibile specificare il valore visualizzato nel controllo se l'origine dati contiene <xref:System.DBNull>. In caso contrario, le opzioni variano leggermente, a seconda del tipo di formato scelto. La tabella seguente illustra i tipi di formato e le opzioni.  
  
    |Tipo di formato|Opzione di formattazione|  
    |-----------------|-----------------------|  
    |Nessuna formattazione|Nessuna opzione.|  
    |Numerico|Specificare il numero di posizioni decimali utilizzando **decimali** controllo di scorrimento.|  
    |Valuta|Specificare il numero di posizioni decimali utilizzando **decimali** controllo di scorrimento.|  
    |Data/Ora|Selezionare come data e ora deve essere visualizzate selezionando uno degli elementi di **tipo** nella casella di selezione.|  
    |Scientifico|Specificare il numero di posizioni decimali utilizzando **decimali** controllo di scorrimento.|  
    |Custom (Personalizzati)|Specificare una stringa di formato personalizzata.<br /><br /> Per altre informazioni, vedere [Formattazione di tipi](../../../docs/standard/base-types/formatting-types.md). **Nota:** stringhe di formato personalizzate potrebbero non funzionare correttamente il round trip tra l'origine dati e il controllo associato. Gestire invece l'evento <xref:System.Windows.Forms.Binding.Parse> o <xref:System.Windows.Forms.Binding.Format> per il binding e applicare la formattazione personalizzata nel codice di gestione degli eventi.|  
  
8.  Fare clic su **OK** per chiudere la **formattazione e associazione avanzata** la finestra di dialogo e tornare alla finestra Proprietà.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Creare un controllo con associazione semplice in un Windows Form](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)  
 [Convalida dell'input utente in Windows Form](../../../docs/framework/winforms/user-input-validation-in-windows-forms.md)  
 [Data binding in Windows Form](../../../docs/framework/winforms/windows-forms-data-binding.md)
