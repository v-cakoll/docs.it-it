---
title: Applicazioni gRPC self-hosted-gRPC per sviluppatori WCF
description: Distribuzione di ASP.NET Core applicazioni gRPC come servizi indipendenti.
ms.date: 09/02/2019
ms.openlocfilehash: 00b4ad50eae629b5b36a890d1eecf7119386c74c
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/29/2019
ms.locfileid: "75545070"
---
# <a name="self-hosted-grpc-applications"></a>Applicazioni gRPC indipendenti

Sebbene le applicazioni ASP.NET Core 3,0 possano essere ospitate in IIS in Windows Server, attualmente non è possibile ospitare un'applicazione gRPC in IIS perché alcune delle funzionalità HTTP/2 non sono ancora supportate. Questa funzionalità è prevista in un aggiornamento futuro di Windows Server.

È possibile eseguire l'applicazione come servizio Windows o come servizio Linux controllato da [systemd](https://en.wikipedia.org/wiki/Systemd), grazie ad alcune nuove funzionalità di .net core 3,0 host Extensions.

## <a name="run-your-app-as-a-windows-service"></a>Eseguire l'app come servizio Windows

Per configurare l'applicazione ASP.NET Core per l'esecuzione come servizio Windows, installare il pacchetto [Microsoft. Extensions. Hosting. WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) da NuGet. Aggiungere quindi una chiamata a `UseWindowsService` al metodo `CreateHostBuilder` in `Program.cs`.

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
> Se l'applicazione non è in esecuzione come servizio di Windows, il `UseWindowsService` metodo non esegue alcuna operazione.

A questo punto, pubblicare l'applicazione, da Visual Studio facendo clic con il pulsante destro del mouse sul progetto e scegliendo *pubblica* dal menu di scelta rapida o dalla interfaccia della riga di comando di .NET Core.

Quando si pubblica un'applicazione .NET Core, è possibile scegliere di creare una distribuzione *dipendente dal Framework* o una distribuzione *autonoma* . Per le distribuzioni dipendenti dal Framework è necessario che il runtime condiviso di .NET Core sia installato nell'host in cui vengono eseguiti. Le distribuzioni autosufficienti sono pubblicate con una copia completa del Framework e del runtime di .NET Core e possono essere eseguite in qualsiasi host. Per ulteriori informazioni, inclusi i vantaggi e gli svantaggi di ogni approccio, vedere la documentazione relativa alla [distribuzione di applicazioni .NET Core](../../core/deploying/index.md) .

Per pubblicare una compilazione autonoma dell'applicazione che non richiede l'installazione del runtime di .NET Core 3,0 nell'host, specificare il runtime da includere nell'applicazione usando il flag `-r` (o `--runtime`).

```console
dotnet publish -c Release -r win-x64 -o ./publish
```

Per pubblicare una compilazione dipendente dal Framework, omettere il flag `-r`.

```console
dotnet publish -c Release -o ./publish
```

Copiare il contenuto completo della directory `publish` in una cartella di installazione e usare l' [utilità SC](https://docs.microsoft.com/windows/desktop/services/controlling-a-service-using-sc) per creare un servizio Windows per il file eseguibile.

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-windows-event-log"></a>Registra nel registro eventi di Windows

Il metodo `UseWindowsService` aggiunge automaticamente un provider di [registrazione](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0) che scrive messaggi di log nel registro eventi di Windows. Per configurare la registrazione per questo provider, è possibile aggiungere una voce `EventLog` alla sezione `Logging` di `appsettings.json` o ad altre origini di configurazione. È possibile eseguire l'override del nome di origine utilizzato nel registro eventi impostando una proprietà `SourceName` in queste impostazioni. Se non si specifica un nome, verrà usato il nome predefinito dell'applicazione, in genere il nome dell'assembly eseguibile.

Ulteriori informazioni sulla registrazione sono alla fine di questo capitolo.

## <a name="run-your-app-as-a-linux-service-with-systemd"></a>Eseguire l'app come servizio Linux con systemd

Per configurare l'applicazione ASP.NET Core per l'esecuzione come servizio Linux (o *daemon* in Linux), installare il pacchetto [Microsoft. Extensions. Hosting. systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) da NuGet. Aggiungere quindi una chiamata a `UseSystemd` al metodo `CreateHostBuilder` in `Program.cs`.

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
> Se l'applicazione non è in esecuzione come servizio Linux, il `UseSystemd` metodo non esegue alcuna operazione.

A questo punto, pubblicare l'applicazione (dipendente dal Framework o autonomo per il runtime di Linux pertinente, ad esempio `linux-x64`), da Visual Studio facendo clic con il pulsante destro del mouse sul progetto e scegliendo *pubblica* dal menu di scelta rapida o dal interfaccia della riga di comando di .NET Core usando il comando seguente.

```console
dotnet publish -c Release -r linux-x64 -o ./publish
```

Copiare il contenuto completo della directory `publish` in una cartella di installazione nell'host Linux. Per la registrazione del servizio è necessario aggiungere un file speciale, denominato "file unità", alla directory `/etc/systemd/system`. È necessario disporre dell'autorizzazione radice per creare un file in questa cartella. Assegnare un nome al file con l'identificatore che si vuole usare `systemd` e l'estensione `.service`. Ad esempio `/etc/systemd/system/myapp.service`.

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

La proprietà `Type=notify` indica `systemd` che l'applicazione invierà una notifica all'avvio e all'arresto. L'impostazione `WantedBy=multi-user.target` provocherà l'avvio del servizio quando il sistema Linux raggiunge "runlevel 2", vale a dire che è attiva una shell multiutente non grafica.

Prima che `systemd` riconosca il servizio, sarà necessario ricaricare la configurazione. È possibile controllare `systemd` usando il comando `systemctl`. Dopo il ricaricamento, utilizzare il sottocomando `status` per verificare che l'applicazione sia stata registrata correttamente.

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

Usare il comando `start` per avviare il servizio.

```console
sudo systemctl start myapp.service
```

> [!TIP]
> L'estensione `.service` è facoltativa quando si usa `systemctl start`.

Per indicare `systemd` avviare automaticamente il servizio all'avvio del sistema, usare il comando `enable`.

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a>Registra in journald

L'equivalente Linux del registro eventi di Windows è `journald`, un servizio del sistema di registrazione strutturato che fa parte di `systemd`. I messaggi di log scritti nell'output standard da un daemon Linux vengono scritti automaticamente in `journald`, quindi, per configurare i livelli di registrazione, usare la sezione `Console` della configurazione di registrazione. Il metodo del generatore host `UseSystemd` configura automaticamente il formato di output della console in base al Journal.

Poiché `journald` è lo standard per i log di Linux, sono disponibili diversi strumenti che si integrano con esso ed è possibile indirizzare facilmente i log da `journald` a un sistema di registrazione esterno. Lavorando localmente nell'host, è possibile usare il comando `journalctl` per visualizzare i log dalla riga di comando.

```console
sudo journalctl -u myapp
```

> [!TIP]
> Se nell'host è disponibile un ambiente GUI, sono disponibili alcuni visualizzatori di log grafici per Linux, ad esempio *QJournalctl* e *GNOME-logs*.

Per ulteriori informazioni sull'esecuzione di query sul Journal systemd dalla riga di comando con `journalctl`, vedere [le pagine man](https://manpages.debian.org/buster/systemd/journalctl.1).

## <a name="https-certificates-for-self-hosted-applications"></a>Certificati HTTPS per le applicazioni indipendenti

Quando si esegue un'applicazione gRPC in produzione, è necessario usare un certificato TLS da un'autorità di certificazione (CA) attendibile. Questa CA può essere una CA pubblica o un'altra per l'organizzazione.

Negli host Windows, il certificato può essere caricato da un [archivio certificati](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) protetto usando la classe <xref:System.Security.Cryptography.X509Certificates.X509Store>. La classe `X509Store` può essere usata anche con l'archivio chiavi OpenSSL in alcuni host Linux.

I certificati possono essere creati anche usando uno dei [costruttori X509Certificate2](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509certificate.-ctor?view=netcore-3.0), da un file, ad esempio un file di `.pfx` protetto da una password complessa, o da dati binari recuperati da un servizio di archiviazione protetto, ad esempio [Azure Key Vault](https://azure.microsoft.com/services/key-vault/).

Il gheppio può essere configurato per l'uso di un certificato in due modi: dalla configurazione o nel codice.

### <a name="set-https-certificates-using-configuration"></a>Impostare i certificati HTTPS usando la configurazione

Per l'approccio di configurazione è necessario impostare il percorso del certificato `.pfx` file e la password nella sezione di configurazione di gheppio. In `appsettings.json` che avrà un aspetto simile al seguente.

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

Per configurare HTTPS in gheppio nel codice, usare il metodo `ConfigureKestrel` su `IWebHostBuilder` nella classe `Program`.

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

Anche in questo caso, la password per il file di `.pfx` deve essere archiviata e recuperata da un'origine di configurazione sicura.

>[!div class="step-by-step"]
>[Precedente](grpc-in-production.md)
>[Successivo](docker.md)
