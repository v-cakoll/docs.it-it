---
title: Provider di reflection (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: ef5ba300-6d7c-455e-a7bd-d0cc6d211ad4
ms.openlocfilehash: 0eeb223093d709cfe2722c2ad7cf622164eab32f
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568866"
---
# <a name="reflection-provider-wcf-data-services"></a>Provider di reflection (WCF Data Services)

Oltre a esporre i dati da un modello di dati tramite la Entity Framework, WCF Data Services possibile esporre dati non definiti rigidamente in un modello basato su entità. Il provider di reflection espone i dati nelle classi che restituiscono i tipi che implementano l'interfaccia <xref:System.Linq.IQueryable%601>. WCF Data Services USA la reflection per dedurre un modello di dati per queste classi e può convertire le query basate sull'indirizzo sulle risorse in query basate su LINQ (Language Integrated Query) sui tipi di <xref:System.Linq.IQueryable%601> esposti.

> [!NOTE]
> È possibile usare il metodo <xref:System.Linq.Queryable.AsQueryable%2A> per restituire un'interfaccia <xref:System.Linq.IQueryable%601> da una classe che implementa l'interfaccia <xref:System.Collections.Generic.IEnumerable%601>. In questo modo è possibile usare la maggior parte dei tipi di raccolte generiche come origine dati per il servizio dati.

Il provider di reflection supporta gerarchie di tipi. Per altre informazioni, vedere [procedura: creare un servizio dati tramite il provider di Reflection](create-a-data-service-using-rp-wcf-data-services.md).

## <a name="inferring-the-data-model"></a>Deduzione del modello di dati

Quando si crea il servizio dati, il modello di dati viene dedotto dal provider tramite reflection. Nell'elenco seguente viene illustrata la modalità di reflection usata dal provider per dedurre il modello di dati:

- Contenitore di entità: classe che espone i dati come proprietà che restituiscono un'istanza di <xref:System.Linq.IQueryable%601>. Quando si indirizza un modello di dati basato su reflection, il contenitore di entità rappresenta la radice del servizio. Per un determinato spazio dei nomi è supportata solo una classe contenitore di entità.

- Set di entità: le proprietà che restituiscono istanze di <xref:System.Linq.IQueryable%601> vengono gestite come set di entità. I set di entità possono essere indirizzati direttamente come risorse nella query. Solo una proprietà nel contenitore di entità può restituire un'istanza di <xref:System.Linq.IQueryable%601> di un determinato tipo.

- Tipi di entità: tipo `T` dell'oggetto <xref:System.Linq.IQueryable%601> restituito dal set di entità. Le classi che fanno parte di una gerarchia di ereditarietà vengono tradotte dal provider di reflection in una gerarchia di tipi di entità equivalenti.

- Chiavi di entità: ogni classe di dati che consiste in un tipo di entità deve disporre di una proprietà di chiave. Questa proprietà viene assegnata con l'attributo <xref:System.Data.Services.Common.DataServiceKeyAttribute> (`[DataServiceKeyAttribute]`).

    > [!NOTE]
    > È opportuno applicare l'attributo <xref:System.Data.Services.Common.DataServiceKeyAttribute> solo a una proprietà che può essere usata per identificare in modo univoco un'istanza del tipo di entità. Questo attributo viene ignorato se applicato a una proprietà di navigazione.

- Proprietà del tipo di entità: sono diverse dalle chiavi di entità, in quanto il provider di reflection gestisce le proprietà accessibili non relative a indicizzatori di una classe corrispondente a un tipo di entità nel modo seguente:

  - Se la proprietà restituisce un tipo primitivo, si presuppone che la proprietà sia una proprietà di un tipo di entità.

  - Se la proprietà restituisce un tipo che consiste anche in un tipo di entità, si presuppone che la proprietà sia una proprietà di navigazione che rappresenta il lato "uno" di una relazione molti-a-uno o uno-a-uno.

  - Se la proprietà restituisce un oggetto <xref:System.Collections.Generic.IEnumerable%601> di un tipo di entità, si presuppone che la proprietà sia una proprietà di navigazione che rappresenta il lato "molti" di una relazione uno-a-molti o molti-a-molti.

  - Se il tipo restituito della proprietà è un tipo valore, significa che la proprietà rappresenta un tipo complesso.

> [!NOTE]
> A differenza del modello di dati basato sul modello di entità relazionale, i modelli basati sul provider di reflection non sono i grado di interpretare dati relazionali. Per esporre i dati relazionali tramite WCF Data Services, è necessario utilizzare il Entity Framework.

## <a name="data-type-mapping"></a>Mapping dei tipi di dati

Quando un modello di dati viene derivato da classi di .NET Framework, i tipi primitivi inclusi nel modello di dati vengono mappati ai tipi di dati di .NET Framework nel modo seguente:

|Tipi di dati di .NET Framework|Tipo del modello di dati|
|------------------------------|---------------------|
|<xref:System.Byte> `[]`|`Edm.Binary`|
|<xref:System.Boolean>|`Edm.Boolean`|
|<xref:System.Byte>|`Edm.Byte`|
|<xref:System.DateTime>|`Edm.DateTime`|
|<xref:System.Decimal>|`Edm.Decimal`|
|<xref:System.Double>|`Edm.Double`|
|<xref:System.Guid>|`Edm.Guid`|
|<xref:System.Int16>|`Edm.Int16`|
|<xref:System.Int32>|`Edm.Int32`|
|<xref:System.Int64>|`Edm.Int64`|
|<xref:System.SByte>|`Edm.SByte`|
|<xref:System.Single>|`Edm.Single`|
|<xref:System.String>|`Edm.String`|

> [!NOTE]
> Viene eseguito il mapping dei tipi di valore nullable di .NET Framework agli stessi tipi del modello di dati dei tipi di valore corrispondenti a cui non è possibile assegnare valori Null.

## <a name="enabling-updates-in-the-data-model"></a>Abilitazione di aggiornamenti nel modello di dati

Per consentire aggiornamenti ai dati esposti tramite questo tipo di modello di dati, il provider di reflection definisce un'interfaccia <xref:System.Data.Services.IUpdatable>. Questa interfaccia indica al servizio dati la modalità da usare per rendere persistenti gli aggiornamenti ai tipi esposti. Per consentire aggiornamenti alle risorse definite dal modello di dati, la classe contenitore di entità deve implementare l'interfaccia <xref:System.Data.Services.IUpdatable>. Per un esempio di implementazione dell'interfaccia <xref:System.Data.Services.IUpdatable>, vedere [procedura: creare un servizio dati tramite un'origine dati LINQ to SQL](create-a-data-service-using-linq-to-sql-wcf.md).

Per fare in modo che gli aggiornamenti vengano propagati all'origine dati tramite il provider di reflection, l'interfaccia <xref:System.Data.Services.IUpdatable> richiede l'implementazione dei membri seguenti:

|Member|Descrizione|
|------------|-----------------|
|<xref:System.Data.Services.IUpdatable.AddReferenceToCollection%2A>|Fornisce la funzionalità che consente di aggiungere un oggetto a una raccolta di oggetti correlati accessibili da una proprietà di navigazione.|
|<xref:System.Data.Services.IUpdatable.ClearChanges%2A>|Fornisce la funzionalità che consente di annullare le modifiche in sospeso apportate ai dati.|
|<xref:System.Data.Services.IUpdatable.CreateResource%2A>|Fornisce la funzionalità che consente di creare una nuova risorsa nel contenitore specificato.|
|<xref:System.Data.Services.IUpdatable.DeleteResource%2A>|Fornisce la funzionalità che consente di eliminare una risorsa.|
|<xref:System.Data.Services.IUpdatable.GetResource%2A>|Fornisce la funzionalità che consente di recuperare una risorsa identificata da una query e un nome di tipo specifici.|
|<xref:System.Data.Services.IUpdatable.GetValue%2A>|Fornisce la funzionalità che consente di restituire il valore di una proprietà di una risorsa.|
|<xref:System.Data.Services.IUpdatable.RemoveReferenceFromCollection%2A>|Fornisce la funzionalità che consente di rimuovere un oggetto da una raccolta di oggetti correlati accessibili da una proprietà di navigazione.|
|<xref:System.Data.Services.IUpdatable.ResetResource%2A>|Fornisce la funzionalità che consente di aggiornare una risorsa specificata.|
|<xref:System.Data.Services.IUpdatable.ResolveResource%2A>|Fornisce la funzionalità che consente di restituire la risorsa rappresentata da un'istanza specifica dell'oggetto.|
|<xref:System.Data.Services.IUpdatable.SaveChanges%2A>|Fornisce la funzionalità che consente di salvare tutte le modifiche in sospeso.|
|<xref:System.Data.Services.IUpdatable.SetReference%2A>|Fornisce la funzionalità che consente di impostare un riferimento all'oggetto correlato tramite una proprietà di navigazione.|
|<xref:System.Data.Services.IUpdatable.SetValue%2A>|Fornisce la funzionalità che consente di impostare il valore della proprietà di una risorsa.|

## <a name="handling-concurrency"></a>Gestione della concorrenza

WCF Data Services supporta un modello di concorrenza ottimistica consentendo di definire un token di concorrenza per un'entità. Questo token di concorrenza, che include una o più proprietà dell'entità, viene usato dal servizio dati per determinare se si è verificata una modifica nei dati richiesti, aggiornati o eliminati. Quando i valori del token ottenuti dal valore eTag nella richiesta sono diversi da quelli correnti dell'entità, viene generata un'eccezione dal servizio dati. L'oggetto <xref:System.Data.Services.ETagAttribute> viene applicato a un tipo di entità per definire un token di concorrenza nel provider di reflection. Il token di concorrenza non può includere una proprietà della chiave o una proprietà di navigazione. Per ulteriori informazioni, vedere [aggiornamento del servizio dati](updating-the-data-service-wcf-data-services.md).

## <a name="using-linq-to-sql-with-the-reflection-provider"></a>Uso di LINQ to SQL con il provider di reflection

Poiché il Entity Framework è supportato in modo nativo per impostazione predefinita, è il provider di dati consigliato per l'utilizzo di dati relazionali con WCF Data Services. Per usare classi LINQ to SQL con un servizio dati, è tuttavia possibile usare il provider di reflection. I set di risultati <xref:System.Data.Linq.Table%601> restituiti dai metodi sul <xref:System.Data.Linq.DataContext> generato dalla LINQ to SQL Object Relational Designer (O/R Designer) implementano l'interfaccia <xref:System.Linq.IQueryable%601>. In questo modo il provider di reflection è in grado di accedere a questi metodi e di restituire i dati di entità da SQL Server tramite le classi LINQ to SQL generate. Poiché LINQ to SQL non implementa l'interfaccia <xref:System.Data.Services.IUpdatable>, sarà tuttavia necessario aggiungere una classe parziale che estenda la classe parziale <xref:System.Data.Linq.DataContext> esistente per aggiungere l'implementazione di <xref:System.Data.Services.IUpdatable>. Per altre informazioni, vedere [procedura: creare un servizio dati tramite un'origine dati LINQ to SQL](create-a-data-service-using-linq-to-sql-wcf.md).

## <a name="see-also"></a>Vedere anche

- [Provider di servizi dati](data-services-providers-wcf-data-services.md)
