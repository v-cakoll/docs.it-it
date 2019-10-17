---
ms.openlocfilehash: c8f44ae1a500ed240dbff7d9a2c1479af368b7f1
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393907"
---
### <a name="identity-default-bootstrap-version-of-ui-changed"></a><span data-ttu-id="160d3-101">Identità: versione bootstrap predefinita dell'interfaccia utente modificata</span><span class="sxs-lookup"><span data-stu-id="160d3-101">Identity: Default Bootstrap version of UI changed</span></span>

<span data-ttu-id="160d3-102">A partire da ASP.NET Core 3,0, per impostazione predefinita l'interfaccia utente Identity usa la versione 4 di bootstrap.</span><span class="sxs-lookup"><span data-stu-id="160d3-102">Starting in ASP.NET Core 3.0, Identity UI defaults to using version 4 of Bootstrap.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="160d3-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="160d3-103">Version introduced</span></span>

<span data-ttu-id="160d3-104">3.0</span><span class="sxs-lookup"><span data-stu-id="160d3-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="160d3-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="160d3-105">Old behavior</span></span>

<span data-ttu-id="160d3-106">La chiamata al metodo `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` corrisponde a `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);`</span><span class="sxs-lookup"><span data-stu-id="160d3-106">The `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` method call was the same as `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);`</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="160d3-107">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="160d3-107">New behavior</span></span>

<span data-ttu-id="160d3-108">La chiamata al metodo `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` corrisponde a `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap4);`</span><span class="sxs-lookup"><span data-stu-id="160d3-108">The `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` method call is the same as `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap4);`</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="160d3-109">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="160d3-109">Reason for change</span></span>

<span data-ttu-id="160d3-110">Il bootstrap 4 è stato rilasciato durante ASP.NET Core intervallo di 3,0.</span><span class="sxs-lookup"><span data-stu-id="160d3-110">Bootstrap 4 was released during ASP.NET Core 3.0 timeframe.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="160d3-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="160d3-111">Recommended action</span></span>

<span data-ttu-id="160d3-112">Questo cambiamento è influenzato da questa modifica se si usa l'interfaccia utente di identità predefinita e la si aggiunge in `Startup.ConfigureServices`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="160d3-112">You're impacted by this change if you use the default Identity UI and have added it in `Startup.ConfigureServices` as shown in the following example:</span></span>

```csharp
services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();
```

<span data-ttu-id="160d3-113">Eseguire una delle azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="160d3-113">Take one of the following actions:</span></span>

- <span data-ttu-id="160d3-114">Eseguire la migrazione dell'applicazione per utilizzare bootstrap 4 utilizzando la relativa [Guida alla migrazione](https://getbootstrap.com/docs/4.0/migration).</span><span class="sxs-lookup"><span data-stu-id="160d3-114">Migrate your app to use Bootstrap 4 using their [migration guide](https://getbootstrap.com/docs/4.0/migration).</span></span>
- <span data-ttu-id="160d3-115">Aggiornare `Startup.ConfigureServices` per applicare l'utilizzo di bootstrap 3.</span><span class="sxs-lookup"><span data-stu-id="160d3-115">Update `Startup.ConfigureServices` to enforce usage of Bootstrap 3.</span></span> <span data-ttu-id="160d3-116">Esempio:</span><span class="sxs-lookup"><span data-stu-id="160d3-116">For example:</span></span>

    ```csharp
    services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);
    ```

#### <a name="category"></a><span data-ttu-id="160d3-117">Category</span><span class="sxs-lookup"><span data-stu-id="160d3-117">Category</span></span>

<span data-ttu-id="160d3-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="160d3-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="160d3-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="160d3-119">Affected APIs</span></span>

<span data-ttu-id="160d3-120">Nessuno</span><span class="sxs-lookup"><span data-stu-id="160d3-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
