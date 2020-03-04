---
title: Analizzatori di .NET Framework-.NET
description: Informazioni su come usare gli analizzatori di .NET Framework nel pacchetto .NET Framework analizzatori per individuare e risolvere i rischi per la sicurezza
author: billwagner
ms.author: wiwagn
ms.date: 01/25/2018
ms.technology: dotnet-standard
ms.openlocfilehash: dd69671e709549fe0ad0f582e4d09b43f7321df2
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155997"
---
# <a name="the-net-framework-analyzer"></a>.NET Framework Analyzer

È possibile usare .NET Framework Analyzer per individuare potenziali problemi nel codice dell'applicazione basata su .NET Framework. L'analizzatore rileva i possibili problemi e suggerisce le relative soluzioni.

Viene eseguito in modo interattivo in Visual Studio durante la scrittura del codice o come parte di una compilazione CI. L'analizzatore deve essere aggiunto al progetto nell'ambiente di sviluppo non appena possibile. Prima si individuano i potenziali problemi nel codice, più facile sarà correggerli. Tuttavia, è possibile aggiungere l'analizzatore in qualsiasi momento nel ciclo di sviluppo. Individua eventuali problemi nel codice già esistente e segnala i nuovi problemi nel corso dello sviluppo.

## <a name="installing-and-configuring-the-net-framework-analyzer"></a>Installazione e configurazione di .NET Framework Analyzer

Gli analizzatori di .NET Framework devono essere installati come pacchetto NuGet in ogni progetto in cui si desidera eseguirli. Solo uno sviluppatore deve aggiungerli al progetto. Il pacchetto di analizzatori è una dipendenza del progetto e verrà eseguito nel computer di ogni sviluppatore non appena è disponibile la soluzione aggiornata.

.NET Framework Analyzer è disponibile nel pacchetto NuGet [Microsoft.NetFramework.Analyzers](https://www.nuget.org/packages/Microsoft.NetFramework.Analyzers/). Questo pacchetto contiene solo gli analizzatori specifici di .NET Framework, inclusi gli analizzatori della sicurezza. Nella maggior parte dei casi è opportuno usare il pacchetto NuGet [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers).
Il pacchetto aggregato FxCopAnalyzers contiene tutti gli analizzatori di framework inclusi nel pacchetto Framework.Analyzers, nonché i seguenti analizzatori:

- [Microsoft.CodeQuality.Analyzers](https://www.nuget.org/packages/Microsoft.CodeQuality.Analyzers): contiene indicazioni generali e linee guida per le API di .NET Standard
- [Microsoft.NetCore.Analyzers](https://www.nuget.org/packages/Microsoft.NetCore.Analyzers): contiene gli analizzatori specifici delle API di .NET Core.
- [Text.Analyzers](https://www.nuget.org/packages/Text.Analyzers): contiene materiale sussidiario per il testo incluso come codice, compresi i commenti.

Per installarlo, fare clic con il pulsante destro del mouse sul progetto e selezionare "Gestisci dipendenze".
In NuGet Package Explorer individuare "NetFramework Analyzer" o, se si preferisce, "Fx Cop Analyzer". Installare la versione stabile più recente in tutti i progetti della soluzione.

## <a name="using-the-net-framework-analyzer"></a>Uso di .NET Framework Analyzer

Dopo aver installato il pacchetto NuGet, compilare la soluzione. L'analizzatore segnalerà eventuali problemi individuati nella base di codici. I problemi vengono segnalati come avvisi nella finestra Elenco errori di Visual Studio, come illustrato nella figura seguente:

![Problemi segnalati dall'analizzatore del framework](./media/framework-analyzers-2.png)

Mentre si scrive il codice, possono apparire linee a zigzag sotto i potenziali problemi nel codice.
Passare il mouse su un problema per visualizzarne i dettagli e i suggerimenti utili per risolverlo, come illustrato nella figura seguente:

![report interattivo di problemi rilevati da framework analyzer](./media/framework-analyzers-1.png)

Gli analizzatori esaminano il codice nella soluzione e visualizzano un elenco di avvisi per i problemi riportati di seguito:

### <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058: I tipi non devono estendere tipi di base specifici

Esiste un numero limitato di tipi in .NET Framework da cui non è consigliabile derivare direttamente.

**Categoria:** Progettazione

**Gravità:** Avviso

Informazioni aggiuntive: [CA1058: I tipi non devono estendere tipi di base specifici](/visualstudio/code-quality/ca1058-types-should-not-extend-certain-base-types)

### <a name="ca2153-do-not-catch-corrupted-state-exceptions"></a>CA2153: Evitare la gestione delle eccezioni stato danneggiato

Usare le eccezioni stato danneggiato potrebbe mascherare gli errori, ad esempio le violazioni dell'accesso, e causare uno stato incoerente dell'esecuzione o rendere più semplice per gli utenti malintenzionati compromettere un sistema. In alternativa, gestire un set più specifico di tipi di eccezioni o generare di nuovo l'eccezione

**Categoria:** Sicurezza

**Gravità:** Avviso

Informazioni aggiuntive: [CA2153: Evitare la gestione delle eccezioni stato danneggiato](/visualstudio/code-quality/ca2153-avoid-handling-corrupted-state-exceptions)

### <a name="ca2229-implement-serialization-constructors"></a>CA2229: Implementare costruttori di serializzazione

L'analizzatore genera questo avviso quando si crea un tipo che implementa l'interfaccia <xref:System.Runtime.Serialization.ISerializable> ma non definisce il costruttore di serializzazione necessario. Per correggere una violazione di questa regola, implementare il costruttore di serializzazione. Per una classe sealed, rendere il costruttore privato; in caso contrario renderlo protetto. Il costruttore di serializzazione ha la firma seguente:

```csharp
public class MyItemType
{
    // The special constructor is used to deserialize values.
    public MyItemType(SerializationInfo info, StreamingContext context)
    {
        // implementation removed.
    }
}
```

**Categoria:** Uso

**Gravità:** Avviso

Informazioni aggiuntive: [CA2229: Implementare costruttori di serializzazione](/visualstudio/code-quality/ca2229-implement-serialization-constructors)

### <a name="ca2235-mark-all-non-serializable-fields"></a>CA2235: Contrassegnare tutti i campi non serializzabili

Un campo di istanza di un tipo non serializzabile viene dichiarato in un tipo serializzabile. È necessario contrassegnare in modo esplicito tale campo con <xref:System.NonSerializedAttribute> per risolvere il problema.

**Categoria:** Uso

**Gravità:** Avviso

Informazioni aggiuntive: [CA2235: Contrassegnare tutti i campi non serializzabili](/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields)

### <a name="ca2237-mark-iserializable-types-with-serializable"></a>CA2237: Contrassegnare i tipi ISerializable con SerializableAttribute

Per essere riconosciuti come serializzabili in Common Language Runtime, i tipi devono essere contrassegnati usando l'attributo <xref:System.SerializableAttribute> anche quando il tipo usa una routine di serializzazione personalizzata implementando l'interfaccia <xref:System.Runtime.Serialization.ISerializable>.

**Categoria:** Uso

**Gravità:** Avviso

Informazioni aggiuntive: [CA2237: Contrassegnare i tipi ISerializable con SerializableAttribute](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)

### <a name="ca3075-insecure-dtd-processing-in-xml"></a>CA3075: Elaborazione DTD non protetta in XML

Se si usano istanze di <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> non protette o si fa riferimento a origini di entità esterne, il parser può accettare un input non attendibile e divulgare informazioni riservate a utenti malintenzionati.  

**Categoria:** Sicurezza

**Gravità:** Avviso

Informazioni aggiuntive: [A3075: Elaborazione DTD non protetta in XML](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)

### <a name="ca5350-do-not-use-weak-cryptographic-algorithms"></a>CA5350: non usare algoritmi di crittografia vulnerabili

Gli algoritmi di crittografia si danneggiano nel tempo man mano che gli attacchi diventano più evoluti. In base al tipo e all'applicazione di questo algoritmo di crittografia, un'ulteriore riduzione dell'efficacia della crittografia può consentire agli utenti malintenzionati di leggere e manomettere i messaggi cifrati, falsificare le firme digitali, alterare il contenuto con hash o danneggiare in altro modo qualsiasi sistema crittografico basato su questo algoritmo. Per la crittografia, usare un algoritmo AES (AES-256, AES 192 e AES-128 sono accettabili) con una lunghezza di chiave maggiore di o uguale a 128 bit. Per l'hash, usare una funzione hash della famiglia SHA-2, ad esempio SHA-2 512, SHA-2 384 o SHA-2 256.

**Categoria:** Sicurezza

**Gravità:** Avviso

Informazioni aggiuntive: [CA5350: non usare algoritmi di crittografia vulnerabili](/visualstudio/code-quality/ca5350-do-not-use-weak-cryptographic-algorithms)

### <a name="ca5351-do-not-use-broken-cryptographic-algorithms"></a>CA5351: non usare algoritmi di crittografia interrotti

Esiste un attacco che rende fattibile a livello di calcolo l'interruzione di questo algoritmo. Ciò consente agli utenti malintenzionati di interrompere le garanzie di crittografia che per cui è stato progettato l'algoritmo. In base al tipo e all'applicazione di questo algoritmo di crittografia, in questo modo gli utenti malintenzionati possono leggere e manomettere i messaggi cifrati, falsificare le firme digitali, alterare il contenuto con hash o danneggiare in altro modo qualsiasi sistema crittografico basato su questo algoritmo. Per la crittografia, usare un algoritmo AES (AES-256, AES 192 e AES-128 sono accettabili) con una lunghezza di chiave maggiore di o uguale a 128 bit. Per l'hash, usare una funzione hash della famiglia SHA-2, ad esempio SHA512, SHA384 o SHA256. Per le firme digitali, usare RSA con una lunghezza di chiave maggiore di o uguale a 2048 bit o ECDSA con una lunghezza di chiave maggiore di o uguale a 256 bit.

**Categoria:** Sicurezza

**Gravità:** Avviso

Informazioni aggiuntive: [CA5351: non usare algoritmi di crittografia interrotti](/visualstudio/code-quality/ca5351)
