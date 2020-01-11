---
title: Proiezioni di query (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- projection [WCF Data Services]
- WCF Data Services, projection
- query projection [WCF Data Services]
- WCF Data Services, querying
ms.assetid: a09f4985-9f0d-48c8-b183-83d67a3dfe5f
ms.openlocfilehash: 764ea6a77ba267e691d48bc72d17c02f6b3c18ca
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900968"
---
# <a name="query-projections-wcf-data-services"></a>Proiezioni di query (WCF Data Services)

La proiezione fornisce un meccanismo nel Open Data Protocol (OData) per ridurre la quantità di dati nel feed restituiti da una query specificando che nella risposta vengono restituite solo determinate proprietà di un'entità. Per ulteriori informazioni, vedere la sezione 4,8. Selezionare l'opzione query di sistema ($select) nelle [convenzioni URI (OData versione 2,0)](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/).

In questo argomento viene descritto come definire una proiezione di query e quali sono i requisiti per i tipi di entità e non entità. Viene inoltre illustrato come eseguire gli aggiornamenti dei risultati proiettati e creare i tipi proiettati e vengono elencate alcune considerazioni sulla proiezione.

## <a name="defining-a-query-projection"></a>Definizione di una proiezione di query

È possibile aggiungere una clausola di proiezione a una query usando l'opzione query `$select` in un URI o usando la clausola [Select](../../../csharp/language-reference/keywords/select-clause.md) ([SELECT](../../../visual-basic/language-reference/queries/select-clause.md) in Visual Basic) in una query LINQ. I dati di entità restituiti possono essere proiettati in tipi di entità o non entità sul client. Negli esempi di questo argomento viene illustrato l'uso della clausola `select` in una query LINQ.

> [!IMPORTANT]
> Quando si salvano gli aggiornamenti apportati ai tipi proiettati, potrebbe verificarsi una perdita di dati nel servizio dati. Per altre informazioni, vedere [considerazioni sulla proiezione](#considerations).

## <a name="requirements-for-entity-and-non-entity-types"></a>Requisiti per tipi di entità e non entità

I tipi di entità devono disporre di una o più proprietà Identity che costituiscono la chiave di entità. I tipi di entità vengono definiti nei client usando uno dei modi riportati di seguito.

- Tramite l'applicazione di <xref:System.Data.Services.Common.DataServiceKeyAttribute> o <xref:System.Data.Services.Common.DataServiceEntityAttribute> al tipo.

- Tramite la proprietà `ID` del tipo.

- Quando il tipo dispone di una proprietà denominata *type*`ID`, dove *Type* è il nome del tipo.

Per impostazione predefinita, quando si proiettano i risultati delle query in un tipo definito nel client, le proprietà richieste nella proiezione devono esistere nel tipo di client. Tuttavia, quando si specifica un valore `true` per la proprietà <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> di <xref:System.Data.Services.Client.DataServiceContext>, non è necessario che le proprietà specificate nella proiezione siano presenti nel tipo di client.

### <a name="making-updates-to-projected-results"></a>Aggiornamenti dei risultati proiettati

Quando si proiettano i risultati di una query in tipi di entità nel client, <xref:System.Data.Services.Client.DataServiceContext> può rilevare gli oggetti con aggiornamenti da restituire al servizio dati quando viene chiamato il metodo <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>. Tuttavia, gli aggiornamenti apportati ai dati proiettati in tipi di non entità nel client non possono essere restituiti al servizio dati, perché il servizio dati non può aggiornare l'entità corretta nell'origine dati senza una chiave per identificare l'istanza di entità. I tipi di non entità non vengono associati a <xref:System.Data.Services.Client.DataServiceContext>.

Quando una o più proprietà di un tipo di entità definito nel servizio dati non sono presenti nel tipo di client in cui viene proiettata l'entità, gli inserimenti di nuove entità non conterranno le proprietà mancanti. In questo caso, **anche** gli aggiornamenti apportati alle entità esistenti non includeranno le proprietà mancanti. Quando esiste un valore per la proprietà, l'aggiornamento ripristina il valore predefinito della proprietà, secondo quanto definito nell'origine dati.

### <a name="creating-projected-types"></a>Creazione di tipi proiettati

Nell'esempio seguente viene usata una query LINQ anonima che proietta le proprietà correlate all'indirizzo del tipo `Customers` in un nuovo tipo `CustomerAddress`, definito nel client ed attribuito come tipo di entità:

[!code-csharp[Astoria Northwind Client#SelectCustomerAddressSpecific](~/samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#selectcustomeraddressspecific)]
[!code-vb[Astoria Northwind Client#SelectCustomerAddressSpecific](~/samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#selectcustomeraddressspecific)]

In questo esempio, il modello dell'inizializzatore di oggetti viene usato per creare una nuova istanza del tipo `CustomerAddress`, anziché chiamare un costruttore. I costruttori non sono supportati in caso di proiezione in tipi di entità, ma possono essere usati durante la proiezione in tipi di non entità e anonimi. Poiché `CustomerAddress` è un tipo di entità, le modifiche possono essere apportate e restituite al servizio dati.

Inoltre, i dati del tipo `Customer` vengono proiettati in un'istanza del tipo di entità `CustomerAddress`, anziché di un tipo anonimo. La proiezione in tipi anonimi è supportata, ma i dati sono di sola lettura perché i tipi anonimi vengono considerati come tipi di non entità.

Le impostazioni <xref:System.Data.Services.Client.MergeOption> di <xref:System.Data.Services.Client.DataServiceContext> vengono usate per la risoluzione di identità durante la proiezione di query. Pertanto, se un'istanza del tipo `Customer` esiste già in <xref:System.Data.Services.Client.DataServiceContext>, un'istanza di `CustomerAddress` con la stessa identità seguirà le regole di risoluzione di identità specificate da <xref:System.Data.Services.Client.MergeOption>

Di seguito vengono descritti i comportamenti quando si proiettano i risultati in tipi di entità e non entità:

**Creazione di una nuova istanza proiettata tramite inizializzatori**

- Esempio:

   [!code-csharp[Astoria Northwind Client#ProjectWithInitializer](~/samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#projectwithinitializer)]
   [!code-vb[Astoria Northwind Client#ProjectWithInitializer](~/samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#projectwithinitializer)]

- Tipo di entità: supportato

- Tipo non entità: supportato

**Creazione di una nuova istanza proiettata tramite costruttori**

- Esempio:

   [!code-csharp[Astoria Northwind Client#ProjectWithConstructor](~/samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#projectwithconstructor)]
   [!code-vb[Astoria Northwind Client#ProjectWithConstructor](~/samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#projectwithconstructor)]

- Tipo di entità: viene generato un <xref:System.NotSupportedException>.

- Tipo non entità: supportato

**Uso della proiezione per trasformare un valore di proprietà**

- Esempio:

   [!code-csharp[Astoria Northwind Client#ProjectWithTransform](~/samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#projectwithtransform)]
   [!code-vb[Astoria Northwind Client#ProjectWithTransform](~/samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#projectwithtransform)]

- Tipo di entità: questa trasformazione non è supportata per i tipi di entità perché può causare confusione e potenzialmente sovrascrivere i dati nell'origine dati appartenente a un'altra entità. Viene generato un oggetto <xref:System.NotSupportedException>.

- Tipo non entità: supportato

<a name="considerations"></a>

## <a name="projection-considerations"></a>Considerazioni sulla proiezione

Alla definizione di una proiezione di query si applicano le considerazioni aggiuntive seguenti:

- Quando si definiscono feed personalizzati per il formato Atom, è necessario assicurarsi che tutte le proprietà dell'entità che dispongono di definizioni di mapping personalizzate vengano incluse nella proiezione. Se una proprietà di entità mappata non è inclusa nella proiezione potrebbe verificarsi una perdita di dati. Per altre informazioni, vedere [personalizzazione del feed](feed-customization-wcf-data-services.md).

- Quando vengono apportati inserimenti a un tipo proiettato che non contiene tutte le proprietà dell'entità nel modello di dati del servizio dati, le proprietà non incluse nella proiezione vengono impostate sui valori predefiniti nel client.

- Quando vengono apportati aggiornamenti a un tipo proiettato che non contiene tutte le proprietà dell'entità nel modello di dati del servizio dati, i valori esistenti non inclusi nella proiezione vengono sovrascritti con i valori predefiniti non inizializzati nel client.

- Quando una proiezione include una proprietà complessa, è necessario che venga restituito l'intero oggetto complesso.

- Quando una proiezione include una proprietà di navigazione, gli oggetti correlati vengono caricati in modo implicito senza necessità di chiamare il metodo <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>. Il metodo <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> non è supportato in una query proiettata.

- Le proiezioni di query eseguite nel client vengono convertite per l'uso dell'opzione query `$select` nell'URI della richiesta. Quando una query con proiezione viene eseguita su una versione precedente di WCF Data Services che non supporta l'opzione di query `$select`, viene restituito un errore. Questa situazione può inoltre verificarsi quando <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> di <xref:System.Data.Services.DataServiceBehavior> per il servizio dati viene impostato su un valore pari a <xref:System.Data.Services.Common.DataServiceProtocolVersion.V1>. Per ulteriori informazioni, vedere [controllo delle versioni del servizio dati](data-service-versioning-wcf-data-services.md).

Per altre informazioni, vedere [procedura: proiettare risultati di query](how-to-project-query-results-wcf-data-services.md).

## <a name="see-also"></a>Vedere anche

- [Esecuzione di query sul servizio dati](querying-the-data-service-wcf-data-services.md)
