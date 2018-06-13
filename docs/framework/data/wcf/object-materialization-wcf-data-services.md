---
title: Materializzazione di oggetti (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, querying
ms.assetid: f0dbf7b0-0292-4e31-9ae4-b98288336dc1
ms.openlocfilehash: 54f8cc876b373fcfa8e8e514abf50111942de88c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365462"
---
# <a name="object-materialization-wcf-data-services"></a>Materializzazione di oggetti (WCF Data Services)
Quando si utilizza il **Aggiungi riferimento al servizio** finestra di dialogo per utilizzare un [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed in un'applicazione client basata su .NET Framework, le classi di dati equivalenti vengono generate per ogni tipo di entità nel modello di dati esposto dal feed. Per ulteriori informazioni, vedere [la generazione della libreria Client del servizio dati](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md). I dati di entità restituiti da una query vengono materializzati in un'istanza di una delle classi del servizio dati client generate. Per informazioni sulle opzioni di unione e la risoluzione di identità per gli oggetti rilevati, vedere [gestione del contesto del servizio dati](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md).  
  
 Anziché usare le classi di dati generate dallo strumento, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] consente inoltre di definire classi personalizzate del servizio dati client. In questo modo è possibile usare le proprie classi di dati, note anche come classi di dati POCO (Plain-Old CLR Object). Quando si utilizzano questi tipi di classi di dati personalizzati, è necessario attribuire la classe di dati con <xref:System.Data.Services.Common.DataServiceKeyAttribute> o <xref:System.Data.Services.Common.DataServiceEntityAttribute> e assicurarsi che i nomi del tipo ai nomi di tipo client corrispondenza nel modello di dati del servizio dati.  
  
 Dopo che la libreria riceve il messaggio di risposta query, i dati restituiti da materializza il [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in istanze di dati del client, le classi del servizio sono del tipo di query. Di seguito viene descritto il processo generale di materializzazione di tali oggetti.  
  
1.  La libreria client legge il tipo serializzato dall'elemento `entry` nel feed del messaggio di risposta e tenta di creare una nuova istanza del tipo corretto usando uno dei modi riportati di seguito.  
  
    -   Quando il nome del tipo dichiarato nel feed è identico al nome del tipo dell'oggetto <xref:System.Data.Services.Client.DataServiceQuery%601>, viene creata una nuova istanza di questo tipo usando il costruttore vuoto.  
  
    -   Quando il nome del tipo dichiarato nel feed è identico al nome del tipo derivato dal tipo dell'oggetto <xref:System.Data.Services.Client.DataServiceQuery%601>, viene creata una nuova istanza di questo tipo derivato usando il costruttore vuoto.  
  
    -   Quando il tipo dichiarato nel feed non corrisponde al tipo dell'oggetto <xref:System.Data.Services.Client.DataServiceQuery%601> o a qualsiasi tipo derivato, viene creata una nuova istanza del tipo sottoposto a query usando il costruttore vuoto.  
  
    -   Quando viene impostata la proprietà <xref:System.Data.Services.Client.DataServiceContext.ResolveType%2A>, viene chiamato il delegato fornito per eseguire l'override del mapping dei tipi basato sul nome predefinito e viene creata una nuova istanza del tipo restituito da <xref:System.Func%602>. Se questo delegato restituisce un valore Null, viene creata invece una nuova istanza del tipo sottoposto a query. Per supportare scenari di ereditarietà, è possibile che sia necessario eseguire l'override del mapping dei nomi dei tipi basato sul nome predefinito.  
  
2.  La libreria client legge il valore URI dall'elemento `id` di `entry` corrispondente al valore di identità dell'entità. Se per <xref:System.Data.Services.Client.DataServiceContext.MergeOption%2A> non viene usato il valore <xref:System.Data.Services.Client.MergeOption.NoTracking>, per rilevare l'oggetto in <xref:System.Data.Services.Client.DataServiceContext> viene usato il valore di identità. Il valore di identità viene inoltre usato per garantire la creazione di una sola istanza di entità, anche nel caso in cui un'entità venga restituita più volte nella risposta alla query.  
  
3.  La libreria client legge le proprietà dalla voce di feed e imposta le proprietà corrispondenti sull'oggetto appena creato. Quando in <xref:System.Data.Services.Client.DataServiceContext> è già presente un oggetto che dispone dello stesso valore di identità, le proprietà vengono impostate in base all'impostazione <xref:System.Data.Services.Client.MergeOption> di <xref:System.Data.Services.Client.DataServiceContext>. La risposta potrebbe contenere valori di proprietà per cui non è presente una proprietà corrispondente nel tipo client. In questo caso, l'azione dipende dal valore della proprietà <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> di <xref:System.Data.Services.Client.DataServiceContext>. Quando questa proprietà è impostata su `true`, la proprietà mancante viene ignorata. In caso contrario, viene generato un errore. Le proprietà vengono impostate come indicato di seguito:  
  
    -   Le proprietà scalari vengono impostate sul valore corrispondente nella voce del messaggio di risposta.  
  
    -   Le proprietà complesse vengono impostate su una nuova istanza di tipo complesso, impostata con le proprietà del tipo complesso dalla risposta.  
  
    -   Le proprietà di navigazione che restituiscono una raccolta di entità correlate vengono impostate su un'istanza di <xref:System.Collections.Generic.ICollection%601> nuova o esistente, dove `T` corrisponde al tipo dell'entità correlata. La raccolta è vuota se gli oggetti correlati non sono stati caricati in <xref:System.Data.Services.Client.DataServiceContext>. Per ulteriori informazioni, vedere [durante il caricamento di contenuto posticipato](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
        > [!NOTE]
        >  Quando le classi di dati client generate supportano l'associazione dati, le proprietà di navigazione restituiscono invece istanze della classe <xref:System.Data.Services.Client.DataServiceCollection%601>. Per ulteriori informazioni, vedere [Binding di dati a controlli](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).  
  
4.  Viene generato l'evento <xref:System.Data.Services.Client.DataServiceContext.ReadingEntity>.  
  
5.  La libreria client collega l'oggetto a <xref:System.Data.Services.Client.DataServiceContext>. Quando <xref:System.Data.Services.Client.MergeOption> è <xref:System.Data.Services.Client.MergeOption.NoTracking>, l'oggetto non viene collegato.  
  
## <a name="see-also"></a>Vedere anche  
 [Esecuzione di query sul servizio dati](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
 [Proiezioni di query](../../../../docs/framework/data/wcf/query-projections-wcf-data-services.md)
