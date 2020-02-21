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
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="69bf3-103">Applicazioni gRPC indipendenti</span><span class="sxs-lookup"><span data-stu-id="69bf3-103">Self-hosted gRPC applications</span></span>

<span data-ttu-id="69bf3-104">Sebbene le applicazioni ASP.NET Core 3,0 possano essere ospitate in IIS in Windows Server, attualmente non è possibile ospitare un'applicazione gRPC in IIS perché alcune delle funzionalità HTTP/2 non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="69bf3-104">Although ASP.NET Core 3.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't supported.</span></span> <span data-ttu-id="69bf3-105">Questa funzionalità è un obiettivo per un futuro aggiornamento a Windows Server.</span><span class="sxs-lookup"><span data-stu-id="69bf3-105">This functionality is a goal for a future update to Windows Server.</span></span>

<span data-ttu-id="69bf3-106">È possibile eseguire l'applicazione come servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="69bf3-106">You can run your application as a Windows service.</span></span> <span data-ttu-id="69bf3-107">In alternativa, è possibile eseguirlo come servizio Linux controllato da [systemd](https://en.wikipedia.org/wiki/Systemd), a causa delle nuove funzionalità delle estensioni di hosting di .net core 3,0.</span><span class="sxs-lookup"><span data-stu-id="69bf3-107">Or you can run it as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), because of new features in the .NET Core 3.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="69bf3-108">Eseguire l'app come servizio Windows</span><span class="sxs-lookup"><span data-stu-id="69bf3-108">Run your app as a Windows service</span></span>

<span data-ttu-id="69bf3-109">Per configurare l'applicazione ASP.NET Core per l'esecuzione come servizio Windows, installare il pacchetto [Microsoft. Extensions. Hosting. WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) da NuGet.</span><span class="sxs-lookup"><span data-stu-id="69bf3-109">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="69bf3-110">Aggiungere quindi una chiamata a `UseWindowsService` al metodo `CreateHostBuilder` in `Program.cs`.</span><span class="sxs-lookup"><span data-stu-id="69bf3-110">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="69bf3-111">Se l'applicazione non è in esecuzione come servizio di Windows, il `UseWindowsService` metodo non esegue alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="69bf3-111">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="69bf3-112">A questo punto, pubblicare l'applicazione usando uno di questi metodi:</span><span class="sxs-lookup"><span data-stu-id="69bf3-112">Now publish your application by using one of these methods:</span></span>

* <span data-ttu-id="69bf3-113">In Visual Studio fare clic con il pulsante destro del mouse sul progetto e scegliere **pubblica** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="69bf3-113">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="69bf3-114">Dal interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="69bf3-114">From the .NET Core CLI.</span></span>

<span data-ttu-id="69bf3-115">Quando si pubblica un'applicazione .NET Core, è possibile scegliere di creare una distribuzione *dipendente dal Framework* o una distribuzione *autonoma* .</span><span class="sxs-lookup"><span data-stu-id="69bf3-115">When you publish a .NET Core application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="69bf3-116">Per le distribuzioni dipendenti dal Framework è necessario che il runtime condiviso di .NET Core sia installato nell'host in cui vengono eseguiti.</span><span class="sxs-lookup"><span data-stu-id="69bf3-116">Framework-dependent deployments require the .NET Core Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="69bf3-117">Le distribuzioni autosufficienti sono pubblicate con una copia completa del Framework e del runtime di .NET Core e possono essere eseguite in qualsiasi host.</span><span class="sxs-lookup"><span data-stu-id="69bf3-117">Self-contained deployments are published with a complete copy of the .NET Core runtime and framework and can be run on any host.</span></span> <span data-ttu-id="69bf3-118">Per ulteriori informazioni, inclusi i vantaggi e gli svantaggi di ogni approccio, vedere la documentazione relativa alla [distribuzione di applicazioni .NET Core](../../core/deploying/index.md) .</span><span class="sxs-lookup"><span data-stu-id="69bf3-118">For more information, including the advantages and disadvantages of each approach, see the [.NET Core application deployment](../../core/deploying/index.md) documentation.</span></span>

<span data-ttu-id="69bf3-119">Per pubblicare una compilazione autonoma dell'applicazione che non richiede l'installazione del runtime di .NET Core 3,0 nell'host, specificare il runtime da includere nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="69bf3-119">To publish a self-contained build of the application that does not require the .NET Core 3.0 runtime to be installed on the host, specify the runtime to be included with the application.</span></span> <span data-ttu-id="69bf3-120">Usare il flag `-r` (o `--runtime`).</span><span class="sxs-lookup"><span data-stu-id="69bf3-120">Use the `-r` (or `--runtime`) flag.</span></span>

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="69bf3-121">Per pubblicare una compilazione dipendente dal Framework, omettere il flag `-r`.</span><span class="sxs-lookup"><span data-stu-id="69bf3-121">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```dotnetcli
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="69bf3-122">Copiare il contenuto completo della directory `publish` in una cartella di installazione.</span><span class="sxs-lookup"><span data-stu-id="69bf3-122">Copy the complete contents of the `publish` directory to an installation folder.</span></span> <span data-ttu-id="69bf3-123">Usare quindi lo [strumento SC](/windows/desktop/services/controlling-a-service-using-sc) per creare un servizio Windows per il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="69bf3-123">Then, use the [sc tool](/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable file.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a><span data-ttu-id="69bf3-124">Accedere al registro eventi di Windows</span><span class="sxs-lookup"><span data-stu-id="69bf3-124">Log to the Windows event log</span></span>

<span data-ttu-id="69bf3-125">Il metodo `UseWindowsService` aggiunge automaticamente un provider di [registrazione](/aspnet/core/fundamentals/logging/) che scrive messaggi di log nel registro eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="69bf3-125">The `UseWindowsService` method automatically adds a [logging](/aspnet/core/fundamentals/logging/) provider that writes log messages to the Windows event log.</span></span> <span data-ttu-id="69bf3-126">È possibile configurare la registrazione per questo provider aggiungendo una voce di `EventLog` alla sezione `Logging` di `appsettings.json` o un'altra origine della configurazione.</span><span class="sxs-lookup"><span data-stu-id="69bf3-126">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or another configuration source.</span></span> 

<span data-ttu-id="69bf3-127">È possibile eseguire l'override del nome di origine usato nel registro eventi impostando una proprietà `SourceName` in queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="69bf3-127">You can override the source name used in the event log by setting a `SourceName` property in these settings.</span></span> <span data-ttu-id="69bf3-128">Se non si specifica un nome, verrà usato il nome predefinito dell'applicazione, in genere il nome dell'assembly eseguibile.</span><span class="sxs-lookup"><span data-stu-id="69bf3-128">If you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="69bf3-129">Ulteriori informazioni sulla registrazione sono alla fine di questo capitolo.</span><span class="sxs-lookup"><span data-stu-id="69bf3-129">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="69bf3-130">Eseguire l'app come servizio Linux con systemd</span><span class="sxs-lookup"><span data-stu-id="69bf3-130">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="69bf3-131">Per configurare l'applicazione ASP.NET Core per l'esecuzione come servizio Linux (o *daemon* in Linux), installare il pacchetto [Microsoft. Extensions. Hosting. systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) da NuGet.</span><span class="sxs-lookup"><span data-stu-id="69bf3-131">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="69bf3-132">Aggiungere quindi una chiamata a `UseSystemd` al metodo `CreateHostBuilder` in `Program.cs`.</span><span class="sxs-lookup"><span data-stu-id="69bf3-132">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="69bf3-133">Se l'applicazione non è in esecuzione come servizio Linux, il `UseSystemd` metodo non esegue alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="69bf3-133">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="69bf3-134">A questo punto, pubblicare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="69bf3-134">Now publish your application.</span></span> <span data-ttu-id="69bf3-135">L'applicazione può essere dipendente dal Framework o indipendente per il runtime di Linux pertinente, ad esempio `linux-x64`.</span><span class="sxs-lookup"><span data-stu-id="69bf3-135">The application can be either framework dependent or self-contained for the relevant Linux runtime (for example, `linux-x64`).</span></span> <span data-ttu-id="69bf3-136">È possibile pubblicare utilizzando uno di questi metodi:</span><span class="sxs-lookup"><span data-stu-id="69bf3-136">You can publish by using one of these methods:</span></span>

* <span data-ttu-id="69bf3-137">In Visual Studio fare clic con il pulsante destro del mouse sul progetto e scegliere **pubblica** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="69bf3-137">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span> 
* <span data-ttu-id="69bf3-138">Dal interfaccia della riga di comando di .NET Core, usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="69bf3-138">From the .NET Core CLI, by using the following command:</span></span>

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
<span data-ttu-id="69bf3-139">Copiare il contenuto completo della directory `publish` in una cartella di installazione nell'host Linux.</span><span class="sxs-lookup"><span data-stu-id="69bf3-139">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="69bf3-140">Per la registrazione del servizio è necessario aggiungere un file speciale, denominato *file di unità*, alla directory `/etc/systemd/system`.</span><span class="sxs-lookup"><span data-stu-id="69bf3-140">Registering the service requires a special file, called a *unit file*, to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="69bf3-141">È necessario disporre dell'autorizzazione radice per creare un file in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="69bf3-141">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="69bf3-142">Assegnare un nome al file con l'identificatore che si desidera utilizzare `systemd` e l'estensione `.service`.</span><span class="sxs-lookup"><span data-stu-id="69bf3-142">Name the file with the identifier that you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="69bf3-143">Ad esempio, usare `/etc/systemd/system/myapp.service`.</span><span class="sxs-lookup"><span data-stu-id="69bf3-143">For example, use `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="69bf3-144">Il file del servizio usa il formato INI, come illustrato in questo esempio:</span><span class="sxs-lookup"><span data-stu-id="69bf3-144">The service file uses INI format, as shown in this example:</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="69bf3-145">La proprietà `Type=notify` indica `systemd` che l'applicazione invierà una notifica all'avvio e all'arresto.</span><span class="sxs-lookup"><span data-stu-id="69bf3-145">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="69bf3-146">L'impostazione `WantedBy=multi-user.target` provocherà l'avvio del servizio quando il sistema Linux raggiunge "runlevel 2", il che significa che è attiva una shell multiutente non grafica.</span><span class="sxs-lookup"><span data-stu-id="69bf3-146">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2," which means a non-graphical multi-user shell is active.</span></span>

<span data-ttu-id="69bf3-147">Prima che `systemd` riconosca il servizio, sarà necessario ricaricare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="69bf3-147">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="69bf3-148">È possibile controllare `systemd` usando il comando `systemctl`.</span><span class="sxs-lookup"><span data-stu-id="69bf3-148">You control `systemd` by using the `systemctl` command.</span></span> <span data-ttu-id="69bf3-149">Dopo il ricaricamento, utilizzare il sottocomando `status` per verificare che l'applicazione sia stata registrata correttamente.</span><span class="sxs-lookup"><span data-stu-id="69bf3-149">After reloading, use the `status` subcommand to confirm that the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="69bf3-150">Se il servizio è stato configurato correttamente, si otterrà l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="69bf3-150">If you've configured the service correctly, you'll get the following output:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="69bf3-151">Usare il comando `start` per avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="69bf3-151">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="69bf3-152">L'estensione `.service` è facoltativa quando si usa `systemctl start`.</span><span class="sxs-lookup"><span data-stu-id="69bf3-152">The `.service` extension is optional when you're using `systemctl start`.</span></span>

<span data-ttu-id="69bf3-153">Per indicare `systemd` avviare automaticamente il servizio all'avvio del sistema, usare il comando `enable`.</span><span class="sxs-lookup"><span data-stu-id="69bf3-153">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="69bf3-154">Registra in journald</span><span class="sxs-lookup"><span data-stu-id="69bf3-154">Log to journald</span></span>

<span data-ttu-id="69bf3-155">L'equivalente Linux del registro eventi di Windows è `journald`, un servizio del sistema di registrazione strutturato che fa parte di `systemd`.</span><span class="sxs-lookup"><span data-stu-id="69bf3-155">The Linux equivalent of the Windows event log is `journald`, a structured logging system service that's part of `systemd`.</span></span> <span data-ttu-id="69bf3-156">I messaggi di log scritti nell'output standard da un daemon Linux vengono scritti automaticamente in `journald`.</span><span class="sxs-lookup"><span data-stu-id="69bf3-156">Log messages written to the standard output by a Linux daemon are automatically written to `journald`.</span></span> <span data-ttu-id="69bf3-157">Per configurare i livelli di registrazione, usare la sezione `Console` della configurazione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="69bf3-157">To configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="69bf3-158">Il metodo del generatore host `UseSystemd` configura automaticamente il formato di output della console in base al Journal.</span><span class="sxs-lookup"><span data-stu-id="69bf3-158">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="69bf3-159">Poiché `journald` è lo standard per i log Linux, un'ampia gamma di strumenti si integrano con esso.</span><span class="sxs-lookup"><span data-stu-id="69bf3-159">Because `journald` is the standard for Linux logs, a variety of tools integrate with it.</span></span> <span data-ttu-id="69bf3-160">È possibile instradare facilmente i log da `journald` a un sistema di registrazione esterno.</span><span class="sxs-lookup"><span data-stu-id="69bf3-160">You can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="69bf3-161">Lavorando localmente nell'host, è possibile usare il comando `journalctl` per visualizzare i log dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="69bf3-161">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="69bf3-162">Se nell'host è disponibile un ambiente GUI, sono disponibili alcuni visualizzatori di log grafici per Linux, ad esempio *QJournalctl* e *GNOME-logs*.</span><span class="sxs-lookup"><span data-stu-id="69bf3-162">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="69bf3-163">Per ulteriori informazioni sull'esecuzione di query sul Journal `systemd` dalla riga di comando tramite `journalctl`, vedere [le pagine man](https://manpages.debian.org/buster/systemd/journalctl.1).</span><span class="sxs-lookup"><span data-stu-id="69bf3-163">To learn more about querying the `systemd` journal from the command line by using `journalctl`, see [the man pages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="69bf3-164">Certificati HTTPS per le applicazioni indipendenti</span><span class="sxs-lookup"><span data-stu-id="69bf3-164">HTTPS certificates for self-hosted applications</span></span>

<span data-ttu-id="69bf3-165">Quando si esegue un'applicazione gRPC in produzione, è necessario usare un certificato TLS da un'autorità di certificazione (CA) attendibile.</span><span class="sxs-lookup"><span data-stu-id="69bf3-165">When you're running a gRPC application in production, you should use a TLS certificate from a trusted certificate authority (CA).</span></span> <span data-ttu-id="69bf3-166">Questa CA può essere una CA pubblica o una interna per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="69bf3-166">This CA might be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="69bf3-167">Negli host Windows è possibile caricare il certificato da un [archivio certificati](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) protetto usando la classe <xref:System.Security.Cryptography.X509Certificates.X509Store>.</span><span class="sxs-lookup"><span data-stu-id="69bf3-167">On Windows hosts, you can load the certificate from a secure [certificate store](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) by using the <xref:System.Security.Cryptography.X509Certificates.X509Store> class.</span></span> <span data-ttu-id="69bf3-168">È anche possibile usare la classe `X509Store` con l'archivio chiavi OpenSSL in alcuni host Linux.</span><span class="sxs-lookup"><span data-stu-id="69bf3-168">You can also use the `X509Store` class with the OpenSSL key store on some Linux hosts.</span></span>

<span data-ttu-id="69bf3-169">È anche possibile creare certificati usando uno dei [costruttori X509Certificate2](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), da uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="69bf3-169">You can also create certificates by using one of the [X509Certificate2 constructors](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), from either:</span></span>

* <span data-ttu-id="69bf3-170">Un file, ad esempio un file di `.pfx` protetto da una password complessa</span><span class="sxs-lookup"><span data-stu-id="69bf3-170">A file, such as a `.pfx` file protected by a strong password</span></span>
* <span data-ttu-id="69bf3-171">Dati binari recuperati da un servizio di archiviazione sicura, ad esempio [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span><span class="sxs-lookup"><span data-stu-id="69bf3-171">Binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span></span>

<span data-ttu-id="69bf3-172">È possibile configurare gheppio per l'uso di un certificato in due modi: dalla configurazione o nel codice.</span><span class="sxs-lookup"><span data-stu-id="69bf3-172">You can configure Kestrel to use a certificate in two ways: from configuration or in code.</span></span>

### <a name="set-https-certificates-by-using-configuration"></a><span data-ttu-id="69bf3-173">Impostare i certificati HTTPS usando la configurazione</span><span class="sxs-lookup"><span data-stu-id="69bf3-173">Set HTTPS certificates by using configuration</span></span>

<span data-ttu-id="69bf3-174">Per l'approccio di configurazione è necessario impostare il percorso del certificato `.pfx` file e la password nella sezione di configurazione di gheppio.</span><span class="sxs-lookup"><span data-stu-id="69bf3-174">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="69bf3-175">In `appsettings.json`, avrà un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="69bf3-175">In `appsettings.json`, that would look like this:</span></span>

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

<span data-ttu-id="69bf3-176">Fornire la password usando un'origine di configurazione sicura, ad esempio Azure Key Vault o Hashicorp Vault.</span><span class="sxs-lookup"><span data-stu-id="69bf3-176">Provide the password by using a secure configuration source such as Azure Key Vault or Hashicorp Vault.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69bf3-177">Non archiviare password non crittografate nei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="69bf3-177">Don't store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="69bf3-178">Impostare i certificati HTTPS nel codice</span><span class="sxs-lookup"><span data-stu-id="69bf3-178">Set HTTPS certificates in code</span></span>

<span data-ttu-id="69bf3-179">Per configurare HTTPS in gheppio nel codice, usare il metodo `ConfigureKestrel` su `IWebHostBuilder` nella classe `Program`.</span><span class="sxs-lookup"><span data-stu-id="69bf3-179">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

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

<span data-ttu-id="69bf3-180">Anche in questo caso, assicurarsi di archiviare la password per il file di `.pfx` in e recuperarla da un'origine di configurazione sicura.</span><span class="sxs-lookup"><span data-stu-id="69bf3-180">Again, be sure to store the password for the `.pfx` file in, and retrieve it from, a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="69bf3-181">[Precedente](grpc-in-production.md)
>[Successivo](docker.md)</span><span class="sxs-lookup"><span data-stu-id="69bf3-181">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
