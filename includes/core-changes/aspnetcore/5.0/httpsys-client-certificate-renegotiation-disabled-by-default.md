---
ms.openlocfilehash: 9a747d8fc15ca8fa2b915f89291f118d7344d172
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325237"
---
### <a name="httpsys-client-certificate-renegotiation-disabled-by-default"></a><span data-ttu-id="9cf7b-101">HttpSys: rinegoziazione certificato client disabilitata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="9cf7b-101">HttpSys: Client certificate renegotiation disabled by default</span></span>

<span data-ttu-id="9cf7b-102">L'opzione per rinegoziare una connessione e richiedere un certificato client è stata disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9cf7b-102">The option to renegotiate a connection and request a client certificate has been disabled by default.</span></span> <span data-ttu-id="9cf7b-103">Per informazioni, vedere Issue [DotNet/aspnetcore # 23181](https://github.com/dotnet/aspnetcore/issues/23181).</span><span class="sxs-lookup"><span data-stu-id="9cf7b-103">For discussion, see issue [dotnet/aspnetcore#23181](https://github.com/dotnet/aspnetcore/issues/23181).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9cf7b-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="9cf7b-104">Version introduced</span></span>

<span data-ttu-id="9cf7b-105">ASP.NET Core 5,0</span><span class="sxs-lookup"><span data-stu-id="9cf7b-105">ASP.NET Core 5.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="9cf7b-106">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="9cf7b-106">Old behavior</span></span>

<span data-ttu-id="9cf7b-107">È possibile rinegoziare la connessione per richiedere un certificato client.</span><span class="sxs-lookup"><span data-stu-id="9cf7b-107">The connection can be renegotiated to request a client certificate.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="9cf7b-108">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="9cf7b-108">New behavior</span></span>

<span data-ttu-id="9cf7b-109">I certificati client possono essere richiesti solo durante l'handshake di connessione iniziale.</span><span class="sxs-lookup"><span data-stu-id="9cf7b-109">Client certificates can only be requested during the initial connection handshake.</span></span> <span data-ttu-id="9cf7b-110">Per altre informazioni, vedere richiesta pull [DotNet/aspnetcore # 23162](https://github.com/dotnet/aspnetcore/pull/23162).</span><span class="sxs-lookup"><span data-stu-id="9cf7b-110">For more information, see pull request [dotnet/aspnetcore#23162](https://github.com/dotnet/aspnetcore/pull/23162).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="9cf7b-111">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="9cf7b-111">Reason for change</span></span>

<span data-ttu-id="9cf7b-112">La rinegoziazione ha causato un certo numero di problemi di prestazioni e deadlock.</span><span class="sxs-lookup"><span data-stu-id="9cf7b-112">Renegotiation caused a number of performance and deadlock issues.</span></span> <span data-ttu-id="9cf7b-113">Non è inoltre supportata in HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="9cf7b-113">It's also not supported in HTTP/2.</span></span> <span data-ttu-id="9cf7b-114">Per un contesto aggiuntivo da quando l'opzione per controllare questo comportamento è stata introdotta in ASP.NET Core 3,1, vedere Issue [DotNet/aspnetcore # 14806](https://github.com/dotnet/aspnetcore/issues/14806).</span><span class="sxs-lookup"><span data-stu-id="9cf7b-114">For additional context from when the option to control this behavior was introduced in ASP.NET Core 3.1, see issue [dotnet/aspnetcore#14806](https://github.com/dotnet/aspnetcore/issues/14806).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9cf7b-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="9cf7b-115">Recommended action</span></span>

<span data-ttu-id="9cf7b-116">Le app che richiedono certificati client devono usare *netsh.exe* per impostare l' `clientcertnegotiation` opzione su `enabled` .</span><span class="sxs-lookup"><span data-stu-id="9cf7b-116">Apps that require client certificates should use *netsh.exe* to set the `clientcertnegotiation` option to `enabled`.</span></span> <span data-ttu-id="9cf7b-117">Per ulteriori informazioni, vedere [comandi netsh http](/windows-server/networking/technologies/netsh/netsh-http).</span><span class="sxs-lookup"><span data-stu-id="9cf7b-117">For more information, see [netsh http commands](/windows-server/networking/technologies/netsh/netsh-http).</span></span>

<span data-ttu-id="9cf7b-118">Se si vuole che i certificati client siano abilitati solo per alcune parti dell'app, vedere le linee guida per i [certificati client facoltativi](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates).</span><span class="sxs-lookup"><span data-stu-id="9cf7b-118">If you want client certificates enabled for only some parts of your app, see the guidance at [Optional client certificates](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates).</span></span>

<span data-ttu-id="9cf7b-119">Se è necessario il comportamento precedente della rinegoziazione, impostare sul `HttpSysOptions.ClientCertificateMethod` valore precedente `ClientCertificateMethod.AllowRenegotiate` .</span><span class="sxs-lookup"><span data-stu-id="9cf7b-119">If you need the old renegotiate behavior, set `HttpSysOptions.ClientCertificateMethod` to the old value `ClientCertificateMethod.AllowRenegotiate`.</span></span> <span data-ttu-id="9cf7b-120">Questa operazione non è consigliata per i motivi illustrati sopra e nelle linee guida collegate.</span><span class="sxs-lookup"><span data-stu-id="9cf7b-120">This isn't recommended for the reasons outlined above and in the linked guidance.</span></span>

#### <a name="category"></a><span data-ttu-id="9cf7b-121">Category</span><span class="sxs-lookup"><span data-stu-id="9cf7b-121">Category</span></span>

<span data-ttu-id="9cf7b-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9cf7b-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9cf7b-123">API interessate</span><span class="sxs-lookup"><span data-stu-id="9cf7b-123">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate`
- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync`
- `Overload:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod`

-->
