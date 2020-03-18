---
ms.openlocfilehash: 771238c53dc97f4cf4068968f3c68500ba9f87da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73198467"
---
### <a name="caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package"></a><span data-ttu-id="43924-101">Memorizzazione nella cache: Microsoft.Extensions.Caching.SqlServer utilizza il nuovo pacchetto SqlClient</span><span class="sxs-lookup"><span data-stu-id="43924-101">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>

<span data-ttu-id="43924-102">Il `Microsoft.Extensions.Caching.SqlServer` pacchetto utilizzerà `Microsoft.Data.SqlClient` il `System.Data.SqlClient` nuovo pacchetto anziché il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="43924-102">The `Microsoft.Extensions.Caching.SqlServer` package will use the new `Microsoft.Data.SqlClient` package instead of `System.Data.SqlClient` package.</span></span> <span data-ttu-id="43924-103">Questa modifica potrebbe causare lievi modifiche di interruzione comportamentale.</span><span class="sxs-lookup"><span data-stu-id="43924-103">This change could cause slight behavioral breaking changes.</span></span> <span data-ttu-id="43924-104">Per ulteriori informazioni, vedere [Introduzione al nuovo Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/).</span><span class="sxs-lookup"><span data-stu-id="43924-104">For more information, see [Introducing the new Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="43924-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="43924-105">Version introduced</span></span>

<span data-ttu-id="43924-106">3.0</span><span class="sxs-lookup"><span data-stu-id="43924-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="43924-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="43924-107">Old behavior</span></span>

<span data-ttu-id="43924-108">Il `Microsoft.Extensions.Caching.SqlServer` pacchetto `System.Data.SqlClient` ha usato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="43924-108">The `Microsoft.Extensions.Caching.SqlServer` package used the `System.Data.SqlClient` package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="43924-109">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="43924-109">New behavior</span></span>

<span data-ttu-id="43924-110">`Microsoft.Extensions.Caching.SqlServer`sta utilizzando `Microsoft.Data.SqlClient` il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="43924-110">`Microsoft.Extensions.Caching.SqlServer` is now using the `Microsoft.Data.SqlClient` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="43924-111">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="43924-111">Reason for change</span></span>

<span data-ttu-id="43924-112">`Microsoft.Data.SqlClient`è un nuovo pacchetto che `System.Data.SqlClient`è costruito fuori di .</span><span class="sxs-lookup"><span data-stu-id="43924-112">`Microsoft.Data.SqlClient` is a new package that is built off of `System.Data.SqlClient`.</span></span> <span data-ttu-id="43924-113">È dove tutto il lavoro di nuova funzionalità sarà fatto d'ora in tanto.</span><span class="sxs-lookup"><span data-stu-id="43924-113">It's where all new feature work will be done from now on.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="43924-114">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="43924-114">Recommended action</span></span>

<span data-ttu-id="43924-115">I clienti non dovrebbero preoccuparsi di questa modifica di rilievo `Microsoft.Extensions.Caching.SqlServer` a meno che `System.Data.SqlClient` non utilizzassero tipi restituiti dal pacchetto e che li esetrae ai tipi.</span><span class="sxs-lookup"><span data-stu-id="43924-115">Customers shouldn't need to worry about this breaking change unless they were using types returned by the `Microsoft.Extensions.Caching.SqlServer` package and casting them to `System.Data.SqlClient` types.</span></span> <span data-ttu-id="43924-116">Ad esempio, se un `DbConnection` utente esegue il cast di un al tipo `Microsoft.Data.SqlClient.SqlConnection` [SqlConnection precedente,](xref:System.Data.SqlClient.SqlConnection)avrebbe dovuto modificare il cast nel nuovo tipo.</span><span class="sxs-lookup"><span data-stu-id="43924-116">For example, if someone was casting a `DbConnection` to the [old SqlConnection type](xref:System.Data.SqlClient.SqlConnection), they would need to change the cast to the new `Microsoft.Data.SqlClient.SqlConnection` type.</span></span>

#### <a name="category"></a><span data-ttu-id="43924-117">Category</span><span class="sxs-lookup"><span data-stu-id="43924-117">Category</span></span>

<span data-ttu-id="43924-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="43924-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="43924-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="43924-119">Affected APIs</span></span>

<span data-ttu-id="43924-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="43924-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
