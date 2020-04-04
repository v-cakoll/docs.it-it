---
title: Pubblicazione di applicazioni
description: Informazioni sui modi per pubblicare un'applicazione .NET Core.Learn about the ways to publish a .NET Core application. .NET Core può pubblicare app specifiche della piattaforma o multipiattaforma. Puoi pubblicare un'app come autonoma o come dipendente dal runtime. Ogni modalità influisce sulla modalità di esecuzione dell'app da parte di un utente.
ms.date: 04/01/2020
ms.openlocfilehash: a4e5f9fe048d40c751f582bd49732cb903202db4
ms.sourcegitcommit: 45cced471d59d5dac3f0c92abc9d4849716098a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/04/2020
ms.locfileid: "80665533"
---
# <a name="net-core-application-publishing-overview"></a>Panoramica della pubblicazione delle applicazioni .NET Core

Le applicazioni create con .NET Core possono essere pubblicate in due diverse modalità e la modalità influisce sulla modalità di esecuzione dell'app da parte di un utente.

La pubblicazione dell'app come *autonoma* produce un'applicazione che include il runtime e le librerie .NET Core, l'applicazione e le relative dipendenze. Gli utenti dell'applicazione possono eseguirlo in un computer in cui non è installato il runtime di .NET Core.

La pubblicazione dell'app come *dipendente dal runtime* (precedentemente nota come dipendente dal *framework*) produce un'applicazione che include solo l'applicazione stessa e le relative dipendenze. Gli utenti dell'applicazione devono installare separatamente il runtime di .NET Core.

Entrambi i modi di pubblicazione producono un eseguibile specifico della piattaforma per impostazione predefinita. Le applicazioni dipendenti dal runtime possono essere create senza un eseguibile e sono multipiattaforma.

Quando viene prodotto un eseguibile, è possibile specificare la piattaforma di destinazione con un identificatore di runtime (RID). Per ulteriori informazioni sui RID, vedere [.NET Core RID Catalog](../rid-catalog.md).

Nella tabella seguente vengono descritti i comandi usati per pubblicare un'app come dipendente dal runtime o indipendente per ogni versione dell'SDK:The following table outlines the commands used to publish an app as runtime-dependent or self-contained, per SDK version:

| Type                                                                                 | SDK 2.1 | SDK 3.x | Comando |
| -----------------------------------------------------------------------------------  | ------- | ------- | ------- |
| [eseguibile dipendente dal runtime](#publish-runtime-dependent) per la piattaforma corrente. |         | ✔️      | [`dotnet publish`](../tools/dotnet-publish.md) |
| [eseguibile dipendente dal runtime](#publish-runtime-dependent) per una piattaforma specifica.  |         | ✔️      | [`dotnet publish -r <RID> --self-contained false`](../tools/dotnet-publish.md) |
| [binario multipiattaforma dipendente dal runtime](#publish-runtime-dependent).               | ✔️      | ✔️      | [`dotnet publish`](../tools/dotnet-publish.md) |
| [file eseguibile indipendente](#publish-self-contained).                                | ✔️      | ✔️      | [`dotnet publish -r <RID>`](../tools/dotnet-publish.md) |

Per ulteriori informazioni, vedere [Comando di pubblicazione dotnet di .NET Core](../tools/dotnet-publish.md).

## <a name="produce-an-executable"></a>Produrre un eseguibile

Gli eseguibili non sono multipiattaforma. Sono specifici di un sistema operativo e dell'architettura della CPU. Quando pubblichi l'app e crei un eseguibile, puoi pubblicarla come [autonoma](#publish-self-contained) o [dipendente dal runtime.](#publish-runtime-dependent) La pubblicazione di un'app come autonoma include il runtime di .NET Core con l'app e gli utenti dell'app non devono preoccuparsi di installare .NET Core prima di eseguire l'app. Le app pubblicate come dipendenti dal runtime non includono il runtime e le librerie di .NET Core; sono incluse solo le dipendenze dell'app e di terze parti.

I seguenti comandi producono un eseguibile:

| Type                                                                                 | SDK 2.1 | SDK 3.x | Comando |
| ------------------------------------------------------------------------------------ | ------- | ------- | ------- |
| [eseguibile dipendente dal runtime](#publish-runtime-dependent) per la piattaforma corrente. |         | ✔️      | [`dotnet publish`](../tools/dotnet-publish.md) |
| [eseguibile dipendente dal runtime](#publish-runtime-dependent) per una piattaforma specifica.  |         | ✔️      | [`dotnet publish -r <RID> --self-contained false`](../tools/dotnet-publish.md) |
| [file eseguibile indipendente](#publish-self-contained).                                | ✔️      | ✔️      | [`dotnet publish -r <RID>`](../tools/dotnet-publish.md) |

## <a name="produce-a-cross-platform-binary"></a>Produrre un binario multipiattaforma

I file binari multipiattaforma vengono creati quando si pubblica l'app come [dipendente dal runtime,](#publish-runtime-dependent)sotto forma di file *dll.* Il file *dll* viene denominato in base al progetto. Ad esempio, se si dispone di un'app denominata **word_reader**, viene creato un file denominato *word_reader.dll.* Le app pubblicate in `dotnet <filename.dll>` questo modo vengono eseguite con il comando e possono essere eseguite su qualsiasi piattaforma.

I file binari multipiattaforma possono essere eseguiti su qualsiasi sistema operativo, purché il runtime .NET Core di destinazione sia già installato. Se il runtime .NET Core di destinazione non è installato, l'app può essere eseguita usando un runtime più recente se l'app è configurata per il rollforward. Per altre informazioni, consultate Avanzamento delle [app dipendenti dal runtime.](../versions/selection.md#framework-dependent-apps-roll-forward)

Il comando seguente produce un binario multipiattaforma:The following command produces a cross-platform binary:

| Type                                                                                 | SDK 2.1 | SDK 3.x | Comando |
| -----------------------------------------------------------------------------------  | ------- | ------- | ------- |
| [binario multipiattaforma dipendente dal runtime](#publish-runtime-dependent).               | ✔️      | ✔️      | [`dotnet publish`](../tools/dotnet-publish.md) |

## <a name="publish-runtime-dependent"></a>Pubblica dipendente dal runtime

Le app pubblicate come dipendenti dal runtime sono multipiattaforma e non includono il runtime .NET Core.Apps published as runtime-dependent are cross-platform and don't include the .NET Core runtime. L'utente dell'app deve installare il runtime di .NET Core.

La pubblicazione di un'app come dipendente dal runtime produce un [file binario multipiattaforma](#produce-a-cross-platform-binary) come file *dll* e un [eseguibile specifico della piattaforma](#produce-an-executable) destinato alla piattaforma corrente. La *dll* è multipiattaforma mentre l'eseguibile non lo è. Ad esempio, se si pubblica un'app denominata **word_reader** e Windows di destinazione, viene creato un eseguibile *word_reader.exe* insieme a *word_reader.dll*. Quando si ha come destinazione Linux o macOS, viene creato un *eseguibile word_reader* insieme a *word_reader.dll*. Per ulteriori informazioni sui RID, vedere [.NET Core RID Catalog](../rid-catalog.md).

> [!IMPORTANT]
> .NET Core SDK 2.1 non produce eseguibili specifici della piattaforma quando si pubblica un'app dipendente dal runtime.

Il file binario multipiattaforma dell'app `dotnet <filename.dll>` può essere eseguito con il comando e può essere eseguito su qualsiasi piattaforma. Se l'app usa un pacchetto NuGet con implementazioni specifiche della piattaforma, le dipendenze di tutte le piattaforme vengono copiate nella cartella di pubblicazione insieme all'app.

È possibile creare un eseguibile per `-r <RID> --self-contained false` una [`dotnet publish`](../tools/dotnet-publish.md) piattaforma specifica passando i parametri al comando. Quando `-r` il parametro viene omesso, viene creato un eseguibile per la piattaforma corrente. Tutti i pacchetti NuGet con dipendenze specifiche della piattaforma per la piattaforma di destinazione vengono copiati nella cartella di pubblicazione.

### <a name="advantages"></a>Vantaggi

- **Distribuzione di piccole dimensioni**\
Vengono distribuiti solo l'app e le relative dipendenze. Il runtime e le librerie di .NET Core vengono installati dall'utente e tutte le app condividono il runtime.

- **Multipiattaforma**\
La tua app e qualsiasi file . La libreria basata su NET viene eseguita su altri sistemi operativi. Non è necessario definire una piattaforma di destinazione per l'app. Per informazioni sul formato di file .NET, vedere [Formato file assembly .NET](../../standard/assembly/file-format.md).

- **Utilizza l'ultimo runtime con patch**\
L'app usa il runtime più recente (all'interno della famiglia principale e minore di destinazione di .NET Core) installato nel sistema di destinazione. Ciò significa che l'app usa automaticamente la versione con patch più recente del runtime di .NET Core. Questo comportamento predefinito può essere sottoposto a override. Per altre informazioni, consultate Avanzamento delle [app dipendenti dal runtime.](../versions/selection.md#framework-dependent-apps-roll-forward)

### <a name="disadvantages"></a>Svantaggi

- **Richiede la preinstallazione del runtime**\
L'app può essere eseguita solo se la versione di .NET Core di destinazione dell'app è già installata nel sistema host. È possibile configurare il comportamento di rollforward per l'app per richiedere una versione specifica di .NET Core o consentire una versione più recente di .NET Core.You can configure roll-forward behavior for the app to either require a specific version of .NET Core or allow a newer version of .NET Core. Per altre informazioni, consultate Avanzamento delle [app dipendenti dal runtime.](../versions/selection.md#framework-dependent-apps-roll-forward)

- **.NET Core può cambiare**\
È possibile che il runtime di .NET Core e le librerie vengano aggiornati nel computer in cui viene eseguita l'app. In rari casi, ciò può modificare il comportamento dell'app se si usano le librerie .NET Core, operazione pari alla maggior parte delle app. Puoi configurare il modo in cui l'app usa le versioni più recenti di .NET Core.You can configure how your app uses newer versions of .NET Core. Per altre informazioni, consultate Avanzamento delle [app dipendenti dal runtime.](../versions/selection.md#framework-dependent-apps-roll-forward)

Il seguente svantaggio si applica solo a .NET Core 2.1 SDK.

- **Usare `dotnet` il comando per avviare l'app**\
Gli utenti `dotnet <filename.dll>` devono eseguire il comando per avviare l'app. .NET Core 2.1 SDK non produce eseguibili specifici della piattaforma per le app pubblicate dipendenti dal runtime.

### <a name="examples"></a>Esempi

Pubblicare un'app dipendente dal runtime multipiattaforma. Viene creato un eseguibile destinato alla piattaforma corrente insieme al file *dll.*

```dotnet
dotnet publish
```

Pubblicare un'app dipendente dal runtime multipiattaforma. Viene creato un eseguibile Linux a 64 bit insieme al file *dll.* Questo comando non funziona con .NET Core SDK 2.1.

```dotnet
dotnet publish -r linux-x64 --self-contained false
```

## <a name="publish-self-contained"></a>Pubblicare autonomamente

La pubblicazione dell'app come autonoma produce un eseguibile specifico della piattaforma. La cartella di pubblicazione dell'output contiene tutti i componenti dell'app, incluse le librerie .NET Core e il runtime di destinazione. L'app è isolata da altre app .NET Core e non usa un runtime condiviso installato localmente. L'utente dell'app non è necessario per scaricare e installare .NET Core.

Il file binario eseguibile viene prodotto per la piattaforma di destinazione specificata. Ad esempio, se si dispone di un'app denominata **word_reader**e si pubblica un eseguibile autonomo per Windows, viene creato un file *word_reader.exe.* Pubblicazione per Linux o macOS, viene creato un *file word_reader.* La piattaforma e l'architettura `-r <RID>` di [`dotnet publish`](../tools/dotnet-publish.md) destinazione vengono specificate con il parametro per il comando. Per ulteriori informazioni sui RID, vedere [.NET Core RID Catalog](../rid-catalog.md).

Se l'app ha dipendenze specifiche della piattaforma, ad esempio un pacchetto NuGet contenente dipendenze specifiche della piattaforma, queste vengono copiate nella cartella di pubblicazione insieme all'app.

### <a name="advantages"></a>Vantaggi

- **Controllare la versione di .NET Core**\
È possibile controllare quale versione di .NET Core viene distribuita con l'app.

- **Targeting specifico della piattaforma**\
Poiché devi pubblicare l'app per ogni piattaforma, sai dove verrà eseguita l'app. Se .NET Core introduce una nuova piattaforma, gli utenti non possono eseguire l'app su tale piattaforma finché non si rilascia una versione destinata a tale piattaforma. Puoi testare la compatibilità dell'app prima che gli utenti esedano l'app nella nuova piattaforma.

### <a name="disadvantages"></a>Svantaggi

- **Distribuzioni più grandi**\
Poiché l'app include il runtime di .NET Core e tutte le dipendenze dell'app, le dimensioni del download e lo spazio sul disco rigido necessari sono maggiori di una versione [dipendente dal runtime.](#publish-runtime-dependent)

  > [!TIP]
  > È possibile ridurre le dimensioni della distribuzione nei sistemi Linux di circa 28 MB utilizzando la [*modalità invariante*](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md)di globalizzazione di .NET Core . In questo modo l'app deve gestire tutte le impostazioni cultura, ad esempio le [impostazioni cultura invarianti.](xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType)

- **Più difficile aggiornare la versione di .NET Core**\
.NET Core Runtime (distribuito con l'app) può essere aggiornato solo rilasciando una nuova versione dell'app. L'utente è responsabile della fornitura di una versione aggiornata dell'applicazione per le patch di sicurezza per il runtime di .NET Core.

### <a name="examples"></a>Esempi

Pubblicare un'app indipendente. Viene creato un eseguibile a 64 bit di macOS.

```dotnet
dotnet publish -r osx-x64
```

Pubblicare un'app indipendente. Viene creato un eseguibile di Windows a 64 bit.

```dotnet
dotnet publish -r win-x64
```

## <a name="see-also"></a>Vedere anche

- [Distribuzione di applicazioni .NET Core con l'interfaccia della riga di comando di .NET Core.Deploying .NET Core Apps with .NET Core CLI.](deploy-with-cli.md)
- [Distribuzione di applicazioni .NET Core con Visual Studio.Deploying .NET Core Apps with Visual Studio.](deploy-with-vs.md)
- [Pacchetti, Metapackage e Framework.](../packages.md)
- [Catalogo RID (Runtime IDentifier) di .NET Core.](../rid-catalog.md)
- [Selezionare la versione di .NET Core da utilizzare.](../versions/selection.md)
