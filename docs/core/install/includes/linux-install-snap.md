---
ms.openlocfilehash: 5e77b7bd73c09e061a94a29703cf5286814d1ebb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602915"
---

[.NET Core è disponibile nell'archivio di snap.](https://snapcraft.io/dotnet-sdk)

Uno snap è un bundle di un'app e delle relative dipendenze che funziona senza modifiche in molte distribuzioni Linux diverse. Gli snap sono individuabili e installabili dall'archivio snap. Per ulteriori informazioni su snap, vedere la pagina relativa all' [Introduzione a snap](https://snapcraft.io/docs/getting-started).

Solo le versioni supportate di .NET Core sono disponibili tramite snap.

### <a name="install-the-sdk"></a>Installare l'SDK

I pacchetti di snap per .NET Core SDK sono tutti pubblicati con lo stesso identificatore: `dotnet-sdk` . È possibile installare una versione specifica dell'SDK specificando il canale. L'SDK include il runtime di corisposta. La tabella seguente elenca i canali:

| Versione di .NET Core | Blocca pacchetto             |
|-------------------|--------------------------|
| 3,1 (LTS)         | `3.1` o `latest/stable` |
| 2,1 (LTS)         | `2.1`                    |
| .NET 5,0 Preview  | `5.0/beta`               |

Usare il `snap install` comando per installare un pacchetto di snap .NET Core SDK. Usare il `--channel` parametro per indicare la versione da installare. Se questo parametro viene omesso, `latest/stable` viene utilizzato. In questo esempio `3.1` viene specificato:

```bash
sudo snap install dotnet-sdk --classic --channel=3.1
```

Registrare quindi il `dotnet` comando per il sistema con il `snap alias` comando:

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

Questo comando è formattato come: `sudo snap alias {package}.{command} {alias}` . È possibile scegliere qualsiasi `{alias}` nome. Ad esempio, è possibile denominare il comando dopo la versione specifica installata da snap: `sudo snap alias dotnet-sdk.dotnet dotnet31` . Quando si usa il comando `dotnet31` , si richiama questa versione specifica di .NET. Tuttavia, questo non è compatibile con la maggior parte delle esercitazioni ed esempi, perché si aspettano che un `dotnet` comando sia disponibile.

### <a name="install-the-runtime"></a>Installare il runtime

I pacchetti di snap per il runtime di .NET Core sono pubblicati con il proprio identificatore del pacchetto. Nella tabella seguente sono elencati gli identificatori dei pacchetti:

| Versione di .NET Core | Blocca pacchetto        |
|-------------------|---------------------|
| 3,1 (LTS)         | `dotnet-runtime-31` |
| 3.0               | `dotnet-runtime-30` |
| 2.2               | `dotnet-runtime-22` |
| 2,1 (LTS)         | `dotnet-runtime-21` |

Usare il `snap install` comando per installare un pacchetto di snap-in di runtime di .NET Core. In questo esempio è installato .NET Core 3,1:

```bash
sudo snap install dotnet-runtime-31 --classic
```

Registrare quindi il `dotnet` comando per il sistema con il `snap alias` comando:

```bash
sudo snap alias dotnet-runtime-31.dotnet dotnet
```

Questo comando è formattato come: `sudo snap alias {package}.{command} {alias}` . È possibile scegliere qualsiasi `{alias}` nome. Ad esempio, è possibile denominare il comando dopo la versione specifica installata da snap: `sudo snap alias dotnet-runtime-31.dotnet dotnet31` . Quando si usa il comando `dotnet31` , si richiama questa versione specifica di .NET. Tuttavia, questo non è compatibile con la maggior parte delle esercitazioni ed esempi, perché si aspettano che un `dotnet` comando sia disponibile.

### <a name="ssl-certificate-errors"></a>Errori del certificato SSL

Quando .NET viene installato tramite snap, è possibile che in alcune distribuzioni i certificati SSL .NET non vengano trovati ed è possibile che venga visualizzato un errore simile al seguente durante `restore` :

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

Per risolvere questo problema, impostare alcune variabili ambiente:

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

Il percorso del certificato può variare in base alla distribuzione. Ecco i percorsi per le distribuzioni in cui si è verificato il problema.

* Fedora`/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`
* OpenSUSE`/etc/ssl/ca-bundle.pem`
* Solus`/etc/ssl/certs/ca-certificates.crt`
