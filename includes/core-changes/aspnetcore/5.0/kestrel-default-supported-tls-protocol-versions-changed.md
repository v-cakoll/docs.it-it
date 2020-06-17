---
ms.openlocfilehash: 3244a36808fb687663241e704d08775ea5c96720
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803264"
---
### <a name="kestrel-default-supported-tls-protocol-versions-changed"></a><span data-ttu-id="e4496-101">Gheppio: versioni del protocollo TLS supportate predefinite modificate</span><span class="sxs-lookup"><span data-stu-id="e4496-101">Kestrel: Default supported TLS protocol versions changed</span></span>

<span data-ttu-id="e4496-102">Il gheppio USA ora le versioni del protocollo TLS predefinite del sistema anziché limitare le connessioni ai protocolli TLS 1,1 e TLS 1,2 come in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e4496-102">Kestrel now uses the system default TLS protocol versions rather than restricting connections to the TLS 1.1 and TLS 1.2 protocols like it did previously.</span></span>

<span data-ttu-id="e4496-103">Questa modifica consente:</span><span class="sxs-lookup"><span data-stu-id="e4496-103">This change allows:</span></span>

* <span data-ttu-id="e4496-104">TLS 1,3 da usare per impostazione predefinita negli ambienti che lo supportano.</span><span class="sxs-lookup"><span data-stu-id="e4496-104">TLS 1.3 to be used by default in environments that support it.</span></span>
* <span data-ttu-id="e4496-105">TLS 1,0 da usare in alcuni ambienti (ad esempio Windows Server 2016 per impostazione predefinita), che in genere [non è consigliabile](/security/engineering/solving-tls1-problem).</span><span class="sxs-lookup"><span data-stu-id="e4496-105">TLS 1.0 to be used in some environments (such as Windows Server 2016 by default), which is usually [not desirable](/security/engineering/solving-tls1-problem).</span></span>

<span data-ttu-id="e4496-106">Per informazioni, vedere Issue [DotNet/aspnetcore # 22563](https://github.com/dotnet/aspnetcore/issues/22563).</span><span class="sxs-lookup"><span data-stu-id="e4496-106">For discussion, see issue [dotnet/aspnetcore#22563](https://github.com/dotnet/aspnetcore/issues/22563).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e4496-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="e4496-107">Version introduced</span></span>

<span data-ttu-id="e4496-108">5,0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="e4496-108">5.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="e4496-109">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="e4496-109">Old behavior</span></span>

<span data-ttu-id="e4496-110">Il gheppio richiede che le connessioni usino TLS 1,1 o TLS 1,2 per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e4496-110">Kestrel required that connections use TLS 1.1 or TLS 1.2 by default.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="e4496-111">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="e4496-111">New behavior</span></span>

<span data-ttu-id="e4496-112">Gheppio consente al sistema operativo di scegliere il protocollo migliore da usare e di bloccare i protocolli non sicuri.</span><span class="sxs-lookup"><span data-stu-id="e4496-112">Kestrel allows the operating system to choose the best protocol to use and to block insecure protocols.</span></span> <span data-ttu-id="e4496-113"><xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType>a questo punto, il valore predefinito è `SslProtocols.None` anziché `SslProtocols.Tls12 | SslProtocols.Tls11` .</span><span class="sxs-lookup"><span data-stu-id="e4496-113"><xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType> now defaults to `SslProtocols.None` instead of `SslProtocols.Tls12 | SslProtocols.Tls11`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e4496-114">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="e4496-114">Reason for change</span></span>

<span data-ttu-id="e4496-115">Per impostazione predefinita, la modifica è stata apportata per supportare TLS 1,3 e le versioni future di TLS quando diventano disponibili.</span><span class="sxs-lookup"><span data-stu-id="e4496-115">The change was made to support TLS 1.3 and future TLS versions by default as they become available.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e4496-116">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="e4496-116">Recommended action</span></span>

<span data-ttu-id="e4496-117">A meno che l'app non abbia un motivo specifico per non farlo, è necessario usare i nuovi valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="e4496-117">Unless your app has a specific reason not to, you should use the new defaults.</span></span> <span data-ttu-id="e4496-118">Verificare che il sistema sia configurato in modo da consentire solo i protocolli protetti.</span><span class="sxs-lookup"><span data-stu-id="e4496-118">Verify your system is configured to allow only secure protocols.</span></span>

<span data-ttu-id="e4496-119">Per disabilitare i protocolli precedenti, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4496-119">To disable older protocols, take one of the following actions:</span></span>

* <span data-ttu-id="e4496-120">Disabilitare i protocolli precedenti, ad esempio TLS 1,0, a livello di sistema con le [istruzioni di Windows](/dotnet/framework/network-programming/tls#configuring-schannel-protocols-in-the-windows-registry).</span><span class="sxs-lookup"><span data-stu-id="e4496-120">Disable older protocols, such as TLS 1.0, system-wide with the [Windows instructions](/dotnet/framework/network-programming/tls#configuring-schannel-protocols-in-the-windows-registry).</span></span> <span data-ttu-id="e4496-121">Attualmente è abilitato per impostazione predefinita in tutte le versioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="e4496-121">It's currently enabled by default on all Windows versions.</span></span>
* <span data-ttu-id="e4496-122">Selezionare manualmente i protocolli che si desidera supportare nel codice nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="e4496-122">Manually select which protocols you want to support in code as follows:</span></span>

    ```csharp
    using System.Security.Authentication;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.Extensions.Hosting;

    public class Program
    {
        public static void Main(string[] args) =>
            CreateHostBuilder(args).Build().Run();

        public static IHostBuilder CreateHostBuilder(string[] args) =>
            Host.CreateDefaultBuilder(args)
                .ConfigureWebHostDefaults(webBuilder =>
                {
                    webBuilder.UseKestrel(kestrelOptions =>
                    {
                        kestrelOptions.ConfigureHttpsDefaults(httpsOptions =>
                        {
                            httpsOptions.SslProtocols = SslProtocols.Tls12 | SslProtocols.Tls13;
                        });
                    });

                    webBuilder.UseStartup<Startup>();
                });
    }
    ```

<span data-ttu-id="e4496-123">Sfortunatamente, non esiste alcuna API per escludere protocolli specifici.</span><span class="sxs-lookup"><span data-stu-id="e4496-123">Unfortunately, there's no API to exclude specific protocols.</span></span>

#### <a name="category"></a><span data-ttu-id="e4496-124">Category</span><span class="sxs-lookup"><span data-stu-id="e4496-124">Category</span></span>

<span data-ttu-id="e4496-125">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e4496-125">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e4496-126">API interessate</span><span class="sxs-lookup"><span data-stu-id="e4496-126">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`P:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols`

-->
