---
title: Roll forward del runtime per le distribuzioni di app autonome di .NET Core.
description: Informazioni sulle modifiche di dotnet publish per le distribuzioni autonome.
author: KathleenDollard
ms.date: 05/31/2018
ms.openlocfilehash: 22385c7b5d2bf87755fd51cd6268d21fe3431c74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75740792"
---
# <a name="self-contained-deployment-runtime-roll-forward"></a>Roll forward del runtime di distribuzione autonoma

Le [distribuzioni di applicazioni autonome](index.md) .NET Core includono sia le librerie che il runtime .NET Core. A partire da .NET Core 2.1 SDK (versione 2.1.300), le distribuzioni di applicazioni autonome [pubblicano nel computer il runtime della patch con il numero di versione più alto](https://github.com/dotnet/designs/pull/36). Per impostazione predefinita, [`dotnet publish`](../tools/dotnet-publish.md) per una distribuzione autonoma seleziona la versione più recente installata come parte dell'SDK nel computer di pubblicazione. Ciò consente l'esecuzione dell'applicazione distribuita con le correzioni, di sicurezza e di altro tipo, disponibili durante l'esecuzione di `publish`. L'applicazione deve essere ripubblicata per ottenere una nuova patch. Le applicazioni autonome vengono create specificando `-r <RID>` nel comando `dotnet publish` o specificando l'[identificatore di runtime](../rid-catalog.md) nel file di progetto (csproj o vbproj) o nella riga di comando.

## <a name="patch-version-roll-forward-overview"></a>Panoramica del roll forward della versione della patch

[`restore`](../tools/dotnet-restore.md)e [`build`](../tools/dotnet-build.md) [`publish`](../tools/dotnet-publish.md) sono `dotnet` comandi che possono essere eseguiti separatamente. La scelta del runtime fa parte dell'operazione di `restore`, non di `publish` o di `build`. Se si chiama `publish`, viene scelta la versione più recente della patch. Se si chiama `publish` con l'argomento `--no-restore`, non è possibile ottenere la versione desiderata della patch, perché in precedenza non può essere stato eseguito un comando `restore` con i nuovi criteri di pubblicazione dell'applicazione autonoma. In questo caso, viene generato un errore di compilazione con testo simile al seguente:

  "The project was restored using Microsoft.NETCore.App version 2.0.0, but with current settings, version 2.0.6 would be used instead. To resolve this issue, make sure the same settings are used for restore and for subsequent operations such as build or publish. Typically this issue can occur if the RuntimeIdentifier property is set during build or publish but not during restore" (Il progetto è stato ripristinato tramite Microsoft.NETCore.App versione 2.0.0, ma con le impostazioni correnti avrebbe dovuto essere usata la versione 2.0.6. Per risolvere il problema, assicurarsi che vengano usate le stesse impostazioni per il comando restore e per operazioni successive, quali build o publish. Questo problema si presenta, in genere, se la proprietà RuntimeIdentifier viene impostata durante l'operazione build o publish ma non durante restore).

> [!NOTE]
> I comandi `restore` e `build` possono essere eseguiti in modo implicito all'interno di un altro comando, ad esempio `publish`. Durante l'esecuzione in modo implicito all'interno di un altro comando, vengono specificati con contesto aggiuntivo, in modo che vengano generati gli artefatti corretti. Quando si esegue `publish` con un runtime (ad esempio, `dotnet publish -r linux-x64`), il comando `restore` implicito ripristina i pacchetti per il runtime linux-x64. Se chiamato in modo esplicito, `restore` non ripristina i pacchetti di runtime per impostazione predefinita, poiché non dispone di tale contesto.

## <a name="how-to-avoid-restore-during-publish"></a>Come evitare il ripristino durante la pubblicazione

L'esecuzione di `restore` all'interno dell'operazione `publish` può essere indesiderata per lo scenario. Per evitare l'esecuzione di `restore` durante la creazione di applicazioni autonome tramite `publish`, eseguire le operazioni seguenti:

- Impostare la proprietà `RuntimeIdentifiers` su un elenco delimitato da punto e virgola di tutti i [RID](../rid-catalog.md) da pubblicare.
- Impostare la proprietà `TargetLatestRuntimePatch` su `true`.

## <a name="no-restore-argument-with-dotnet-publish-options"></a>Argomento no-restore con le opzioni di dotnet publish

Se con lo stesso file di progetto si vogliono creare sia applicazioni autonome che [applicazioni dipendenti dal framework](index.md) e si vuole usare l'argomento `--no-restore` con `dotnet publish`, scegliere una delle alternative seguenti:

1. Preferire il comportamento dipendente dal framework. Se l'applicazione è dipendente dal framework, questo è il comportamento predefinito. Se l'applicazione è autonoma e può usare un runtime locale versione 2.1.0 senza patch, impostare `TargetLatestRuntimePatch` su `false` nel file di progetto.

2. Preferire il comportamento autonomo. Se l'applicazione è autonoma, questo è il comportamento predefinito. Se l'applicazione è dipendente dal framework e richiede l'installazione della patch più recente, impostare `TargetLatestRuntimePatch` su `true` nel file di progetto.

3. Assumere il controllo esplicito della versione del framework del runtime impostando `RuntimeFrameworkVersion` sulla versione specifica della patch nel file di progetto.
