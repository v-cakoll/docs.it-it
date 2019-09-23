---
title: Applicazioni gRPC self-hosted-gRPC per sviluppatori WCF
description: Distribuzione di ASP.NET Core applicazioni gRPC come servizi indipendenti.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 1269137b58f4d25f407a6a04327c51bc9f069c1b
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184106"
---
# <a name="self-hosted-grpc-applications"></a>Applicazioni gRPC indipendenti

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Sebbene le applicazioni ASP.NET Core 3,0 possano essere ospitate in IIS in Windows Server, attualmente non è possibile ospitare un'applicazione gRPC in IIS perché alcune delle funzionalità HTTP/2 non sono ancora supportate. Questa funzionalità è prevista in un aggiornamento futuro di Windows Server.

È possibile eseguire l'applicazione come servizio Windows o come servizio Linux controllato da [systemd](https://en.wikipedia.org/wiki/Systemd), grazie ad alcune nuove funzionalità di .net core 3,0 host Extensions.

## <a name="run-your-app-as-a-windows-service"></a>Eseguire l'app come servizio Windows

Per configurare l'applicazione ASP.NET Core per l'esecuzione come servizio Windows, installare il pacchetto [Microsoft. Extensions. Hosting. WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) da NuGet. Aggiungere quindi una chiamata al `UseWindowsService` `CreateHostBuilder` metodo in `Program.cs`.

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .UseWindowsService() // Enable running as a Windows service
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

> [!NOTE]
> Se l'applicazione non è in esecuzione come servizio Windows, `UseWindowsService` il metodo non esegue alcuna operazione.

A questo punto, pubblicare l'applicazione, da Visual Studio facendo clic con il pulsante destro del mouse sul progetto e scegliendo *pubblica* dal menu di scelta rapida o dalla interfaccia della riga di comando di .NET Core.

Quando si pubblica un'applicazione .NET Core, è possibile scegliere di creare una distribuzione *dipendente dal Framework* o una distribuzione *autonoma* . Per le distribuzioni dipendenti dal Framework è necessario che il runtime condiviso di .NET Core sia installato nell'host in cui vengono eseguiti. Le distribuzioni autosufficienti sono pubblicate con una copia completa del Framework e del runtime di .NET Core e possono essere eseguite in qualsiasi host. Per ulteriori informazioni, inclusi i vantaggi e gli svantaggi di ogni approccio, vedere la documentazione relativa alla [distribuzione di applicazioni .NET Core](https://docs.microsoft.com/dotnet/core/deploying/) .

Per pubblicare una compilazione autonoma dell'applicazione che non richiede l'installazione del runtime di .NET Core 3,0 nell'host, specificare il runtime da includere nell'applicazione usando il `-r` flag (o `--runtime`).

```console
dotnet publish -c Release -r win-x64 -o ./publish
```

Per pubblicare una compilazione dipendente dal Framework, omettere `-r` il flag.

```console
dotnet publish -c Release -o ./publish
```

Copiare il contenuto completo della `publish` directory in una cartella di installazione e usare l' [utilità SC](https://docs.microsoft.com/windows/desktop/services/controlling-a-service-using-sc) per creare un servizio Windows per il file eseguibile.

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-windows-event-log"></a>Registra nel registro eventi di Windows

Il `UseWindowsService` metodo aggiunge automaticamente un provider di [registrazione](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0) che scrive messaggi di log nel registro eventi di Windows. È possibile configurare la `EventLog` `Logging` registrazione per questo provider aggiungendo una voce alla sezione di o `appsettings.json` di un'altra origine della configurazione. È possibile eseguire l'override del nome di origine usato nel registro eventi impostando una `SourceName` proprietà in queste impostazioni. se non si specifica un nome, verrà usato il nome dell'applicazione predefinito, in genere il nome dell'assembly eseguibile.

Ulteriori informazioni sulla registrazione sono alla fine di questo capitolo.

## <a name="run-your-app-as-a-linux-service-with-systemd"></a>Eseguire l'app come servizio Linux con systemd

Per configurare l'applicazione ASP.NET Core per l'esecuzione come servizio Linux (o *daemon* in Linux), installare il pacchetto [Microsoft. Extensions. Hosting. systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) da NuGet. Aggiungere quindi una chiamata al `UseSystemd` `CreateHostBuilder` metodo in `Program.cs`.

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .UseSystemd() // Enable running as a Systemd service
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

> [!NOTE]
> Se l'applicazione non è in esecuzione come servizio Linux, `UseSystemd` il metodo non esegue alcuna operazione.

A questo punto, pubblicare l'applicazione (dipendente dal Framework o autonomo per il runtime di Linux pertinente, `linux-x64`ad esempio), da Visual Studio facendo clic con il pulsante destro del mouse sul progetto e scegliendo *pubblica* dal menu di scelta rapida o da .NET INTERFACCIA della riga di comando di base usando il comando seguente.

```console
dotnet publish -c Release -r linux-x64 -o ./publish
```

Copiare il contenuto completo della `publish` directory in una cartella di installazione nell'host Linux. Per la registrazione del servizio è necessario aggiungere alla `/etc/systemd/system` directory un file speciale, denominato "file unità". È necessario disporre dell'autorizzazione radice per creare un file in questa cartella. Assegnare un nome al file con l'identificatore `systemd` che si desidera utilizzare `.service` e l'estensione. Ad esempio `/etc/systemd/system/myapp.service`.

Il file del servizio usa il formato INI, come illustrato in questo esempio.

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

La `Type=notify` proprietà indica `systemd` che l'applicazione invierà una notifica all'avvio e all'arresto. L' `WantedBy=multi-user.target` impostazione provocherà l'avvio del servizio quando il sistema Linux raggiunge "runlevel 2", vale a dire che è attiva una shell multiutente non grafica.

Prima `systemd` che riconosca il servizio, deve ricaricare la configurazione. È possibile `systemd` controllare usando `systemctl` il comando. Dopo il ricaricamento, utilizzare `status` il sottocomando per verificare che l'applicazione sia stata registrata correttamente.

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

Se il servizio è stato configurato correttamente, verrà visualizzato l'output seguente:

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

Usare il `start` comando per avviare il servizio.

```console
sudo systemctl start myapp.service
```

> [!TIP]
> L' `.service` estensione è facoltativa quando `systemctl start`si usa.

Per indicare `systemd` di avviare automaticamente il servizio all'avvio del sistema, usare `enable` il comando.

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a>Registra in journald

L'equivalente Linux del registro eventi di Windows è `journald`, un servizio del sistema di registrazione strutturato che `systemd`fa parte di. I messaggi di log scritti nell'output standard da un daemon Linux vengono scritti automaticamente `journald`in, quindi per configurare i livelli di registrazione `Console` , usare la sezione della configurazione di registrazione. Il `UseSystemd` metodo del generatore host configura automaticamente il formato di output della console in base al Journal.

Poiché `journald` è lo standard per i log di Linux, sono disponibili diversi strumenti che si integrano con esso ed è possibile indirizzare facilmente `journald` i log da a un sistema di registrazione esterno. Lavorando localmente nell'host, è possibile usare il `journalctl` comando per visualizzare i log dalla riga di comando.

```console
sudo journalctl -u myapp
```

> [!TIP]
> Se nell'host è disponibile un ambiente GUI, sono disponibili alcuni visualizzatori di log grafici per Linux, ad esempio *QJournalctl* e *GNOME-logs*.

Per ulteriori informazioni sull'esecuzione di query sul Journal systemd dalla riga di comando `journalctl`con, vedere [le pagine man](https://manpages.debian.org/buster/systemd/journalctl.1).

## <a name="https-certificates-for-self-hosted-applications"></a>Certificati HTTPS per le applicazioni indipendenti

Quando si esegue un'applicazione gRPC in produzione, è necessario usare un certificato TLS da un'autorità di certificazione (CA) attendibile. Questa CA può essere una CA pubblica o un'altra per l'organizzazione.

Negli host Windows, il certificato può essere caricato da un [archivio certificati](https://docs.microsoft.com/windows/win32/seccrypto/managing-certificates-with-certificate-stores) protetto usando la [classe X509Store](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509store?view=netcore-3.0). La `X509Store` classe può essere usata anche con l'archivio chiavi OpenSSL in alcuni host Linux.

I certificati possono anche essere creati utilizzando uno dei [costruttori X509Certificate2](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509certificate.-ctor?view=netcore-3.0), da un file (ad esempio un `.pfx` file protetto da una password complessa) o da dati binari recuperati da un servizio di archiviazione protetto, ad esempio [Azure Key Vault ](https://azure.microsoft.com/services/key-vault/).

Il gheppio può essere configurato per l'uso di un certificato in due modi: dalla configurazione o nel codice.

### <a name="set-https-certificates-using-configuration"></a>Impostare i certificati HTTPS usando la configurazione

Per l'approccio di configurazione è necessario impostare il percorso `.pfx` del file di certificato e la password nella sezione di configurazione di gheppio. In `appsettings.json` questo aspetto sarà simile al seguente.

```json
{
  "Kestrel": {
    "Certificates": {
      "Default": {
        "Path": "cert.pfx",
        "Password": "DO NOT STORE PLAINTEXT PASSWORDS IN APPSETTINGS FILES"
      }
    }
  }
}
```

La password deve essere fornita usando un'origine di configurazione sicura, ad esempio l'insieme di credenziali delle credenziali di Azure o Hashicorp.

NON è consigliabile archiviare password non crittografate nei file di configurazione.

### <a name="set-https-certificates-in-code"></a>Impostare i certificati HTTPS nel codice

Per configurare HTTPS in gheppio nel codice, usare il `ConfigureKestrel` metodo su `IWebHostBuilder` nella `Program` classe.

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
            webBuilder.ConfigureKestrel(kestrel =>
            {
                kestrel.ConfigureHttpsDefaults(https =>
                {
                    https.ServerCertificate = new X509Certificate2("mycert.pfx", "password");
                });
            });
        });
```

Anche in questo caso, la `.pfx` password per il file deve essere archiviata e recuperata da un'origine di configurazione sicura.

>[!div class="step-by-step"]
>[Precedente](grpc-in-production.md)
>[Successivo](docker.md)
