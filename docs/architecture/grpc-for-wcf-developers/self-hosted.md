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
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="8cb94-103">Applicazioni gRPC indipendenti</span><span class="sxs-lookup"><span data-stu-id="8cb94-103">Self-hosted gRPC applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="8cb94-104">Sebbene le applicazioni ASP.NET Core 3,0 possano essere ospitate in IIS in Windows Server, attualmente non è possibile ospitare un'applicazione gRPC in IIS perché alcune delle funzionalità HTTP/2 non sono ancora supportate.</span><span class="sxs-lookup"><span data-stu-id="8cb94-104">Although ASP.NET Core 3.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't yet supported.</span></span> <span data-ttu-id="8cb94-105">Questa funzionalità è prevista in un aggiornamento futuro di Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8cb94-105">This functionality is expected in a future update to Windows Server.</span></span>

<span data-ttu-id="8cb94-106">È possibile eseguire l'applicazione come servizio Windows o come servizio Linux controllato da [systemd](https://en.wikipedia.org/wiki/Systemd), grazie ad alcune nuove funzionalità di .net core 3,0 host Extensions.</span><span class="sxs-lookup"><span data-stu-id="8cb94-106">You can run your application as a Windows Service, or as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), thanks to some new features in the .NET Core 3.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="8cb94-107">Eseguire l'app come servizio Windows</span><span class="sxs-lookup"><span data-stu-id="8cb94-107">Run your app as a Windows service</span></span>

<span data-ttu-id="8cb94-108">Per configurare l'applicazione ASP.NET Core per l'esecuzione come servizio Windows, installare il pacchetto [Microsoft. Extensions. Hosting. WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) da NuGet.</span><span class="sxs-lookup"><span data-stu-id="8cb94-108">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="8cb94-109">Aggiungere quindi una chiamata al `UseWindowsService` `CreateHostBuilder` metodo in `Program.cs`.</span><span class="sxs-lookup"><span data-stu-id="8cb94-109">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="8cb94-110">Se l'applicazione non è in esecuzione come servizio Windows, `UseWindowsService` il metodo non esegue alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="8cb94-110">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="8cb94-111">A questo punto, pubblicare l'applicazione, da Visual Studio facendo clic con il pulsante destro del mouse sul progetto e scegliendo *pubblica* dal menu di scelta rapida o dalla interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8cb94-111">Now publish your application, either from Visual Studio by right-clicking the project and choosing *Publish* from the context menu, or from the .NET Core CLI.</span></span>

<span data-ttu-id="8cb94-112">Quando si pubblica un'applicazione .NET Core, è possibile scegliere di creare una distribuzione *dipendente dal Framework* o una distribuzione *autonoma* .</span><span class="sxs-lookup"><span data-stu-id="8cb94-112">When you publish a .NET Core application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="8cb94-113">Per le distribuzioni dipendenti dal Framework è necessario che il runtime condiviso di .NET Core sia installato nell'host in cui vengono eseguiti.</span><span class="sxs-lookup"><span data-stu-id="8cb94-113">Framework-dependent deployments require the .NET Core Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="8cb94-114">Le distribuzioni autosufficienti sono pubblicate con una copia completa del Framework e del runtime di .NET Core e possono essere eseguite in qualsiasi host.</span><span class="sxs-lookup"><span data-stu-id="8cb94-114">Self-contained deployments are published with a complete copy of the .NET Core runtime and framework and can be run on any host.</span></span> <span data-ttu-id="8cb94-115">Per ulteriori informazioni, inclusi i vantaggi e gli svantaggi di ogni approccio, vedere la documentazione relativa alla [distribuzione di applicazioni .NET Core](https://docs.microsoft.com/dotnet/core/deploying/) .</span><span class="sxs-lookup"><span data-stu-id="8cb94-115">For more information, including the advantages and disadvantages of each approach, refer to the [.NET Core application deployment](https://docs.microsoft.com/dotnet/core/deploying/) documentation.</span></span>

<span data-ttu-id="8cb94-116">Per pubblicare una compilazione autonoma dell'applicazione che non richiede l'installazione del runtime di .NET Core 3,0 nell'host, specificare il runtime da includere nell'applicazione usando il `-r` flag (o `--runtime`).</span><span class="sxs-lookup"><span data-stu-id="8cb94-116">To publish a self-contained build of the application that does not require the .NET Core 3.0 runtime to be installed on the host, specify the runtime to be included with the application using the `-r` (or `--runtime`) flag.</span></span>

```console
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="8cb94-117">Per pubblicare una compilazione dipendente dal Framework, omettere `-r` il flag.</span><span class="sxs-lookup"><span data-stu-id="8cb94-117">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```console
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="8cb94-118">Copiare il contenuto completo della `publish` directory in una cartella di installazione e usare l' [utilità SC](https://docs.microsoft.com/windows/desktop/services/controlling-a-service-using-sc) per creare un servizio Windows per il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="8cb94-118">Copy the complete contents of the `publish` directory to an installation folder, and use the [sc utility](https://docs.microsoft.com/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-windows-event-log"></a><span data-ttu-id="8cb94-119">Registra nel registro eventi di Windows</span><span class="sxs-lookup"><span data-stu-id="8cb94-119">Log to Windows Event Log</span></span>

<span data-ttu-id="8cb94-120">Il `UseWindowsService` metodo aggiunge automaticamente un provider di [registrazione](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0) che scrive messaggi di log nel registro eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="8cb94-120">The `UseWindowsService` method automatically adds a [Logging](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0) provider that writes log messages to the Windows Event Log.</span></span> <span data-ttu-id="8cb94-121">È possibile configurare la `EventLog` `Logging` registrazione per questo provider aggiungendo una voce alla sezione di o `appsettings.json` di un'altra origine della configurazione.</span><span class="sxs-lookup"><span data-stu-id="8cb94-121">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or other configuration source.</span></span> <span data-ttu-id="8cb94-122">È possibile eseguire l'override del nome di origine usato nel registro eventi impostando una `SourceName` proprietà in queste impostazioni. se non si specifica un nome, verrà usato il nome dell'applicazione predefinito, in genere il nome dell'assembly eseguibile.</span><span class="sxs-lookup"><span data-stu-id="8cb94-122">The source name used in Event Log can be overridden by setting a `SourceName` property in these settings; if you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="8cb94-123">Ulteriori informazioni sulla registrazione sono alla fine di questo capitolo.</span><span class="sxs-lookup"><span data-stu-id="8cb94-123">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="8cb94-124">Eseguire l'app come servizio Linux con systemd</span><span class="sxs-lookup"><span data-stu-id="8cb94-124">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="8cb94-125">Per configurare l'applicazione ASP.NET Core per l'esecuzione come servizio Linux (o *daemon* in Linux), installare il pacchetto [Microsoft. Extensions. Hosting. systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) da NuGet.</span><span class="sxs-lookup"><span data-stu-id="8cb94-125">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="8cb94-126">Aggiungere quindi una chiamata al `UseSystemd` `CreateHostBuilder` metodo in `Program.cs`.</span><span class="sxs-lookup"><span data-stu-id="8cb94-126">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="8cb94-127">Se l'applicazione non è in esecuzione come servizio Linux, `UseSystemd` il metodo non esegue alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="8cb94-127">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="8cb94-128">A questo punto, pubblicare l'applicazione (dipendente dal Framework o autonomo per il runtime di Linux pertinente, `linux-x64`ad esempio), da Visual Studio facendo clic con il pulsante destro del mouse sul progetto e scegliendo *pubblica* dal menu di scelta rapida o da .NET INTERFACCIA della riga di comando di base usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="8cb94-128">Now publish your application (either framework-dependent, or self-contained for the relevant Linux runtime, e.g. `linux-x64`), either from Visual Studio by right-clicking the project and choosing *Publish* from the context menu, or from the .NET Core CLI using the following command.</span></span>

```console
dotnet publish -c Release -r linux-x64 -o ./publish
```

<span data-ttu-id="8cb94-129">Copiare il contenuto completo della `publish` directory in una cartella di installazione nell'host Linux.</span><span class="sxs-lookup"><span data-stu-id="8cb94-129">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="8cb94-130">Per la registrazione del servizio è necessario aggiungere alla `/etc/systemd/system` directory un file speciale, denominato "file unità".</span><span class="sxs-lookup"><span data-stu-id="8cb94-130">Registering the service requires a special file, called a "unit file", to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="8cb94-131">È necessario disporre dell'autorizzazione radice per creare un file in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="8cb94-131">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="8cb94-132">Assegnare un nome al file con l'identificatore `systemd` che si desidera utilizzare `.service` e l'estensione.</span><span class="sxs-lookup"><span data-stu-id="8cb94-132">Name the file with the identifier you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="8cb94-133">Ad esempio `/etc/systemd/system/myapp.service`.</span><span class="sxs-lookup"><span data-stu-id="8cb94-133">For example, `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="8cb94-134">Il file del servizio usa il formato INI, come illustrato in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="8cb94-134">The service file uses INI format, as shown in this example.</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="8cb94-135">La `Type=notify` proprietà indica `systemd` che l'applicazione invierà una notifica all'avvio e all'arresto.</span><span class="sxs-lookup"><span data-stu-id="8cb94-135">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="8cb94-136">L' `WantedBy=multi-user.target` impostazione provocherà l'avvio del servizio quando il sistema Linux raggiunge "runlevel 2", vale a dire che è attiva una shell multiutente non grafica.</span><span class="sxs-lookup"><span data-stu-id="8cb94-136">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2", meaning a non-graphical multi-user shell is active.</span></span>

<span data-ttu-id="8cb94-137">Prima `systemd` che riconosca il servizio, deve ricaricare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="8cb94-137">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="8cb94-138">È possibile `systemd` controllare usando `systemctl` il comando.</span><span class="sxs-lookup"><span data-stu-id="8cb94-138">You control `systemd` using the `systemctl` command.</span></span> <span data-ttu-id="8cb94-139">Dopo il ricaricamento, utilizzare `status` il sottocomando per verificare che l'applicazione sia stata registrata correttamente.</span><span class="sxs-lookup"><span data-stu-id="8cb94-139">After reloading, use the `status` subcommand to confirm the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="8cb94-140">Se il servizio è stato configurato correttamente, verrà visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="8cb94-140">If you've configured the service correctly, the following output will be shown:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="8cb94-141">Usare il `start` comando per avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="8cb94-141">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="8cb94-142">L' `.service` estensione è facoltativa quando `systemctl start`si usa.</span><span class="sxs-lookup"><span data-stu-id="8cb94-142">The `.service` extension is optional when using `systemctl start`.</span></span>

<span data-ttu-id="8cb94-143">Per indicare `systemd` di avviare automaticamente il servizio all'avvio del sistema, usare `enable` il comando.</span><span class="sxs-lookup"><span data-stu-id="8cb94-143">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="8cb94-144">Registra in journald</span><span class="sxs-lookup"><span data-stu-id="8cb94-144">Log to journald</span></span>

<span data-ttu-id="8cb94-145">L'equivalente Linux del registro eventi di Windows è `journald`, un servizio del sistema di registrazione strutturato che `systemd`fa parte di.</span><span class="sxs-lookup"><span data-stu-id="8cb94-145">The Linux equivalent of the Windows Event Log is `journald`, a structured logging system service that is part of `systemd`.</span></span> <span data-ttu-id="8cb94-146">I messaggi di log scritti nell'output standard da un daemon Linux vengono scritti automaticamente `journald`in, quindi per configurare i livelli di registrazione `Console` , usare la sezione della configurazione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="8cb94-146">Log messages written to the standard output by a Linux daemon are automatically written to `journald`, so to configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="8cb94-147">Il `UseSystemd` metodo del generatore host configura automaticamente il formato di output della console in base al Journal.</span><span class="sxs-lookup"><span data-stu-id="8cb94-147">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="8cb94-148">Poiché `journald` è lo standard per i log di Linux, sono disponibili diversi strumenti che si integrano con esso ed è possibile indirizzare facilmente `journald` i log da a un sistema di registrazione esterno.</span><span class="sxs-lookup"><span data-stu-id="8cb94-148">Because `journald` is the standard for Linux logs, there are a variety of tools that integrate with it, and you can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="8cb94-149">Lavorando localmente nell'host, è possibile usare il `journalctl` comando per visualizzare i log dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="8cb94-149">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="8cb94-150">Se nell'host è disponibile un ambiente GUI, sono disponibili alcuni visualizzatori di log grafici per Linux, ad esempio *QJournalctl* e *GNOME-logs*.</span><span class="sxs-lookup"><span data-stu-id="8cb94-150">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="8cb94-151">Per ulteriori informazioni sull'esecuzione di query sul Journal systemd dalla riga di comando `journalctl`con, vedere [le pagine man](https://manpages.debian.org/buster/systemd/journalctl.1).</span><span class="sxs-lookup"><span data-stu-id="8cb94-151">To learn more about querying the systemd journal from the command line with `journalctl`, see [the man pages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="8cb94-152">Certificati HTTPS per le applicazioni indipendenti</span><span class="sxs-lookup"><span data-stu-id="8cb94-152">HTTPS Certificates for self-hosted applications</span></span>

<span data-ttu-id="8cb94-153">Quando si esegue un'applicazione gRPC in produzione, è necessario usare un certificato TLS da un'autorità di certificazione (CA) attendibile.</span><span class="sxs-lookup"><span data-stu-id="8cb94-153">When running a gRPC application in production, you should use a TLS certificate from a trusted Certificate Authority (CA).</span></span> <span data-ttu-id="8cb94-154">Questa CA può essere una CA pubblica o un'altra per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8cb94-154">This CA could be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="8cb94-155">Negli host Windows, il certificato può essere caricato da un [archivio certificati](https://docs.microsoft.com/windows/win32/seccrypto/managing-certificates-with-certificate-stores) protetto usando la [classe X509Store](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509store?view=netcore-3.0).</span><span class="sxs-lookup"><span data-stu-id="8cb94-155">On Windows hosts, the certificate may be loaded from a secure [Certificate Store](https://docs.microsoft.com/windows/win32/seccrypto/managing-certificates-with-certificate-stores) using the [X509Store class](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509store?view=netcore-3.0).</span></span> <span data-ttu-id="8cb94-156">La `X509Store` classe può essere usata anche con l'archivio chiavi OpenSSL in alcuni host Linux.</span><span class="sxs-lookup"><span data-stu-id="8cb94-156">The `X509Store` class can also be used with the OpenSSL key-store on some Linux hosts.</span></span>

<span data-ttu-id="8cb94-157">I certificati possono anche essere creati utilizzando uno dei [costruttori X509Certificate2](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509certificate.-ctor?view=netcore-3.0), da un file (ad esempio un `.pfx` file protetto da una password complessa) o da dati binari recuperati da un servizio di archiviazione protetto, ad esempio [Azure Key Vault ](https://azure.microsoft.com/services/key-vault/).</span><span class="sxs-lookup"><span data-stu-id="8cb94-157">Certificates may also be created using one of the [X509Certificate2 constructors](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509certificate.-ctor?view=netcore-3.0), either from a file (for example a `.pfx` file protected by a strong password), or from binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/).</span></span>

<span data-ttu-id="8cb94-158">Il gheppio può essere configurato per l'uso di un certificato in due modi: dalla configurazione o nel codice.</span><span class="sxs-lookup"><span data-stu-id="8cb94-158">Kestrel can be configured to use a certificate in two ways: from configuration, or in code.</span></span>

### <a name="set-https-certificates-using-configuration"></a><span data-ttu-id="8cb94-159">Impostare i certificati HTTPS usando la configurazione</span><span class="sxs-lookup"><span data-stu-id="8cb94-159">Set HTTPS certificates using configuration</span></span>

<span data-ttu-id="8cb94-160">Per l'approccio di configurazione è necessario impostare il percorso `.pfx` del file di certificato e la password nella sezione di configurazione di gheppio.</span><span class="sxs-lookup"><span data-stu-id="8cb94-160">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="8cb94-161">In `appsettings.json` questo aspetto sarà simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="8cb94-161">In `appsettings.json` that would look like this.</span></span>

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

<span data-ttu-id="8cb94-162">La password deve essere fornita usando un'origine di configurazione sicura, ad esempio l'insieme di credenziali delle credenziali di Azure o Hashicorp.</span><span class="sxs-lookup"><span data-stu-id="8cb94-162">The password should be provided using a secure configuration source such as Azure KeyVault or Hashicorp Vault.</span></span>

<span data-ttu-id="8cb94-163">NON è consigliabile archiviare password non crittografate nei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8cb94-163">You SHOULD NOT store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="8cb94-164">Impostare i certificati HTTPS nel codice</span><span class="sxs-lookup"><span data-stu-id="8cb94-164">Set HTTPS certificates in code</span></span>

<span data-ttu-id="8cb94-165">Per configurare HTTPS in gheppio nel codice, usare il `ConfigureKestrel` metodo su `IWebHostBuilder` nella `Program` classe.</span><span class="sxs-lookup"><span data-stu-id="8cb94-165">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

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

<span data-ttu-id="8cb94-166">Anche in questo caso, la `.pfx` password per il file deve essere archiviata e recuperata da un'origine di configurazione sicura.</span><span class="sxs-lookup"><span data-stu-id="8cb94-166">Again, the password for the `.pfx` file should be stored in and retrieved from a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8cb94-167">[Precedente](grpc-in-production.md)
>[Successivo](docker.md)</span><span class="sxs-lookup"><span data-stu-id="8cb94-167">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
