---
ms.openlocfilehash: d1ddba72ce25c5e01025d916d52f785b5a1a9e71
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901821"
---
### <a name="hosting-generic-host-restricts-startup-constructor-injection"></a><span data-ttu-id="d7182-101">Hosting: l'host generico limita l'inserimento del costruttore di avvioHosting: Generic host restricts Startup constructor injection</span><span class="sxs-lookup"><span data-stu-id="d7182-101">Hosting: Generic host restricts Startup constructor injection</span></span>

<span data-ttu-id="d7182-102">Gli unici tipi supportati dall'host generico `Startup` per l'inserimento del costruttore di classe `IHostEnvironment`sono , `IWebHostEnvironment`, e `IConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="d7182-102">The only types the generic host supports for `Startup` class constructor injection are `IHostEnvironment`, `IWebHostEnvironment`, and `IConfiguration`.</span></span> <span data-ttu-id="d7182-103">Le `WebHost` app in uso non sono interessate.</span><span class="sxs-lookup"><span data-stu-id="d7182-103">Apps using `WebHost` are unaffected.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d7182-104">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="d7182-104">Change description</span></span>

<span data-ttu-id="d7182-105">Prima di ASP.NET Core 3.0, l'inserimento del `Startup` costruttore poteva essere utilizzato per tipi arbitrari nel costruttore della classe.</span><span class="sxs-lookup"><span data-stu-id="d7182-105">Prior to ASP.NET Core 3.0, constructor injection could be used for arbitrary types in the `Startup` class's constructor.</span></span> <span data-ttu-id="d7182-106">In ASP.NET Core 3.0, lo stack Web è stato nuovamente reindirizzato alla libreria host generica.</span><span class="sxs-lookup"><span data-stu-id="d7182-106">In ASP.NET Core 3.0, the web stack was replatformed onto the generic host library.</span></span> <span data-ttu-id="d7182-107">È possibile visualizzare la modifica nel file *Program.cs* dei modelli:</span><span class="sxs-lookup"><span data-stu-id="d7182-107">You can see the change in the *Program.cs* file of the templates:</span></span>

<span data-ttu-id="d7182-108">**ASP.NET Core 2.x:**</span><span class="sxs-lookup"><span data-stu-id="d7182-108">**ASP.NET Core 2.x:**</span></span>

<https://github.com/dotnet/aspnetcore/blob/5cb615fcbe8559e49042e93394008077e30454c0/src/Templating/src/Microsoft.DotNet.Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L20-L22>

<span data-ttu-id="d7182-109">**ASP.NET Core 3.0:**</span><span class="sxs-lookup"><span data-stu-id="d7182-109">**ASP.NET Core 3.0:**</span></span>

<https://github.com/dotnet/aspnetcore/blob/b1ca2c1155da3920f0df5108b9fedbe82efaa11c/src/ProjectTemplates/Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L19-L24>

<span data-ttu-id="d7182-110">`Host`utilizza un contenitore di inserimento delle dipendenze (DI) per compilare l'app.</span><span class="sxs-lookup"><span data-stu-id="d7182-110">`Host` uses one dependency injection (DI) container to build the app.</span></span> <span data-ttu-id="d7182-111">`WebHost`utilizza due contenitori: uno per l'host e uno per l'app.</span><span class="sxs-lookup"><span data-stu-id="d7182-111">`WebHost` uses two containers: one for the host and one for the app.</span></span> <span data-ttu-id="d7182-112">Di conseguenza, `Startup` il costruttore non supporta più l'inserimento di servizi personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d7182-112">As a result, the `Startup` constructor no longer supports custom service injection.</span></span> <span data-ttu-id="d7182-113">Solo `IHostEnvironment` `IWebHostEnvironment`, `IConfiguration` , e può essere iniettato.</span><span class="sxs-lookup"><span data-stu-id="d7182-113">Only `IHostEnvironment`, `IWebHostEnvironment`, and `IConfiguration` can be injected.</span></span> <span data-ttu-id="d7182-114">Questa modifica impedisce problemi DI, ad esempio la creazione duplicata di un servizio singleton.</span><span class="sxs-lookup"><span data-stu-id="d7182-114">This change prevents DI issues such as the duplicate creation of a singleton service.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d7182-115">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="d7182-115">Version introduced</span></span>

<span data-ttu-id="d7182-116">3.0</span><span class="sxs-lookup"><span data-stu-id="d7182-116">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d7182-117">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="d7182-117">Reason for change</span></span>

<span data-ttu-id="d7182-118">Questa modifica è una conseguenza del replatforming dello stack Web nella libreria host generica.</span><span class="sxs-lookup"><span data-stu-id="d7182-118">This change is a consequence of replatforming the web stack onto the generic host library.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d7182-119">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="d7182-119">Recommended action</span></span>

<span data-ttu-id="d7182-120">Inserire i `Startup.Configure` servizi nella firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="d7182-120">Inject services into the `Startup.Configure` method signature.</span></span> <span data-ttu-id="d7182-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d7182-121">For example:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IOptions<MyOptions> options)
```

#### <a name="category"></a><span data-ttu-id="d7182-122">Category</span><span class="sxs-lookup"><span data-stu-id="d7182-122">Category</span></span>

<span data-ttu-id="d7182-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d7182-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d7182-124">API interessate</span><span class="sxs-lookup"><span data-stu-id="d7182-124">Affected APIs</span></span>

<span data-ttu-id="d7182-125">nessuno</span><span class="sxs-lookup"><span data-stu-id="d7182-125">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
