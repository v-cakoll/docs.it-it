---
title: 'Procedura: convalidare file di mapping esterni e DBML'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c4c17b41f9bee3ce43b7627343fec2b5a69dbba8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a>Procedura: convalidare file di mapping esterni e DBML
I file di mapping esterno e i file con estensione dbml modificati devono essere convalidati in base alle rispettive definizioni dello schema. In questo argomento vengono descritti i passaggi per l'implementazione del processo di convalida per gli utenti di [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
### <a name="to-validate-a-dbml-or-xml-file"></a>Per convalidare un file con estensione dbml o un file XML  
  
1.  In Visual Studio **File** dal menu **aprire**, quindi fare clic su **File**.  
  
2.  Nel **Apri** finestra di dialogo fare clic su di dbml o un file di mapping XML che si desidera convalidare.  
  
     Il file viene aperto nel **Editor XML**.  
  
3.  Fare clic sulla finestra e quindi fare clic su **proprietà**.  
  
4.  Nel **proprietà** finestra, fare clic sui puntini di sospensione per il **schemi** proprietà.  
  
     Il **schemi XML** verrà visualizzata la finestra di dialogo.  
  
5.  Notare la definizione dello schema adatta allo scopo.  
  
    -   DbmlSchema.xsd è la definizione dello schema per la convalida di un file dbml. Per ulteriori informazioni, vedere [generazione di codice in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
    -   LinqToSqlMapping.xsd è la definizione dello schema per la convalida di un file di mapping XML esterno. Per ulteriori informazioni, vedere [Mapping esterno](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
6.  Nel **utilizzare** colonna della riga di definizione dello schema desiderato, fare clic per aprire la casella di riepilogo a discesa e quindi fare clic su **utilizzano questo schema**.  
  
     Il file di definizione dello schema è ora associato al file di mapping DBML o XML.  
  
     Assicurarsi che non siano selezionate altre definizioni dello schema.  
  
7.  Nel **vista** menu, fare clic su **elenco errori**.  
  
     Determinare se sono stati generati errori, avvisi o messaggi. In caso contrario, il file XML è valido per la definizione dello schema.  
  
## <a name="alternate-method-for-supplying-schema-definition"></a>Metodo alternativo per fornire la definizione dello schema  
 Se per qualche motivo XSD appropriato file non viene visualizzato nel **schemi XML** nella finestra di dialogo è possibile scaricare il file XSD da un argomento della Guida. I passaggi seguenti consentono di salvare il file scaricato nel formato Unicode richiesto dall'editor XML di [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].  
  
#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a>Per copiare un file di definizione dello schema da un argomento della Guida  
  
1.  Individuare l'argomento della Guida che contiene la definizione dello schema descritta in questo argomento.  
  
    -   Per i file con estensione dbml, vedere [generazione di codice in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
    -   Per i file di mapping esterno, vedere [Mapping esterno](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
2.  Fare clic su **Copia codice** per copiare il file di codice negli Appunti.  
  
3.  Avviare il Blocco note per creare un nuovo file.  
  
4.  Incollare il codice dagli Appunti nel file del Blocco note.  
  
5.  Nel blocco note di **File** menu, fare clic su **Salva con nome**.  
  
6.  Nel **codifica** , quindi selezionare **Unicode**.  
  
    > [!IMPORTANT]
    >  Questa selezione assicura che il file di testo sia preceduto dal marcatore dell'ordine di byte Unicode 16 (`FFFE`).  
  
7.  Nel **nome File** casella, creare un nome di file con estensione XSD.  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
