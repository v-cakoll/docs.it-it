---
ms.openlocfilehash: c8f44ae1a500ed240dbff7d9a2c1479af368b7f1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72393907"
---
### <a name="identity-default-bootstrap-version-of-ui-changed"></a><span data-ttu-id="c57dd-101">Identità: è stata modificata la versione Bootstrap predefinita dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="c57dd-101">Identity: Default Bootstrap version of UI changed</span></span>

<span data-ttu-id="c57dd-102">A partire da ASP.NET Core 3.0, l'interfaccia utente di identità utilizza per impostazione predefinita la versione 4 di Bootstrap.</span><span class="sxs-lookup"><span data-stu-id="c57dd-102">Starting in ASP.NET Core 3.0, Identity UI defaults to using version 4 of Bootstrap.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c57dd-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="c57dd-103">Version introduced</span></span>

<span data-ttu-id="c57dd-104">3.0</span><span class="sxs-lookup"><span data-stu-id="c57dd-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="c57dd-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="c57dd-105">Old behavior</span></span>

<span data-ttu-id="c57dd-106">La `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` chiamata al metodo è stata la stessa`services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);`</span><span class="sxs-lookup"><span data-stu-id="c57dd-106">The `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` method call was the same as `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);`</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="c57dd-107">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="c57dd-107">New behavior</span></span>

<span data-ttu-id="c57dd-108">La `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` chiamata al metodo è la stessa`services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap4);`</span><span class="sxs-lookup"><span data-stu-id="c57dd-108">The `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` method call is the same as `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap4);`</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c57dd-109">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="c57dd-109">Reason for change</span></span>

<span data-ttu-id="c57dd-110">Bootstrap 4 è stato rilasciato durante ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="c57dd-110">Bootstrap 4 was released during ASP.NET Core 3.0 timeframe.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c57dd-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="c57dd-111">Recommended action</span></span>

<span data-ttu-id="c57dd-112">Si è interessati da questa modifica se si utilizza l'interfaccia utente di identità predefinita e l'utente l'ha aggiunta, come illustrato nell'esempio seguente:You're impacted by this change if you use the default Identity UI and have added in `Startup.ConfigureServices` as shown in the following example:</span><span class="sxs-lookup"><span data-stu-id="c57dd-112">You're impacted by this change if you use the default Identity UI and have added it in `Startup.ConfigureServices` as shown in the following example:</span></span>

```csharp
services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();
```

<span data-ttu-id="c57dd-113">eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c57dd-113">Take one of the following actions:</span></span>

- <span data-ttu-id="c57dd-114">Eseguire la migrazione dell'app per l'utilizzo di Bootstrap 4 usando la [relativa guida alla migrazione.](https://getbootstrap.com/docs/4.0/migration)</span><span class="sxs-lookup"><span data-stu-id="c57dd-114">Migrate your app to use Bootstrap 4 using their [migration guide](https://getbootstrap.com/docs/4.0/migration).</span></span>
- <span data-ttu-id="c57dd-115">Aggiornamento `Startup.ConfigureServices` per imporre l'utilizzo di Bootstrap 3.</span><span class="sxs-lookup"><span data-stu-id="c57dd-115">Update `Startup.ConfigureServices` to enforce usage of Bootstrap 3.</span></span> <span data-ttu-id="c57dd-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c57dd-116">For example:</span></span>

    ```csharp
    services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);
    ```

#### <a name="category"></a><span data-ttu-id="c57dd-117">Category</span><span class="sxs-lookup"><span data-stu-id="c57dd-117">Category</span></span>

<span data-ttu-id="c57dd-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c57dd-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c57dd-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="c57dd-119">Affected APIs</span></span>

<span data-ttu-id="c57dd-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="c57dd-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
