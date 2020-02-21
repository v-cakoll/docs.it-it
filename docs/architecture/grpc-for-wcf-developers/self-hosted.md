---
title: Applicazioni gRPC self-hosted-gRPC per sviluppatori WCF
description: Distribuzione di ASP.NET Core applicazioni gRPC come servizi indipendenti.
ms.date: 09/02/2019
ms.openlocfilehash: ee370ba1893b060505b38ddf84235bd84433ad32
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542989"
---
# <a name="self-hosted-grpc-applications"></a>Applicazioni gRPC indipendenti

Sebbene le applicazioni ASP.NET Core 3,0 possano essere ospitate in IIS in Windows Server, attualmente non è possibile ospitare un'applicazione gRPC in IIS perché alcune delle funzionalità HTTP/2 non sono supportate. Questa funzionalità è un obiettivo per un futuro aggiornamento a Windows Server.

È possibile eseguire l'applicazione come servizio Windows. In alternativa, è possibile eseguirlo come servizio Linux controllato da [systemd](https://en.wikipedia.org/wiki/Systemd), a causa delle nuove funzionalità delle estensioni di hosting di .net core 3,0.

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

A questo punto, pubblicare l'applicazione usando uno di questi metodi:

* In Visual Studio fare clic con il pulsante destro del mouse sul progetto e scegliere **pubblica** dal menu di scelta rapida.
* Dal interfaccia della riga di comando di .NET Core.

Quando si pubblica un'applicazione .NET Core, è possibile scegliere di creare una distribuzione *dipendente dal Framework* o una distribuzione *autonoma* . Per le distribuzioni dipendenti dal Framework è necessario che il runtime condiviso di .NET Core sia installato nell'host in cui vengono eseguiti. Le distribuzioni autosufficienti sono pubblicate con una copia completa del Framework e del runtime di .NET Core e possono essere eseguite in qualsiasi host. Per ulteriori informazioni, inclusi i vantaggi e gli svantaggi di ogni approccio, vedere la documentazione relativa alla [distribuzione di applicazioni .NET Core](../../core/deploying/index.md) .

Per pubblicare una compilazione autonoma dell'applicazione che non richiede l'installazione del runtime di .NET Core 3,0 nell'host, specificare il runtime da includere nell'applicazione. Usare il flag `-r` (o `--runtime`).

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

Per pubblicare una compilazione dipendente dal Framework, omettere il flag `-r`.

```dotnetcli
dotnet publish -c Release -o ./publish
```

Copiare il contenuto completo della directory `publish` in una cartella di installazione. Usare quindi lo [strumento SC](/windows/desktop/services/controlling-a-service-using-sc) per creare un servizio Windows per il file eseguibile.

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a>Accedere al registro eventi di Windows

Il metodo `UseWindowsService` aggiunge automaticamente un provider di [registrazione](/aspnet/core/fundamentals/logging/) che scrive messaggi di log nel registro eventi di Windows. È possibile configurare la registrazione per questo provider aggiungendo una voce di `EventLog` alla sezione `Logging` di `appsettings.json` o un'altra origine della configurazione. 

È possibile eseguire l'override del nome di origine usato nel registro eventi impostando una proprietà `SourceName` in queste impostazioni. Se non si specifica un nome, verrà usato il nome predefinito dell'applicazione, in genere il nome dell'assembly eseguibile.

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

A questo punto, pubblicare l'applicazione. L'applicazione può essere dipendente dal Framework o indipendente per il runtime di Linux pertinente, ad esempio `linux-x64`. È possibile pubblicare utilizzando uno di questi metodi:

* In Visual Studio fare clic con il pulsante destro del mouse sul progetto e scegliere **pubblica** dal menu di scelta rapida. 
* Dal interfaccia della riga di comando di .NET Core, usando il comando seguente:

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
Copiare il contenuto completo della directory `publish` in una cartella di installazione nell'host Linux. Per la registrazione del servizio è necessario aggiungere un file speciale, denominato *file di unità*, alla directory `/etc/systemd/system`. È necessario disporre dell'autorizzazione radice per creare un file in questa cartella. Assegnare un nome al file con l'identificatore che si desidera utilizzare `systemd` e l'estensione `.service`. Ad esempio, usare `/etc/systemd/system/myapp.service`.

Il file del servizio usa il formato INI, come illustrato in questo esempio:

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

La proprietà `Type=notify` indica `systemd` che l'applicazione invierà una notifica all'avvio e all'arresto. L'impostazione `WantedBy=multi-user.target` provocherà l'avvio del servizio quando il sistema Linux raggiunge "runlevel 2", il che significa che è attiva una shell multiutente non grafica.

Prima che `systemd` riconosca il servizio, sarà necessario ricaricare la configurazione. È possibile controllare `systemd` usando il comando `systemctl`. Dopo il ricaricamento, utilizzare il sottocomando `status` per verificare che l'applicazione sia stata registrata correttamente.

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

Se il servizio è stato configurato correttamente, si otterrà l'output seguente:

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

L'equivalente Linux del registro eventi di Windows è `journald`, un servizio del sistema di registrazione strutturato che fa parte di `systemd`. I messaggi di log scritti nell'output standard da un daemon Linux vengono scritti automaticamente in `journald`. Per configurare i livelli di registrazione, usare la sezione `Console` della configurazione di registrazione. Il metodo del generatore host `UseSystemd` configura automaticamente il formato di output della console in base al Journal.

Poiché `journald` è lo standard per i log Linux, un'ampia gamma di strumenti si integrano con esso. È possibile instradare facilmente i log da `journald` a un sistema di registrazione esterno. Lavorando localmente nell'host, è possibile usare il comando `journalctl` per visualizzare i log dalla riga di comando.

```console
sudo journalctl -u myapp
```

> [!TIP]
> Se nell'host è disponibile un ambiente GUI, sono disponibili alcuni visualizzatori di log grafici per Linux, ad esempio *QJournalctl* e *GNOME-logs*.

Per ulteriori informazioni sull'esecuzione di query sul Journal `systemd` dalla riga di comando tramite `journalctl`, vedere [le pagine man](https://manpages.debian.org/buster/systemd/journalctl.1).

## <a name="https-certificates-for-self-hosted-applications"></a>Certificati HTTPS per le applicazioni indipendenti

Quando si esegue un'applicazione gRPC in produzione, è necessario usare un certificato TLS da un'autorità di certificazione (CA) attendibile. Questa CA può essere una CA pubblica o una interna per l'organizzazione.

Negli host Windows è possibile caricare il certificato da un [archivio certificati](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) protetto usando la classe <xref:System.Security.Cryptography.X509Certificates.X509Store>. È anche possibile usare la classe `X509Store` con l'archivio chiavi OpenSSL in alcuni host Linux.

È anche possibile creare certificati usando uno dei [costruttori X509Certificate2](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), da uno dei seguenti:

* Un file, ad esempio un file di `.pfx` protetto da una password complessa
* Dati binari recuperati da un servizio di archiviazione sicura, ad esempio [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)

È possibile configurare gheppio per l'uso di un certificato in due modi: dalla configurazione o nel codice.

### <a name="set-https-certificates-by-using-configuration"></a>Impostare i certificati HTTPS usando la configurazione

Per l'approccio di configurazione è necessario impostare il percorso del certificato `.pfx` file e la password nella sezione di configurazione di gheppio. In `appsettings.json`, avrà un aspetto simile al seguente:

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

Fornire la password usando un'origine di configurazione sicura, ad esempio Azure Key Vault o Hashicorp Vault.

> [!IMPORTANT]
> Non archiviare password non crittografate nei file di configurazione.

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

Anche in questo caso, assicurarsi di archiviare la password per il file di `.pfx` in e recuperarla da un'origine di configurazione sicura.

>[!div class="step-by-step"]
>[Precedente](grpc-in-production.md)
>[Successivo](docker.md)
