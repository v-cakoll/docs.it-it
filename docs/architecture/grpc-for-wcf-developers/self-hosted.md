---
title: Applicazioni gRPC self-hosted - gRPC per gli sviluppatori WCFSelf-hosted gRPC applications - gRPC for WCF developers
description: Distribuzione di applicazioni gRPC ASP.NET Core come servizi self-hosted.
ms.date: 09/02/2019
ms.openlocfilehash: 69f70e4077247fd07eba7abeee82f257dd1f4f90
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80110906"
---
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="a83bb-103">Applicazioni gRPC auto-ospitate</span><span class="sxs-lookup"><span data-stu-id="a83bb-103">Self-hosted gRPC applications</span></span>

<span data-ttu-id="a83bb-104">Sebbene ASP.NET applicazioni Core 3.0 possano essere ospitate in IIS in Windows Server, attualmente non è possibile ospitare un'applicazione gRPC in IIS perché alcune delle funzionalità HTTP/2 non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="a83bb-104">Although ASP.NET Core 3.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't supported.</span></span> <span data-ttu-id="a83bb-105">Questa funzionalità è un obiettivo per un aggiornamento futuro di Windows Server.This functionality is a goal for a future update to Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a83bb-105">This functionality is a goal for a future update to Windows Server.</span></span>

<span data-ttu-id="a83bb-106">È possibile eseguire l'applicazione come servizio Windows.You can run your application as a Windows service.</span><span class="sxs-lookup"><span data-stu-id="a83bb-106">You can run your application as a Windows service.</span></span> <span data-ttu-id="a83bb-107">In alternativa, è possibile eseguirlo come un servizio Linux controllato da [systemd](https://en.wikipedia.org/wiki/Systemd), a causa delle nuove funzionalità nelle estensioni di hosting di .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="a83bb-107">Or you can run it as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), because of new features in the .NET Core 3.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="a83bb-108">Eseguire l'app come servizio WindowsRun your app as a Windows service</span><span class="sxs-lookup"><span data-stu-id="a83bb-108">Run your app as a Windows service</span></span>

<span data-ttu-id="a83bb-109">Per configurare l'applicazione ASP.NET Core per l'esecuzione come servizio Windows, installare il pacchetto Microsoft.Extensions.Hosting.WindowsServices da NuGet.To configure your Application a Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span><span class="sxs-lookup"><span data-stu-id="a83bb-109">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="a83bb-110">Aggiungere quindi una `UseWindowsService` chiamata `CreateHostBuilder` a `Program.cs`al metodo in .</span><span class="sxs-lookup"><span data-stu-id="a83bb-110">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="a83bb-111">Se l'applicazione non è in esecuzione `UseWindowsService` come servizio Windows, il metodo non esegue alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="a83bb-111">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="a83bb-112">Pubblicare ora l'applicazione utilizzando uno di questi metodi:Now publish your application by using one of these methods:</span><span class="sxs-lookup"><span data-stu-id="a83bb-112">Now publish your application by using one of these methods:</span></span>

* <span data-ttu-id="a83bb-113">In Visual Studio fare clic con il pulsante destro del mouse sul progetto e **scegliere Pubblica** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="a83bb-113">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="a83bb-114">Dalla CLI di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a83bb-114">From the .NET Core CLI.</span></span>

<span data-ttu-id="a83bb-115">Quando si pubblica un'applicazione .NET Core, è possibile scegliere di creare una distribuzione *dipendente dal framework* o una distribuzione *autonoma.*</span><span class="sxs-lookup"><span data-stu-id="a83bb-115">When you publish a .NET Core application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="a83bb-116">Le distribuzioni dipendenti da Framework richiedono l'installazione del runtime condiviso .NET Core nell'host in cui vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="a83bb-116">Framework-dependent deployments require the .NET Core Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="a83bb-117">Le distribuzioni autonome vengono pubblicate con una copia completa del runtime e del framework .NET Core e possono essere eseguite in qualsiasi host.</span><span class="sxs-lookup"><span data-stu-id="a83bb-117">Self-contained deployments are published with a complete copy of the .NET Core runtime and framework and can be run on any host.</span></span> <span data-ttu-id="a83bb-118">Per altre informazioni, inclusi i vantaggi e gli svantaggi di ogni approccio, vedere la documentazione relativa alla distribuzione di applicazioni [.NET Core.For](../../core/deploying/index.md) more information, including the advantages and disadvantages of each approach, see the .NET Core application deployment documentation.</span><span class="sxs-lookup"><span data-stu-id="a83bb-118">For more information, including the advantages and disadvantages of each approach, see the [.NET Core application deployment](../../core/deploying/index.md) documentation.</span></span>

<span data-ttu-id="a83bb-119">Per pubblicare una compilazione autonoma dell'applicazione che non richiede l'installazione del runtime di .NET Core 3.0 nell'host, specificare il runtime da includere nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a83bb-119">To publish a self-contained build of the application that does not require the .NET Core 3.0 runtime to be installed on the host, specify the runtime to be included with the application.</span></span> <span data-ttu-id="a83bb-120">Utilizzare `-r` il `--runtime`flag (o).</span><span class="sxs-lookup"><span data-stu-id="a83bb-120">Use the `-r` (or `--runtime`) flag.</span></span>

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="a83bb-121">Per pubblicare una compilazione dipendente `-r` dal framework, omettere il flag.</span><span class="sxs-lookup"><span data-stu-id="a83bb-121">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```dotnetcli
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="a83bb-122">Copiare il contenuto `publish` completo della directory in una cartella di installazione.</span><span class="sxs-lookup"><span data-stu-id="a83bb-122">Copy the complete contents of the `publish` directory to an installation folder.</span></span> <span data-ttu-id="a83bb-123">Quindi, utilizzare [lo strumento sc](/windows/desktop/services/controlling-a-service-using-sc) per creare un servizio di Windows per il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="a83bb-123">Then, use the [sc tool](/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable file.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a><span data-ttu-id="a83bb-124">Accedere al registro eventi di Windows</span><span class="sxs-lookup"><span data-stu-id="a83bb-124">Log to the Windows event log</span></span>

<span data-ttu-id="a83bb-125">Il `UseWindowsService` metodo aggiunge automaticamente un provider di [registrazione](/aspnet/core/fundamentals/logging/) che scrive i messaggi di log nel registro eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="a83bb-125">The `UseWindowsService` method automatically adds a [logging](/aspnet/core/fundamentals/logging/) provider that writes log messages to the Windows event log.</span></span> <span data-ttu-id="a83bb-126">È possibile configurare la registrazione `EventLog` per `Logging` questo `appsettings.json` provider aggiungendo una voce alla sezione o a un'altra origine di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a83bb-126">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or another configuration source.</span></span>

<span data-ttu-id="a83bb-127">È possibile sostituire il nome di origine `SourceName` utilizzato nel registro eventi impostando una proprietà in queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a83bb-127">You can override the source name used in the event log by setting a `SourceName` property in these settings.</span></span> <span data-ttu-id="a83bb-128">Se non si specifica un nome, verrà utilizzato il nome dell'applicazione predefinita (in genere il nome dell'assembly eseguibile).</span><span class="sxs-lookup"><span data-stu-id="a83bb-128">If you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="a83bb-129">Ulteriori informazioni sulla registrazione sono alla fine di questo capitolo.</span><span class="sxs-lookup"><span data-stu-id="a83bb-129">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="a83bb-130">Eseguire l'app come servizio Linux con sistema</span><span class="sxs-lookup"><span data-stu-id="a83bb-130">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="a83bb-131">Per configurare l'applicazione ASP.NET Core per l'esecuzione come servizio Linux (o daemon nel linguaggio Linux), installare il pacchetto [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) da NuGet.To configure your Application ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the Microsoft.Extensions.Hosting.Systemd package from NuGet.</span><span class="sxs-lookup"><span data-stu-id="a83bb-131">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="a83bb-132">Aggiungere quindi una `UseSystemd` chiamata `CreateHostBuilder` a `Program.cs`al metodo in .</span><span class="sxs-lookup"><span data-stu-id="a83bb-132">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="a83bb-133">Se l'applicazione non è in esecuzione `UseSystemd` come servizio Linux, il metodo non esegue alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="a83bb-133">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="a83bb-134">Pubblicare ora l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a83bb-134">Now publish your application.</span></span> <span data-ttu-id="a83bb-135">L'applicazione può essere dipendente dal framework o autonoma per `linux-x64`il runtime Linux pertinente (ad esempio, ).</span><span class="sxs-lookup"><span data-stu-id="a83bb-135">The application can be either framework dependent or self-contained for the relevant Linux runtime (for example, `linux-x64`).</span></span> <span data-ttu-id="a83bb-136">È possibile pubblicare utilizzando uno dei seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="a83bb-136">You can publish by using one of these methods:</span></span>

* <span data-ttu-id="a83bb-137">In Visual Studio fare clic con il pulsante destro del mouse sul progetto e **scegliere Pubblica** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="a83bb-137">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="a83bb-138">Dalla CLI di .NET Core, utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a83bb-138">From the .NET Core CLI, by using the following command:</span></span>

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
<span data-ttu-id="a83bb-139">Copiare il contenuto `publish` completo della directory in una cartella di installazione nell'host Linux.</span><span class="sxs-lookup"><span data-stu-id="a83bb-139">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="a83bb-140">La registrazione del servizio richiede l'aggiunta di un file `/etc/systemd/system` speciale, denominato file di *unità,* alla directory.</span><span class="sxs-lookup"><span data-stu-id="a83bb-140">Registering the service requires a special file, called a *unit file*, to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="a83bb-141">È necessaria l'autorizzazione root per creare un file in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="a83bb-141">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="a83bb-142">Assegnare al file il `systemd` nome con `.service` l'identificatore che si desidera utilizzare e l'estensione.</span><span class="sxs-lookup"><span data-stu-id="a83bb-142">Name the file with the identifier that you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="a83bb-143">Ad esempio, usare `/etc/systemd/system/myapp.service`.</span><span class="sxs-lookup"><span data-stu-id="a83bb-143">For example, use `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="a83bb-144">Il file del servizio usa il formato INI, come illustrato nell'esempio seguente:The service file uses INI format, as shown in this example:</span><span class="sxs-lookup"><span data-stu-id="a83bb-144">The service file uses INI format, as shown in this example:</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="a83bb-145">La `Type=notify` proprietà `systemd` indica che l'applicazione invierà una notifica all'avvio e all'arresto.</span><span class="sxs-lookup"><span data-stu-id="a83bb-145">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="a83bb-146">L'impostazione `WantedBy=multi-user.target` causerà l'avvio del servizio quando il sistema Linux raggiunge il "runlevel 2", il che significa che è attiva una shell non grafica e multiutente.</span><span class="sxs-lookup"><span data-stu-id="a83bb-146">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2," which means a non-graphical, multi-user shell is active.</span></span>

<span data-ttu-id="a83bb-147">Prima `systemd` di riconoscere il servizio, è necessario ricaricare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="a83bb-147">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="a83bb-148">È `systemd` possibile controllare `systemctl` utilizzando il comando .</span><span class="sxs-lookup"><span data-stu-id="a83bb-148">You control `systemd` by using the `systemctl` command.</span></span> <span data-ttu-id="a83bb-149">Dopo il ricaricamento, utilizzare il `status` sottocomando per verificare che l'applicazione sia stata registrata correttamente.</span><span class="sxs-lookup"><span data-stu-id="a83bb-149">After reloading, use the `status` subcommand to confirm that the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="a83bb-150">Se il servizio è stato configurato correttamente, si otterrà il seguente output:</span><span class="sxs-lookup"><span data-stu-id="a83bb-150">If you've configured the service correctly, you'll get the following output:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="a83bb-151">Utilizzare `start` il comando per avviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="a83bb-151">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="a83bb-152">L'estensione `.service` è facoltativa quando `systemctl start`si utilizza .</span><span class="sxs-lookup"><span data-stu-id="a83bb-152">The `.service` extension is optional when you're using `systemctl start`.</span></span>

<span data-ttu-id="a83bb-153">Per `systemd` indicare di avviare automaticamente il `enable` servizio all'avvio del sistema, utilizzare il comando .</span><span class="sxs-lookup"><span data-stu-id="a83bb-153">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="a83bb-154">Registra nel journal</span><span class="sxs-lookup"><span data-stu-id="a83bb-154">Log to journald</span></span>

<span data-ttu-id="a83bb-155">L'equivalente Linux del registro eventi di Windows è `journald`, `systemd`un servizio di sistema di registrazione strutturata che fa parte di .</span><span class="sxs-lookup"><span data-stu-id="a83bb-155">The Linux equivalent of the Windows event log is `journald`, a structured logging system service that's part of `systemd`.</span></span> <span data-ttu-id="a83bb-156">I messaggi di log scritti nell'output standard di `journald`un daemon Linux vengono scritti automaticamente in .</span><span class="sxs-lookup"><span data-stu-id="a83bb-156">Log messages written to the standard output by a Linux daemon are automatically written to `journald`.</span></span> <span data-ttu-id="a83bb-157">Per configurare i `Console` livelli di registrazione, utilizzare la sezione della configurazione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="a83bb-157">To configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="a83bb-158">Il `UseSystemd` metodo del generatore host configura automaticamente il formato di output della console in base al journal.</span><span class="sxs-lookup"><span data-stu-id="a83bb-158">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="a83bb-159">Poiché `journald` è lo standard per i log Linux, una varietà di strumenti si integra con esso.</span><span class="sxs-lookup"><span data-stu-id="a83bb-159">Because `journald` is the standard for Linux logs, a variety of tools integrate with it.</span></span> <span data-ttu-id="a83bb-160">È possibile instradare facilmente i registri da `journald` un sistema di registrazione esterno.</span><span class="sxs-lookup"><span data-stu-id="a83bb-160">You can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="a83bb-161">Lavorando localmente sull'host, `journalctl` è possibile utilizzare il comando per visualizzare i registri dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="a83bb-161">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="a83bb-162">Se nell'host è disponibile un ambiente GUI, sono disponibili alcuni visualizzatori di log grafici per Linux, ad esempio *QJournalctl* e *gnome-logs*.</span><span class="sxs-lookup"><span data-stu-id="a83bb-162">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="a83bb-163">Per ulteriori informazioni sull'esecuzione di query `systemd` `journalctl`sul journal dalla riga di comando utilizzando , vedere [manpages](https://manpages.debian.org/buster/systemd/journalctl.1).</span><span class="sxs-lookup"><span data-stu-id="a83bb-163">To learn more about querying the `systemd` journal from the command line by using `journalctl`, see [the manpages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="a83bb-164">Certificati HTTPS per applicazioni self-hosted</span><span class="sxs-lookup"><span data-stu-id="a83bb-164">HTTPS certificates for self-hosted applications</span></span>

<span data-ttu-id="a83bb-165">Quando si esegue un'applicazione gRPC nell'ambiente di produzione, è necessario utilizzare un certificato TLS da un'autorità di certificazione (CA) attendibile.</span><span class="sxs-lookup"><span data-stu-id="a83bb-165">When you're running a gRPC application in production, you should use a TLS certificate from a trusted certificate authority (CA).</span></span> <span data-ttu-id="a83bb-166">Questa CA può essere una CA pubblica o interna per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a83bb-166">This CA might be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="a83bb-167">Negli host Windows è possibile caricare il certificato da <xref:System.Security.Cryptography.X509Certificates.X509Store> un [archivio certificati](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) protetto utilizzando la classe .</span><span class="sxs-lookup"><span data-stu-id="a83bb-167">On Windows hosts, you can load the certificate from a secure [certificate store](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) by using the <xref:System.Security.Cryptography.X509Certificates.X509Store> class.</span></span> <span data-ttu-id="a83bb-168">È anche possibile `X509Store` usare la classe con l'archivio chiavi OpenSSL su alcuni host Linux.You can also use the class with the OpenSSL key store on some Linux hosts.</span><span class="sxs-lookup"><span data-stu-id="a83bb-168">You can also use the `X509Store` class with the OpenSSL key store on some Linux hosts.</span></span>

<span data-ttu-id="a83bb-169">È inoltre possibile creare certificati utilizzando uno dei [costruttori X509Certificate2](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), da:</span><span class="sxs-lookup"><span data-stu-id="a83bb-169">You can also create certificates by using one of the [X509Certificate2 constructors](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), from either:</span></span>

* <span data-ttu-id="a83bb-170">Un file, ad `.pfx` esempio un file protetto da una password complessa</span><span class="sxs-lookup"><span data-stu-id="a83bb-170">A file, such as a `.pfx` file protected by a strong password</span></span>
* <span data-ttu-id="a83bb-171">Dati binari recuperati da un servizio di archiviazione sicuro, ad esempio Archiviazione guidata chiavi di [AzureBinary data](https://azure.microsoft.com/services/key-vault/) retrieved from a secure storage service such as Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="a83bb-171">Binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span></span>

<span data-ttu-id="a83bb-172">È possibile configurare Kestrel per l'utilizzo di un certificato in due modi: dalla configurazione o nel codice.</span><span class="sxs-lookup"><span data-stu-id="a83bb-172">You can configure Kestrel to use a certificate in two ways: from configuration or in code.</span></span>

### <a name="set-https-certificates-by-using-configuration"></a><span data-ttu-id="a83bb-173">Impostare i certificati HTTPS tramite la configurazioneSet HTTPS certificates by using configuration</span><span class="sxs-lookup"><span data-stu-id="a83bb-173">Set HTTPS certificates by using configuration</span></span>

<span data-ttu-id="a83bb-174">L'approccio di configurazione richiede `.pfx` l'impostazione del percorso del file del certificato e della password nella sezione di configurazione di Kestrel.</span><span class="sxs-lookup"><span data-stu-id="a83bb-174">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="a83bb-175">In `appsettings.json`, che sarebbe simile a questo:</span><span class="sxs-lookup"><span data-stu-id="a83bb-175">In `appsettings.json`, that would look like this:</span></span>

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

<span data-ttu-id="a83bb-176">Fornire la password usando un'origine di configurazione sicura, ad esempio Azure Key Vault o Hashicorp Vault.Provide the password by using a secure configuration source such as Azure Key Vault or Hashicorp Vault.</span><span class="sxs-lookup"><span data-stu-id="a83bb-176">Provide the password by using a secure configuration source such as Azure Key Vault or Hashicorp Vault.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a83bb-177">Non archiviare password non crittografate nei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a83bb-177">Don't store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="a83bb-178">Impostare i certificati HTTPS nel codiceSet HTTPS certificates in code</span><span class="sxs-lookup"><span data-stu-id="a83bb-178">Set HTTPS certificates in code</span></span>

<span data-ttu-id="a83bb-179">Per configurare HTTPS su Kestrel `ConfigureKestrel` nel `IWebHostBuilder` codice, utilizzare il metodo on nella `Program` classe.</span><span class="sxs-lookup"><span data-stu-id="a83bb-179">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

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

<span data-ttu-id="a83bb-180">Anche in questo caso, assicurarsi di archiviare la password per il `.pfx` file in e recuperarlo da un'origine di configurazione sicura.</span><span class="sxs-lookup"><span data-stu-id="a83bb-180">Again, be sure to store the password for the `.pfx` file in, and retrieve it from, a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a83bb-181">[Successivo](grpc-in-production.md)
>[precedente](docker.md)</span><span class="sxs-lookup"><span data-stu-id="a83bb-181">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
