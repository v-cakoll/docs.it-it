---
title: Applicazioni gRPC self-hosted - gRPC per gli sviluppatori WCFSelf-hosted gRPC applications - gRPC for WCF developers
description: Distribuzione di applicazioni gRPC ASP.NET Core come servizi self-hosted.
ms.date: 09/02/2019
ms.openlocfilehash: 00fb1453e19a02469f80af79672e0c1f72c7280f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147802"
---
# <a name="self-hosted-grpc-applications"></a>Applicazioni gRPC auto-ospitate

Sebbene ASP.NET applicazioni Core 3.0 possano essere ospitate in IIS in Windows Server, attualmente non è possibile ospitare un'applicazione gRPC in IIS perché alcune delle funzionalità HTTP/2 non sono supportate. Questa funzionalità è un obiettivo per un aggiornamento futuro di Windows Server.This functionality is a goal for a future update to Windows Server.

È possibile eseguire l'applicazione come servizio Windows.You can run your application as a Windows service. In alternativa, è possibile eseguirlo come un servizio Linux controllato da [systemd](https://en.wikipedia.org/wiki/Systemd), a causa delle nuove funzionalità nelle estensioni di hosting di .NET Core 3.0.

## <a name="run-your-app-as-a-windows-service"></a>Eseguire l'app come servizio WindowsRun your app as a Windows service

Per configurare l'applicazione ASP.NET Core per l'esecuzione come servizio Windows, installare il pacchetto Microsoft.Extensions.Hosting.WindowsServices da NuGet.To configure your Application a Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet. Aggiungere quindi una `UseWindowsService` chiamata `CreateHostBuilder` a `Program.cs`al metodo in .

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
> Se l'applicazione non è in esecuzione `UseWindowsService` come servizio Windows, il metodo non esegue alcuna operazione.

Pubblicare ora l'applicazione utilizzando uno di questi metodi:Now publish your application by using one of these methods:

* In Visual Studio fare clic con il pulsante destro del mouse sul progetto e **scegliere Pubblica** dal menu di scelta rapida.
* Dalla CLI di .NET Core.

Quando si pubblica un'applicazione .NET Core, è possibile scegliere di creare una distribuzione *dipendente dal framework* o una distribuzione *autonoma.* Le distribuzioni dipendenti da Framework richiedono l'installazione del runtime condiviso .NET Core nell'host in cui vengono eseguite. Le distribuzioni autonome vengono pubblicate con una copia completa del runtime e del framework .NET Core e possono essere eseguite in qualsiasi host. Per altre informazioni, inclusi i vantaggi e gli svantaggi di ogni approccio, vedere la documentazione relativa alla distribuzione di applicazioni [.NET Core.For](../../core/deploying/index.md) more information, including the advantages and disadvantages of each approach, see the .NET Core application deployment documentation.

Per pubblicare una compilazione autonoma dell'applicazione che non richiede l'installazione del runtime di .NET Core 3.0 nell'host, specificare il runtime da includere nell'applicazione. Utilizzare `-r` il `--runtime`flag (o).

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

Per pubblicare una compilazione dipendente `-r` dal framework, omettere il flag.

```dotnetcli
dotnet publish -c Release -o ./publish
```

Copiare il contenuto `publish` completo della directory in una cartella di installazione. Quindi, utilizzare [lo strumento sc](/windows/desktop/services/controlling-a-service-using-sc) per creare un servizio di Windows per il file eseguibile.

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a>Accedere al registro eventi di Windows

Il `UseWindowsService` metodo aggiunge automaticamente un provider di [registrazione](/aspnet/core/fundamentals/logging/) che scrive i messaggi di log nel registro eventi di Windows. È possibile configurare la registrazione `EventLog` per `Logging` questo `appsettings.json` provider aggiungendo una voce alla sezione o a un'altra origine di configurazione.

È possibile sostituire il nome di origine `SourceName` utilizzato nel registro eventi impostando una proprietà in queste impostazioni. Se non si specifica un nome, verrà utilizzato il nome dell'applicazione predefinita (in genere il nome dell'assembly eseguibile).

Ulteriori informazioni sulla registrazione sono alla fine di questo capitolo.

## <a name="run-your-app-as-a-linux-service-with-systemd"></a>Eseguire l'app come servizio Linux con sistema

Per configurare l'applicazione ASP.NET Core per l'esecuzione come servizio Linux (o daemon nel linguaggio Linux), installare il pacchetto [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) da NuGet.To configure your Application ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the Microsoft.Extensions.Hosting.Systemd package from NuGet. Aggiungere quindi una `UseSystemd` chiamata `CreateHostBuilder` a `Program.cs`al metodo in .

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
> Se l'applicazione non è in esecuzione `UseSystemd` come servizio Linux, il metodo non esegue alcuna operazione.

Pubblicare ora l'applicazione. L'applicazione può essere dipendente dal framework o autonoma per `linux-x64`il runtime Linux pertinente (ad esempio, ). È possibile pubblicare utilizzando uno dei seguenti metodi:

* In Visual Studio fare clic con il pulsante destro del mouse sul progetto e **scegliere Pubblica** dal menu di scelta rapida.
* Dalla CLI di .NET Core, utilizzando il comando seguente:

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
Copiare il contenuto `publish` completo della directory in una cartella di installazione nell'host Linux. La registrazione del servizio richiede l'aggiunta di un file `/etc/systemd/system` speciale, denominato file di *unità,* alla directory. È necessaria l'autorizzazione root per creare un file in questa cartella. Assegnare al file il `systemd` nome con `.service` l'identificatore che si desidera utilizzare e l'estensione. Ad esempio, usare `/etc/systemd/system/myapp.service`.

Il file del servizio usa il formato INI, come illustrato nell'esempio seguente:The service file uses INI format, as shown in this example:

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

La `Type=notify` proprietà `systemd` indica che l'applicazione invierà una notifica all'avvio e all'arresto. L'impostazione `WantedBy=multi-user.target` causerà l'avvio del servizio quando il sistema Linux raggiunge il "runlevel 2", il che significa che è attiva una shell multiutente non grafica.

Prima `systemd` di riconoscere il servizio, è necessario ricaricare la configurazione. È `systemd` possibile controllare `systemctl` utilizzando il comando . Dopo il ricaricamento, utilizzare il `status` sottocomando per verificare che l'applicazione sia stata registrata correttamente.

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

Se il servizio è stato configurato correttamente, si otterrà il seguente output:

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

Utilizzare `start` il comando per avviare il servizio.

```console
sudo systemctl start myapp.service
```

> [!TIP]
> L'estensione `.service` è facoltativa quando `systemctl start`si utilizza .

Per `systemd` indicare di avviare automaticamente il `enable` servizio all'avvio del sistema, utilizzare il comando .

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a>Registra nel journal

L'equivalente Linux del registro eventi di Windows è `journald`, `systemd`un servizio di sistema di registrazione strutturata che fa parte di . I messaggi di log scritti nell'output standard di `journald`un daemon Linux vengono scritti automaticamente in . Per configurare i `Console` livelli di registrazione, utilizzare la sezione della configurazione di registrazione. Il `UseSystemd` metodo del generatore host configura automaticamente il formato di output della console in base al journal.

Poiché `journald` è lo standard per i log Linux, una varietà di strumenti si integra con esso. È possibile instradare facilmente i registri da `journald` un sistema di registrazione esterno. Lavorando localmente sull'host, `journalctl` è possibile utilizzare il comando per visualizzare i registri dalla riga di comando.

```console
sudo journalctl -u myapp
```

> [!TIP]
> Se nell'host è disponibile un ambiente GUI, sono disponibili alcuni visualizzatori di log grafici per Linux, ad esempio *QJournalctl* e *gnome-logs*.

Per ulteriori informazioni sull'esecuzione di query `systemd` `journalctl`sul journal dalla riga di comando utilizzando , vedere [le pagine man](https://manpages.debian.org/buster/systemd/journalctl.1).

## <a name="https-certificates-for-self-hosted-applications"></a>Certificati HTTPS per applicazioni self-hosted

Quando si esegue un'applicazione gRPC nell'ambiente di produzione, è necessario utilizzare un certificato TLS da un'autorità di certificazione (CA) attendibile. Questa CA può essere una CA pubblica o interna per l'organizzazione.

Negli host Windows è possibile caricare il certificato da <xref:System.Security.Cryptography.X509Certificates.X509Store> un [archivio certificati](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) protetto utilizzando la classe . È anche possibile `X509Store` usare la classe con l'archivio chiavi OpenSSL su alcuni host Linux.You can also use the class with the OpenSSL key store on some Linux hosts.

È inoltre possibile creare certificati utilizzando uno dei [costruttori X509Certificate2](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), da:

* Un file, ad `.pfx` esempio un file protetto da una password complessa
* Dati binari recuperati da un servizio di archiviazione sicuro, ad esempio Archiviazione guidata chiavi di [AzureBinary data](https://azure.microsoft.com/services/key-vault/) retrieved from a secure storage service such as Azure Key Vault

È possibile configurare Kestrel per l'utilizzo di un certificato in due modi: dalla configurazione o nel codice.

### <a name="set-https-certificates-by-using-configuration"></a>Impostare i certificati HTTPS tramite la configurazioneSet HTTPS certificates by using configuration

L'approccio di configurazione richiede `.pfx` l'impostazione del percorso del file del certificato e della password nella sezione di configurazione di Kestrel. In `appsettings.json`, che sarebbe simile a questo:

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

Fornire la password usando un'origine di configurazione sicura, ad esempio Azure Key Vault o Hashicorp Vault.Provide the password by using a secure configuration source such as Azure Key Vault or Hashicorp Vault.

> [!IMPORTANT]
> Non archiviare password non crittografate nei file di configurazione.

### <a name="set-https-certificates-in-code"></a>Impostare i certificati HTTPS nel codiceSet HTTPS certificates in code

Per configurare HTTPS su Kestrel `ConfigureKestrel` nel `IWebHostBuilder` codice, utilizzare il metodo on nella `Program` classe.

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

Anche in questo caso, assicurarsi di archiviare la password per il `.pfx` file in e recuperarlo da un'origine di configurazione sicura.

>[!div class="step-by-step"]
>[Successivo](grpc-in-production.md)
>[precedente](docker.md)
