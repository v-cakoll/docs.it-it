---
ms.openlocfilehash: be9a79f6ead3e72d7ffaade758704f0c1e2477f0
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394142"
---
### <a name="hosting-generic-host-restricts-startup-constructor-injection"></a><span data-ttu-id="2828b-101">Hosting: l'host generico limita l'inserimento del costruttore di avvio</span><span class="sxs-lookup"><span data-stu-id="2828b-101">Hosting: Generic host restricts Startup constructor injection</span></span>

<span data-ttu-id="2828b-102">Gli unici tipi supportati dall'host generico per l'inserimento di un costruttore di classe `Startup` sono `IHostEnvironment`, `IWebHostEnvironment` e `IConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="2828b-102">The only types the generic host supports for `Startup` class constructor injection are `IHostEnvironment`, `IWebHostEnvironment`, and `IConfiguration`.</span></span> <span data-ttu-id="2828b-103">Le app che usano `WebHost` non sono interessate.</span><span class="sxs-lookup"><span data-stu-id="2828b-103">Apps using `WebHost` are unaffected.</span></span>

#### <a name="change-description"></a><span data-ttu-id="2828b-104">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="2828b-104">Change description</span></span>

<span data-ttu-id="2828b-105">Prima di ASP.NET Core 3,0, era possibile usare l'inserimento del costruttore per i tipi arbitrari nel costruttore della classe `Startup`.</span><span class="sxs-lookup"><span data-stu-id="2828b-105">Prior to ASP.NET Core 3.0, constructor injection could be used for arbitrary types in the `Startup` class's constructor.</span></span> <span data-ttu-id="2828b-106">In ASP.NET Core 3,0, lo stack Web è stato riplatformato nella libreria host generica.</span><span class="sxs-lookup"><span data-stu-id="2828b-106">In ASP.NET Core 3.0, the web stack was replatformed onto the generic host library.</span></span> <span data-ttu-id="2828b-107">È possibile visualizzare le modifiche apportate al file *Program.cs* dei modelli:</span><span class="sxs-lookup"><span data-stu-id="2828b-107">You can see the change in the *Program.cs* file of the templates:</span></span>

<span data-ttu-id="2828b-108">**ASP.NET Core 2. x:**</span><span class="sxs-lookup"><span data-stu-id="2828b-108">**ASP.NET Core 2.x:**</span></span>

<https://github.com/aspnet/AspNetCore/blob/5cb615fcbe8559e49042e93394008077e30454c0/src/Templating/src/Microsoft.DotNet.Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L20-L22>

<span data-ttu-id="2828b-109">**ASP.NET Core 3,0:**</span><span class="sxs-lookup"><span data-stu-id="2828b-109">**ASP.NET Core 3.0:**</span></span>

<https://github.com/aspnet/AspNetCore/blob/b1ca2c1155da3920f0df5108b9fedbe82efaa11c/src/ProjectTemplates/Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L19-L24>

<span data-ttu-id="2828b-110">`Host` usa un contenitore DI inserimento delle dipendenze per compilare l'app.</span><span class="sxs-lookup"><span data-stu-id="2828b-110">`Host` uses one dependency injection (DI) container to build the app.</span></span> <span data-ttu-id="2828b-111">`WebHost` usa due contenitori: uno per l'host e uno per l'app.</span><span class="sxs-lookup"><span data-stu-id="2828b-111">`WebHost` uses two containers: one for the host and one for the app.</span></span> <span data-ttu-id="2828b-112">Di conseguenza, il costruttore `Startup` non supporta più l'inserimento di un servizio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2828b-112">As a result, the `Startup` constructor no longer supports custom service injection.</span></span> <span data-ttu-id="2828b-113">È possibile inserire solo `IHostEnvironment`, `IWebHostEnvironment` e `IConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="2828b-113">Only `IHostEnvironment`, `IWebHostEnvironment`, and `IConfiguration` can be injected.</span></span> <span data-ttu-id="2828b-114">Questa modifica impedisce problemi DI inserimento, ad esempio la creazione di duplicati di un servizio singleton.</span><span class="sxs-lookup"><span data-stu-id="2828b-114">This change prevents DI issues such as the duplicate creation of a singleton service.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2828b-115">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="2828b-115">Version introduced</span></span>

<span data-ttu-id="2828b-116">3.0</span><span class="sxs-lookup"><span data-stu-id="2828b-116">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2828b-117">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="2828b-117">Reason for change</span></span>

<span data-ttu-id="2828b-118">Questa modifica è una conseguenza della ripiattaforma dello stack Web nella libreria host generica.</span><span class="sxs-lookup"><span data-stu-id="2828b-118">This change is a consequence of replatforming the web stack onto the generic host library.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2828b-119">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="2828b-119">Recommended action</span></span>

<span data-ttu-id="2828b-120">Inserire i servizi nella firma del metodo `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="2828b-120">Inject services into the `Startup.Configure` method signature.</span></span> <span data-ttu-id="2828b-121">Esempio:</span><span class="sxs-lookup"><span data-stu-id="2828b-121">For example:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IOptions<MyOptions> options)
```

#### <a name="category"></a><span data-ttu-id="2828b-122">Category</span><span class="sxs-lookup"><span data-stu-id="2828b-122">Category</span></span>

<span data-ttu-id="2828b-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2828b-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2828b-124">API interessate</span><span class="sxs-lookup"><span data-stu-id="2828b-124">Affected APIs</span></span>

<span data-ttu-id="2828b-125">Nessuno</span><span class="sxs-lookup"><span data-stu-id="2828b-125">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
