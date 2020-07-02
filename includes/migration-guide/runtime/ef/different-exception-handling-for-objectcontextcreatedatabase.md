---
ms.openlocfilehash: 687118157020ede200f97a0125c4740a06bf4b5e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620304"
---
### <a name="different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a><span data-ttu-id="acf80-101">Diversa gestione delle eccezioni per i metodi ObjectContext.CreateDatabase e DbProviderServices.CreateDatabase</span><span class="sxs-lookup"><span data-stu-id="acf80-101">Different exception handling for ObjectContext.CreateDatabase and DbProviderServices.CreateDatabase methods</span></span>

#### <a name="details"></a><span data-ttu-id="acf80-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="acf80-102">Details</span></span>

<span data-ttu-id="acf80-103">A partire da .NET Framework 4.5, se la creazione del database non riesce, i metodi <code>CreateDatabase</code> tentano di eliminare il database vuoto.</span><span class="sxs-lookup"><span data-stu-id="acf80-103">Beginning in .NET Framework 4.5, if database creation fails, <code>CreateDatabase</code> methods will attempt to drop the empty database.</span></span> <span data-ttu-id="acf80-104">Se tale operazione ha esito positivo, verrà propagata l'eccezione <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> originale, al posto dell'eccezione <xref:System.InvalidOperationException?displayProperty=fullName> che viene sempre generata in .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="acf80-104">If that operation succeeds, the original <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> will be propagated (instead of the <xref:System.InvalidOperationException?displayProperty=fullName> that was always thrown in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="acf80-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="acf80-105">Suggestion</span></span>

<span data-ttu-id="acf80-106">Quando si rileva un oggetto <xref:System.InvalidOperationException?displayProperty=fullName> durante l'esecuzione di <xref:System.Data.Objects.ObjectContext.CreateDatabase> o <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)>, ora deve essere rilevato anche SQLExceptions.</span><span class="sxs-lookup"><span data-stu-id="acf80-106">When catching an <xref:System.InvalidOperationException?displayProperty=fullName> while executing <xref:System.Data.Objects.ObjectContext.CreateDatabase> or <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)>, SQLExceptions should now also be caught.</span></span>

| <span data-ttu-id="acf80-107">Nome</span><span class="sxs-lookup"><span data-stu-id="acf80-107">Name</span></span>    | <span data-ttu-id="acf80-108">Valore</span><span class="sxs-lookup"><span data-stu-id="acf80-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="acf80-109">Scope</span><span class="sxs-lookup"><span data-stu-id="acf80-109">Scope</span></span>   |<span data-ttu-id="acf80-110">Minorenne</span><span class="sxs-lookup"><span data-stu-id="acf80-110">Minor</span></span>|
|<span data-ttu-id="acf80-111">Version</span><span class="sxs-lookup"><span data-stu-id="acf80-111">Version</span></span>|<span data-ttu-id="acf80-112">4.5</span><span class="sxs-lookup"><span data-stu-id="acf80-112">4.5</span></span>|
|<span data-ttu-id="acf80-113">Type</span><span class="sxs-lookup"><span data-stu-id="acf80-113">Type</span></span>|<span data-ttu-id="acf80-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="acf80-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="acf80-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="acf80-115">Affected APIs</span></span>

-<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType></li></ul>|
