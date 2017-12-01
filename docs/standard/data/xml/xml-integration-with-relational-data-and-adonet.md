---
title: Integrazione di XML con dati relazionali e ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f6ebb1a1-f2ca-49b9-92c9-0150940cf6e6
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5d03a0ca7518b06c08d98967d7c5ae864f1c04ac
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="xml-integration-with-relational-data-and-adonet"></a>Integrazione di XML con dati relazionali e ADO.NET
Il **XmlDataDocument** classe è una classe derivata del **XmlDocument**e contiene dati XML. Il vantaggio di **XmlDataDocument** è quello di fornire un bridge tra i dati relazionali sia gerarchici. Si tratta di un **XmlDocument** che può essere associato a un **DataSet** ed entrambe le classi possono sincronizzare le modifiche apportate ai dati contenuti in due classi. Un **XmlDocument** associato a un **DataSet** consente XML per l'integrazione con dati relazionali e non si dispone i dati rappresentati in un formato relazionale o XML. È possibile usare entrambe le rappresentazioni di dati, senza essere costretti a usarne una sola.  
  
 La possibilità di visualizzare i dati in due modi diversi comporta i seguenti vantaggi:  
  
-   È possibile associare la parte strutturata di un documento XML a un dataset per aumentare l'efficacia delle operazioni di archiviazione, indicizzazione e ricerca.  
  
-   Le operazioni di trasformazione, convalida e navigazione possono essere eseguite in modo efficace tramite un modello a cursore per i dati XML archiviati in modo relazionale. In alcuni casi può essere eseguita in modo più efficiente rispetto a strutture relazionali più se il codice XML viene archiviato un **XmlDocument** modello.  
  
-   Il **DataSet** può archiviare una parte del codice XML. Ovvero, è possibile utilizzare **XPath** o **XslTransform** per archiviare un **DataSet** solo gli elementi e attributi di interesse. Da qui, è possibile apportare modifiche al subset più piccolo, filtrato di dati, con le modifiche propagate in dati di dimensioni maggiori nel **XmlDataDocument**.  
  
 È anche possibile eseguire una trasformazione sui dati caricati nel **DataSet** da SQL Server. Un'altra opzione consiste nell'associare WinForm classi stile gestito di .NET Framework e i controlli Web Form a un **DataSet** compilato da un flusso di input XML.  
  
 Oltre a supportare **XslTransform**, un **XmlDataDocument** espone dati relazionali alle **XPath** convalida e query.  Fondamentalmente, per i dati relazionali sono disponibili tutti i servizi XML. Le funzionalità relazionali, quali l'associazione dei controlli, la chiamata CODEGEN e così via sono inoltre disponibili nelle proiezioni strutturate di XML, senza compromettere la fedeltà al documento XML.  
  
 Poiché **XmlDataDocument** viene ereditata da un **XmlDocument**, fornisce un'implementazione del DOM W3C. Il fatto che il **XmlDataDocument** è associato e archivia un subset dei dati all'interno di un **DataSet** non ne limitano né modificano l'utilizzo come un **XmlDocument** in alcun modo. Il codice scritto per utilizzare un **XmlDocument** funziona anche con un **XmlDataDocument**. Il **DataSet** consente una visualizzazione relazionale degli stessi dati mediante la definizione di tabelle, colonne, relazioni e vincoli, senza che sia un archivio dati utente autonomo, in memoria.  
  
 La figura seguente illustra le diverse associazioni dei dati XML con il **DataSet** e **XmlDataDocument**.  
  
 ![Set di dati XML](../../../../docs/standard/data/xml/media/xmlintegrationwithrelationaldataandadodotnet.gif "xmlIntegrationWithRelationalDataAndADOdotNet")  
  
 La figura mostra che i dati XML possono essere caricati direttamente in un **DataSet**, che consente la modifica diretta di XML in modo relazionale. O, il codice XML possono essere caricate in una classe derivata del DOM, ovvero il **XmlDataDocument**e successivamente caricati e sincronizzati con il **DataSet**. Poiché il **DataSet** e **XmlDataDocument** sono sincronizzati rispetto a un singolo set di dati, le modifiche apportate ai dati in un archivio si riflettono in altro archivio.  
  
 Il **XmlDataDocument** eredita tutte le funzionalità di modifica e di navigazione dal **XmlDocument**. Vi sono casi quando si utilizza il **XmlDataDocument** le relative funzionalità ereditate, sincronizzato con un **DataSet**, è un'opzione più appropriata, anziché caricare i dati XML direttamente nel **setdidati**. Nella tabella seguente mostra gli elementi da considerare nella scelta del metodo da utilizzare per caricare il **DataSet**.  
  
|Quando caricare i dati XML direttamente in un DataSet|Quando sincronizzare una classe XmlDataDocument con un DataSet|  
|----------------------------------------------|-----------------------------------------------------------|  
|Query di dati di **set di dati** sono più semplici usando SQL anziché XPath.|Query XPath sono necessarie nei dati di **DataSet**.|  
|Non è necessario conservare l'ordine degli elementi nel documento XML di origine.|È necessario conservare l'ordine degli elementi nel documento XML di origine.|  
|Non è necessario conservare gli spazi vuoti tra gli elementi e la formattazione nel documento XML di origine.|È necessario conservare gli spazi vuoti tra gli elementi e la formattazione nel documento XML di origine.|  
  
 Se il caricamento e la scrittura del codice XML direttamente in e da un **DataSet** risolve le proprie esigenze, vedere [durante il caricamento di un set di dati da XML](../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) e [scrittura di un DataSet come dati XML](../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Se il caricamento di **DataSet** da un **XmlDataDocument** risolve le proprie esigenze, vedere [sincronizzazione un XmlDataDocument un](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di XML in un set di dati](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
