---
title: 'Procedura: Convalidare file di mapping esterni e DBML'
ms.date: 03/30/2017
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
ms.openlocfilehash: 83a26f22495c849aa00143ca36b63fa147120c28
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59310239"
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a>Procedura: Convalidare file di mapping esterni e DBML
I file di mapping esterno e i file con estensione dbml modificati devono essere convalidati in base alle rispettive definizioni dello schema. In questo argomento offre agli utenti di Visual Studio con i passaggi per implementare il processo di convalida.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
### <a name="to-validate-a-dbml-or-xml-file"></a>Per convalidare un file con estensione dbml o un file XML  
  
1. In Visual Studio **File** dal menu **Open**, quindi fare clic su **File**.  
  
2. Nel **Apri File** finestra di dialogo, scegliere il. dbml o un file di mapping XML che si desidera convalidare.  
  
     Aprire il file nei **Editor XML**.  
  
3. Fare doppio clic la finestra e quindi fare clic su **proprietà**.  
  
4. Nel **delle proprietà** finestra, fare clic sui puntini di sospensione per il **schemi** proprietà.  
  
     Il **schemi XML** verrà visualizzata la finestra di dialogo.  
  
5. Notare la definizione dello schema adatta allo scopo.  
  
    -   DbmlSchema.xsd è la definizione dello schema per la convalida di un file dbml. Per altre informazioni, vedere [generazione di codice in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
    -   LinqToSqlMapping.xsd è la definizione dello schema per la convalida di un file di mapping XML esterno. Per altre informazioni, vedere [Mapping esterno](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
6. Nel **utilizzo** colonna della riga di definizione dello schema desiderata, fare clic per aprire la casella di riepilogo a discesa e quindi fare clic su **utilizzano questo schema**.  
  
     Il file di definizione dello schema è ora associato al file di mapping DBML o XML.  
  
     Assicurarsi che non siano selezionate altre definizioni dello schema.  
  
7. Nel **View** menu, fare clic su **elenco errori**.  
  
     Determinare se sono stati generati errori, avvisi o messaggi. In caso contrario, il file XML è valido per la definizione dello schema.  
  
## <a name="alternate-method-for-supplying-schema-definition"></a>Metodo alternativo per fornire la definizione dello schema  
 Se per qualche motivo il XSD appropriato file non viene visualizzato nei **schemi XML** nella finestra di dialogo è possibile scaricare il file con estensione XSD da un argomento della Guida. La procedura seguente consente di salvare il file scaricato in formato Unicode richiesto dall'Editor XML di Visual Studio.  
  
#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a>Per copiare un file di definizione dello schema da un argomento della Guida  
  
1. Individuare l'argomento della Guida che contiene la definizione dello schema descritta in questo argomento.  
  
    -   Per i file con estensione dbml, vedere [generazione di codice in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
    -   Per i file di mapping esterno, vedere [Mapping esterno](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
2. Fare clic su **Copia codice** per copiare il file di codice negli Appunti.  
  
3. Avviare il Blocco note per creare un nuovo file.  
  
4. Incollare il codice dagli Appunti nel file del Blocco note.  
  
5. Nel blocco note **File** menu, fare clic su **Salva con nome**.  
  
6. Nel **Encoding** , quindi selezionare **Unicode**.  
  
    > [!IMPORTANT]
    >  Questa selezione assicura che il file di testo sia preceduto dal marcatore dell'ordine di byte Unicode 16 (`FFFE`).  
  
7. Nel **nome del File** casella, creare un nome di file con estensione XSD.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
