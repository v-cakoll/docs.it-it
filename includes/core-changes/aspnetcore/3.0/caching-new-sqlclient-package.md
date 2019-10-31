---
ms.openlocfilehash: 771238c53dc97f4cf4068968f3c68500ba9f87da
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198467"
---
### <a name="caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package"></a><span data-ttu-id="678e4-101">Caching: Microsoft. Extensions. Caching. SqlServer usa il nuovo pacchetto SqlClient</span><span class="sxs-lookup"><span data-stu-id="678e4-101">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>

<span data-ttu-id="678e4-102">Il pacchetto `Microsoft.Extensions.Caching.SqlServer` utilizzerà il nuovo pacchetto `Microsoft.Data.SqlClient` anziché il pacchetto `System.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="678e4-102">The `Microsoft.Extensions.Caching.SqlServer` package will use the new `Microsoft.Data.SqlClient` package instead of `System.Data.SqlClient` package.</span></span> <span data-ttu-id="678e4-103">Questa modifica può provocare lievi modifiche di comportamento.</span><span class="sxs-lookup"><span data-stu-id="678e4-103">This change could cause slight behavioral breaking changes.</span></span> <span data-ttu-id="678e4-104">Per ulteriori informazioni, vedere [Introducing The New Microsoft. Data. SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/).</span><span class="sxs-lookup"><span data-stu-id="678e4-104">For more information, see [Introducing the new Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="678e4-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="678e4-105">Version introduced</span></span>

<span data-ttu-id="678e4-106">3.0</span><span class="sxs-lookup"><span data-stu-id="678e4-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="678e4-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="678e4-107">Old behavior</span></span>

<span data-ttu-id="678e4-108">Il pacchetto `Microsoft.Extensions.Caching.SqlServer` ha usato il pacchetto `System.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="678e4-108">The `Microsoft.Extensions.Caching.SqlServer` package used the `System.Data.SqlClient` package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="678e4-109">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="678e4-109">New behavior</span></span>

<span data-ttu-id="678e4-110">`Microsoft.Extensions.Caching.SqlServer` USA ora il pacchetto `Microsoft.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="678e4-110">`Microsoft.Extensions.Caching.SqlServer` is now using the `Microsoft.Data.SqlClient` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="678e4-111">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="678e4-111">Reason for change</span></span>

<span data-ttu-id="678e4-112">`Microsoft.Data.SqlClient` è un nuovo pacchetto compilato da `System.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="678e4-112">`Microsoft.Data.SqlClient` is a new package that is built off of `System.Data.SqlClient`.</span></span> <span data-ttu-id="678e4-113">È qui che verranno eseguite tutte le nuove funzionalità da ora in poi.</span><span class="sxs-lookup"><span data-stu-id="678e4-113">It's where all new feature work will be done from now on.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="678e4-114">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="678e4-114">Recommended action</span></span>

<span data-ttu-id="678e4-115">I clienti non devono preoccuparsi di questa modifica sostanziale a meno che non utilizzino i tipi restituiti dal pacchetto `Microsoft.Extensions.Caching.SqlServer` e li eseguono il cast ai tipi `System.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="678e4-115">Customers shouldn't need to worry about this breaking change unless they were using types returned by the `Microsoft.Extensions.Caching.SqlServer` package and casting them to `System.Data.SqlClient` types.</span></span> <span data-ttu-id="678e4-116">Se, ad esempio, un utente esegue il cast di un `DbConnection` al [tipo SqlConnection precedente](xref:System.Data.SqlClient.SqlConnection), sarà necessario modificare il cast al nuovo tipo `Microsoft.Data.SqlClient.SqlConnection`.</span><span class="sxs-lookup"><span data-stu-id="678e4-116">For example, if someone was casting a `DbConnection` to the [old SqlConnection type](xref:System.Data.SqlClient.SqlConnection), they would need to change the cast to the new `Microsoft.Data.SqlClient.SqlConnection` type.</span></span>

#### <a name="category"></a><span data-ttu-id="678e4-117">Category</span><span class="sxs-lookup"><span data-stu-id="678e4-117">Category</span></span>

<span data-ttu-id="678e4-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="678e4-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="678e4-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="678e4-119">Affected APIs</span></span>

<span data-ttu-id="678e4-120">Nessuno</span><span class="sxs-lookup"><span data-stu-id="678e4-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
