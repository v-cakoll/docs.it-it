---
title: Pubblicazione dell'applicazione
description: Informazioni sulle modalità di pubblicazione di un'applicazione .NET Core. .NET Core può pubblicare app specifiche della piattaforma o multipiattaforma. È possibile pubblicare un'app come indipendente o dipendente dal runtime. Ogni modalità influiscono sul modo in cui un utente esegue l'app.
ms.date: 04/01/2020
ms.openlocfilehash: 201363ad314373ec3be44eb8496f92a8e0c8e418
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164932"
---
# <a name="net-core-application-publishing-overview"></a>Panoramica della pubblicazione di applicazioni .NET Core

Le applicazioni create con .NET Core possono essere pubblicate in due modalità diverse e la modalità influiscono sulla modalità di esecuzione dell'app da parte di un utente.

La pubblicazione dell'app come *autonoma* produce un'applicazione che include il runtime e le librerie di .NET Core e l'applicazione e le relative dipendenze. Gli utenti dell'applicazione possono eseguirla in un computer in cui non è installato il runtime di .NET Core.

La pubblicazione dell'app come *dipendente dal runtime* (precedentemente noto come *dipendente dal Framework*) produce un'applicazione che include solo l'applicazione stessa e le relative dipendenze. Gli utenti dell'applicazione devono installare separatamente il runtime di .NET Core.

Per impostazione predefinita, entrambe le modalità di pubblicazione producono un eseguibile specifico della piattaforma. Le applicazioni dipendenti dal runtime possono essere create senza un eseguibile e queste applicazioni sono multipiattaforma.

Quando viene prodotto un file eseguibile, è possibile specificare la piattaforma di destinazione con un identificatore di runtime (RID). Per ulteriori informazioni su rid, vedere il [Catalogo dei RID di .NET Core](../rid-catalog.md).

La tabella seguente descrive i comandi usati per pubblicare un'app come dipendente dal runtime o autonomo, per versione SDK:

| Type                                                                                 | SDK 2.1 | SDK 3. x | Comando |
| -----------------------------------------------------------------------------------  | ------- | ------- | ------- |
| [eseguibile dipendente dal runtime](#publish-runtime-dependent) per la piattaforma corrente. |         | ✔️      | [`dotnet publish`](../tools/dotnet-publish.md) |
| [eseguibile dipendente dal runtime](#publish-runtime-dependent) per una piattaforma specifica.  |         | ✔️      | [`dotnet publish -r <RID> --self-contained false`](../tools/dotnet-publish.md) |
| [binario multipiattaforma dipendente dal runtime](#publish-runtime-dependent).               | ✔️      | ✔️      | [`dotnet publish`](../tools/dotnet-publish.md) |
| [eseguibile indipendente](#publish-self-contained).                                | ✔️      | ✔️      | [`dotnet publish -r <RID>`](../tools/dotnet-publish.md) |

Per altre informazioni, vedere [comando DotNet Publish di .NET Core](../tools/dotnet-publish.md).

## <a name="produce-an-executable"></a>Produrre un eseguibile

Gli eseguibili non sono multipiattaforma. Sono specifici di un sistema operativo e di un'architettura della CPU. Quando si pubblica l'app e si crea un eseguibile, è possibile pubblicare l'app come dipendente [autonomo](#publish-self-contained) o di [Runtime](#publish-runtime-dependent). La pubblicazione di un'app come indipendente include il runtime di .NET Core con l'app e gli utenti dell'app non devono preoccuparsi di installare .NET Core prima di eseguire l'app. Le app pubblicate come dipendenti dal runtime non includono il runtime e le librerie di .NET Core. sono incluse solo l'app e le dipendenze di terze parti.

I comandi seguenti producono un eseguibile:

| Type                                                                                 | SDK 2.1 | SDK 3. x | Comando |
| ------------------------------------------------------------------------------------ | ------- | ------- | ------- |
| [eseguibile dipendente dal runtime](#publish-runtime-dependent) per la piattaforma corrente. |         | ✔️      | [`dotnet publish`](../tools/dotnet-publish.md) |
| [eseguibile dipendente dal runtime](#publish-runtime-dependent) per una piattaforma specifica.  |         | ✔️      | [`dotnet publish -r <RID> --self-contained false`](../tools/dotnet-publish.md) |
| [eseguibile indipendente](#publish-self-contained).                                | ✔️      | ✔️      | [`dotnet publish -r <RID>`](../tools/dotnet-publish.md) |

## <a name="produce-a-cross-platform-binary"></a>Produrre un file binario multipiattaforma

I file binari multipiattaforma vengono creati quando si pubblica l'app come [dipendente dal runtime](#publish-runtime-dependent), sotto forma di file *dll* . Il nome del file *dll* viene eseguito dopo il progetto. Se, ad esempio, si dispone di un'app denominata **word_reader**, viene creato un file denominato *word_reader.dll* . Le app pubblicate in questo modo vengono eseguite con il `dotnet <filename.dll>` comando e possono essere eseguite su qualsiasi piattaforma.

I file binari multipiattaforma possono essere eseguiti in qualsiasi sistema operativo, purché il runtime di .NET Core di destinazione sia già installato. Se il runtime di .NET Core di destinazione non è installato, l'app può essere eseguita usando un runtime più recente se l'app è configurata per il rollforward. Per altre informazioni, vedere [rollforward delle app dipendenti dal runtime](../versions/selection.md#framework-dependent-apps-roll-forward).

Il comando seguente genera un file binario multipiattaforma:

| Type                                                                                 | SDK 2.1 | SDK 3. x | Comando |
| -----------------------------------------------------------------------------------  | ------- | ------- | ------- |
| [binario multipiattaforma dipendente dal runtime](#publish-runtime-dependent).               | ✔️      | ✔️      | [`dotnet publish`](../tools/dotnet-publish.md) |

## <a name="publish-runtime-dependent"></a>Pubblicazione dipendente dal runtime

Le app pubblicate come dipendenti dal runtime sono multipiattaforma e non includono il runtime di .NET Core. L'utente dell'app è necessario per installare il runtime di .NET Core.

La pubblicazione di un'app come dipendente dal runtime produce un file [binario multipiattaforma](#produce-a-cross-platform-binary) come file *dll* e un file [eseguibile specifico della piattaforma](#produce-an-executable) destinato alla piattaforma corrente. La *dll* è multipiattaforma mentre l'eseguibile non lo è. Se ad esempio si pubblica un'app denominata **word_reader** e le finestre di destinazione, viene creato un file eseguibile *word_reader.exe* insieme a *word_reader.dll*. Quando la destinazione è Linux o macOS, viene creato un file eseguibile *word_reader* insieme al *word_reader.dll*. Per ulteriori informazioni su rid, vedere il [Catalogo dei RID di .NET Core](../rid-catalog.md).

> [!IMPORTANT]
> .NET Core SDK 2,1 non produce eseguibili specifici della piattaforma quando si pubblica un'app dipendente dal runtime.

Il file binario multipiattaforma dell'app può essere eseguito con il `dotnet <filename.dll>` comando e può essere eseguito su qualsiasi piattaforma. Se l'app usa un pacchetto NuGet con implementazioni specifiche della piattaforma, le dipendenze di tutte le piattaforme vengono copiate nella cartella di pubblicazione insieme all'app.

È possibile creare un eseguibile per una piattaforma specifica passando i `-r <RID> --self-contained false` parametri al [`dotnet publish`](../tools/dotnet-publish.md) comando. Quando il `-r` parametro viene omesso, viene creato un eseguibile per la piattaforma corrente. Tutti i pacchetti NuGet con dipendenze specifiche della piattaforma per la piattaforma di destinazione vengono copiati nella cartella di pubblicazione.

### <a name="advantages"></a>Vantaggi

- **Distribuzione di piccole dimensioni**\
Verranno distribuite solo l'app e le relative dipendenze. Il runtime e le librerie di .NET Core vengono installati dall'utente e tutte le app condividono il Runtime.

- **Multipiattaforma**\
L'app e qualsiasi. La libreria basata su rete viene eseguita in altri sistemi operativi. Non è necessario definire una piattaforma di destinazione per l'app. Per informazioni sul formato di file .NET, vedere [formato di file di assembly .NET](../../standard/assembly/file-format.md).

- **Usa il runtime con patch più recente**\
L'app usa il runtime più recente (all'interno della famiglia principale-secondaria di .NET Core) installato nel sistema di destinazione. Ciò significa che l'app usa automaticamente la versione più recente con patch del runtime di .NET Core. Questo comportamento predefinito può essere sottoposto a override. Per altre informazioni, vedere [rollforward delle app dipendenti dal runtime](../versions/selection.md#framework-dependent-apps-roll-forward).

### <a name="disadvantages"></a>Svantaggi

- **Richiede la pre-installazione del runtime**\
L'app può essere eseguita solo se la versione di .NET Core di destinazione dell'app è già installata nel sistema host. È possibile configurare il comportamento di rollforward per l'app in modo che sia necessaria una versione specifica di .NET Core o consentire una versione più recente di .NET Core. Per altre informazioni, vedere [rollforward delle app dipendenti dal runtime](../versions/selection.md#framework-dependent-apps-roll-forward).

- **.NET Core può cambiare**\
È possibile che le librerie e il runtime di .NET Core vengano aggiornati nel computer in cui viene eseguita l'app. In rari casi, questo potrebbe modificare il comportamento dell'app se si usano le librerie .NET Core, che la maggior parte delle app. È possibile configurare il modo in cui l'app usa le versioni più recenti di .NET Core. Per altre informazioni, vedere [rollforward delle app dipendenti dal runtime](../versions/selection.md#framework-dependent-apps-roll-forward).

Gli svantaggi seguenti si applicano solo a .NET Core 2,1 SDK.

- **Usare il `dotnet` comando per avviare l'app**\
Per avviare l'app, gli utenti devono eseguire il `dotnet <filename.dll>` comando. .NET Core 2,1 SDK non produce eseguibili specifici della piattaforma per le app che dipendono dal runtime.

### <a name="examples"></a>Esempi

Pubblicare un'app dipendente dal runtime multipiattaforma. Un eseguibile destinato alla piattaforma corrente viene creato insieme al file *dll* .

```dotnet
dotnet publish
```

Pubblicare un'app dipendente dal runtime multipiattaforma. Insieme al file *dll* viene creato un eseguibile Linux a 64 bit. Questo comando non funziona con .NET Core SDK 2,1.

```dotnet
dotnet publish -r linux-x64 --self-contained false
```

## <a name="publish-self-contained"></a>Pubblicazione indipendente

La pubblicazione dell'app come indipendente produce un eseguibile specifico della piattaforma. La cartella di pubblicazione di output contiene tutti i componenti dell'app, incluse le librerie .NET Core e il runtime di destinazione. L'app è isolata dalle altre app .NET Core e non usa un runtime condiviso installato localmente. L'utente dell'app non è necessario per scaricare e installare .NET Core.

Il file binario eseguibile viene prodotto per la piattaforma di destinazione specificata. Se, ad esempio, si dispone di un'app denominata **word_reader**e si pubblica un eseguibile autonomo per Windows, viene creato un file di *word_reader.exe* . Pubblicazione per Linux o macOS, viene creato un file di *word_reader* . La piattaforma e l'architettura di destinazione vengono specificate con il `-r <RID>` parametro per il [`dotnet publish`](../tools/dotnet-publish.md) comando. Per ulteriori informazioni su rid, vedere il [Catalogo dei RID di .NET Core](../rid-catalog.md).

Se l'app ha dipendenze specifiche della piattaforma, ad esempio un pacchetto NuGet contenente dipendenze specifiche della piattaforma, queste vengono copiate nella cartella publish insieme all'app.

### <a name="advantages"></a>Vantaggi

- **Controllare la versione di .NET Core**\
È possibile controllare la versione di .NET Core distribuita con l'app.

- **Targeting specifico della piattaforma**\
Poiché è necessario pubblicare l'app per ogni piattaforma, si sa dove viene eseguita l'app. Se .NET Core introduce una nuova piattaforma, gli utenti non possono eseguire l'app su tale piattaforma finché non viene rilasciata una versione destinata alla piattaforma. È possibile testare l'app per i problemi di compatibilità prima che gli utenti eseguano l'app nella nuova piattaforma.

### <a name="disadvantages"></a>Svantaggi

- **Distribuzioni di dimensioni maggiori**\
Poiché l'app include il runtime di .NET Core e tutte le dipendenze dell'app, le dimensioni del download e lo spazio su disco rigido richiesto sono maggiori di una versione [dipendente dal runtime](#publish-runtime-dependent) .

  > [!TIP]
  > È possibile ridurre le dimensioni della distribuzione nei sistemi Linux di circa 28 MB usando la [*modalità invariante di globalizzazione*](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md)di .NET Core. Questa operazione impone all'app di trattare tutte le impostazioni [cultura come la lingua inglese](xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType).

- **Più difficile aggiornare la versione di .NET Core**\
Il runtime di .NET Core (distribuito con l'app) può essere aggiornato solo rilasciando una nuova versione dell'app. Si è responsabili della fornitura di una versione aggiornata dell'applicazione per le patch di sicurezza al runtime di .NET Core.

### <a name="examples"></a>Esempi

Pubblicare un'app indipendente. Viene creato un file eseguibile macOS a 64 bit.

```dotnet
dotnet publish -r osx-x64
```

Pubblicare un'app indipendente. Viene creato un file eseguibile di Windows a 64 bit.

```dotnet
dotnet publish -r win-x64
```

## <a name="see-also"></a>Vedere anche

- [Distribuzione di app .NET Core con interfaccia della riga di comando di .NET Core.](deploy-with-cli.md)
- [Distribuzione di app .NET Core con Visual Studio.](deploy-with-vs.md)
- [Catalogo RID (Runtime IDentifier) di .NET Core.](../rid-catalog.md)
- [Selezionare la versione di .NET Core da usare.](../versions/selection.md)
