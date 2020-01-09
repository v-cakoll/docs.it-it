---
title: Controllo delle versioni e librerie .NET
description: Procedure consigliate per il controllo delle versioni delle librerie .NET.
ms.date: 12/10/2018
ms.openlocfilehash: 8ed3217e39b1fe0f330a650ec72cda224866e207
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706413"
---
# <a name="versioning"></a>Versionamento

Una libreria software è raramente completa nella versione 1.0. Le librerie di buon livello si evolvono nel tempo, con l'aggiunta di funzionalità, la correzione di bug e il miglioramento delle prestazioni. È importante poter rilasciare nuove versioni di una libreria .NET, offrendo valore aggiuntivo con ogni versione, ma senza interrompere le funzionalità per gli utenti esistenti.

## <a name="breaking-changes"></a>Modifiche che causano un'interruzione

Per informazioni sulla gestione delle modifiche tra versioni che causano un'interruzione, vedere [Modifiche che causano un'interruzione](./breaking-changes.md).

## <a name="version-numbers"></a>Numeri di versione

Una libreria .NET dispone di molti modi per specificare una versione. Le versioni più importanti sono le seguenti:

### <a name="nuget-package-version"></a>Versione del pacchetto NuGet

La [versione del pacchetto NuGet](/nuget/reference/package-versioning) viene visualizzata in NuGet.org, lo strumento di gestione pacchetti NuGet di Visual Studio, e viene aggiunta al codice sorgente quando il pacchetto viene usato. La versione del pacchetto NuGet è il numero di versione che gli utenti generalmente vedono e a cui fanno riferimento quando parlano della versione di una libreria che stanno usando. La versione del pacchetto NuGet viene usata da NuGet e non ha alcun effetto sul comportamento in fase di esecuzione.

```xml
<PackageVersion>1.0.0-alpha1</PackageVersion>
```

L'identificatore del pacchetto NuGet combinato con la versione del pacchetto NuGet consente di identificare un pacchetto in NuGet. Ad esempio: `Newtonsoft.Json` + `11.0.2`. Un pacchetto con un suffisso è un versione non definitiva del pacchetto e ha un comportamento speciale che lo rende ideale per i test. Per altre informazioni, vedere [Pacchetti in versione non definitiva](./nuget.md#pre-release-packages).

Poiché la versione del pacchetto NuGet è la versione più visibile agli sviluppatori, è consigliabile aggiornarla tramite [Versionamento semantico (SemVer)](https://semver.org/). SemVer indica la rilevanza delle modifiche tra versioni e aiuta agli sviluppatori a prendere decisioni basate su informazioni aggiornate nella scelta della versione da usare. Il passaggio da `1.0` a `2.0`, ad esempio, indica la potenziale presenza di modifiche che causano un'interruzione.

**✔️ DA CONSIDERARE** Usare [SemVer 2.0.0](https://semver.org/) per la gestione versioni del pacchetto NuGet.

**✔️ USARE** la versione del pacchetto NuGet nella documentazione pubblica in quanto si tratta del numero di versione comunemente visualizzato dagli utenti.

**✔️ INCLUDERE** un suffisso di versione non definitiva quando si rilascia un pacchetto non stabile.

> Gli utenti devono scegliere esplicitamente di ottenere i pacchetti in versione non definitiva, quindi saranno consapevoli del fatto che il pacchetto non è completo.

### <a name="assembly-version"></a>Versione assembly

La versione dell'assembly viene usata da CLR in fase di esecuzione per scegliere la versione di un assembly da caricare. La selezione di un assembly tramite il controllo delle versioni si applica solo agli assembly con nome sicuro.

```xml
<AssemblyVersion>1.0.0.0</AssemblyVersion>
```

CLR .NET Framework in Windows richiede una corrispondenza esatta per il caricamento di un assembly con nome sicuro. Ad esempio, la compilazione di `Libary1, Version=1.0.0.0` è stata eseguita con un riferimento a `Newtonsoft.Json, Version=11.0.0.0`. .NET Framework caricherà solo la versione esatta `11.0.0.0`. Per caricare una versione diversa in fase di esecuzione, è necessario aggiungere un reindirizzamento di binding al file di configurazione dell'applicazione .NET.

La combinazione di nome sicuro e versione dell'assembly permette il [caricamento della versione dell'assembly in modalità strict](../assembly/versioning.md). Sebbene l'uso di un nome sicuro per una libreria offra diversi vantaggi, spesso comporta eccezioni in fase di esecuzione quando un assembly non viene trovato e sono necessari [reindirizzamenti di binding](../../framework/configure-apps/redirect-assembly-versions.md) in `app.config`/`web.config` per risolvere il problema. Il caricamento di assembly .NET Core è meno rigido e CLR .NET Core carica automaticamente gli assembly in fase di esecuzione con una versione più recente.

**✔️ VALUTARE** se includere solo una versione principale in AssemblyVersion.

> Ad esempio, sia per Library 1.0 che per Library 1.0.1 il valore di AssemblyVersion è `1.0.0.0`, mentre il valore di AssemblyVersion per Library 2.0 è `2.0.0.0`. Quando la versione dell'assembly viene modificata con meno frequenza, si riducono i reindirizzamenti di binding.

**✔️ VALUTARE** la possibilità di mantenere sincronizzati il numero di versione principale di AssemblyVersion e la versione del pacchetto NuGet.

> Il valore di AssemblyVersion è incluso in alcuni messaggi informativi visualizzati per l'utente, ad esempio, il nome dell'assembly e i nomi di tipi qualificati dall'assembly nei messaggi di eccezione. Mantenendo una relazione tra le versioni è possibile fornire agli sviluppatori più informazioni sulla versione in uso.

**❌ non** dispongono di un AssemblyVersion fisso.

> Sebbene evitando di modificare AssemblyVersion si eviti l'esigenza di reindirizzamenti di binding, ciò significa che è possibile installare solo un'unica versione dell'assembly nella Global Assembly Cache (GAC). Inoltre, le applicazioni che fanno riferimento all'assembly nella Global Assembly Cache non funzioneranno più se un'altra applicazione aggiorna l'assembly nella GAC con modifiche che causano un'interruzione.

### <a name="assembly-file-version"></a>Versione del file di assembly

La versione del file di assembly viene usata per visualizzare una versione di file in Windows e non ha alcun effetto sul comportamento in fase di esecuzione. L'impostazione di questa versione è facoltativa. Il valore è visibile nella finestra di dialogo Proprietà file in Esplora risorse:

```xml
<FileVersion>11.0.2.21924</FileVersion>
```

![Esplora risorse](./media/versioning/win-properties.png "Esplora risorse")

**✔️ VALUTARE** la possibilità di includere un numero di build di integrazione continua come revisione AssemblyFileVersion.

> Ad esempio, se si sta compilando la versione 1.0.0 del progetto e il numero di build di integrazione continua è 99, il valore di AssemblyFileVersion sarà 1.0.0.99.

**✔️ USARE** il formato `Major.Minor.Build.Revision` per la versione del file.

> La versione del file non viene mai usata da .NET, ma [Windows prevede che la versione del file](/windows/desktop/menurc/versioninfo-resource) usi il formato `Major.Minor.Build.Revision`. Se la versione non usa questo formato, viene generato un avviso.

### <a name="assembly-informational-version"></a>Versione informativa dell'assembly

La versione informativa dell'assembly viene usata per registrare informazioni aggiuntive sulla versione e non ha alcun effetto sul comportamento in fase di esecuzione. L'impostazione di questa versione è facoltativa. Se si usa un collegamento all'origine, questa versione verrà impostata in fase di compilazione con la versione del pacchetto NuGet più una versione del controllo del codice sorgente. Ad esempio, `1.0.0-beta1+204ff0a` include l'hash commit del codice sorgente da cui è stato compilato l'assembly. Per altre informazioni, vedere [Collegamento all'origine](./sourcelink.md).

```xml
<AssemblyInformationalVersion>The quick brown fox jumped over the lazy dog.</AssemblyInformationalVersion>
```

> [!NOTE]
> Le versioni precedenti di Visual Studio generano un avviso di compilazione se questa versione non usa il formato `Major.Minor.Build.Revision`. L'avviso può essere ignorato senza problemi.

**❌ evitare** di impostare manualmente la versione informativa dell'assembly.

> Lasciare che SourceLink generi automaticamente la versione contenente i metadati del controllo del codice sorgente e NuGet.

>[!div class="step-by-step"]
>[Precedente](publish-nuget-package.md)
>[Successivo](breaking-changes.md)
