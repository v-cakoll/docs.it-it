---
ms.openlocfilehash: 23ba6064a283b47312a66f3636c2834a7d58106e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620188"
---
### <a name="adonet-now-attempts-to-automatically-reconnect-broken-sql-connections"></a><span data-ttu-id="b49ad-101">ADO.NET ora tenta di riconnettere automaticamente le connessioni SQL interrotte</span><span class="sxs-lookup"><span data-stu-id="b49ad-101">ADO.NET now attempts to automatically reconnect broken SQL connections</span></span>

#### <a name="details"></a><span data-ttu-id="b49ad-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b49ad-102">Details</span></span>

<span data-ttu-id="b49ad-103">A partire da .NET Framework 4.5.1, .NET Framework tenterà di riconnettere automaticamente le connessioni SQL interrotte.</span><span class="sxs-lookup"><span data-stu-id="b49ad-103">Beginning in the .NET Framework 4.5.1, the .NET Framework will attempt to automatically reconnect broken SQL connections.</span></span> <span data-ttu-id="b49ad-104">Anche se ciò in genere renderà più affidabili le app, in alcuni casi limite un'app deve sapere che la connessione è stata interrotta in modo da poter adottare determinate azioni alla riconnessione.</span><span class="sxs-lookup"><span data-stu-id="b49ad-104">Although this will typically make apps more reliable, there are edge cases in which an app needs to know that the connection was lost so that it can take some action upon reconnection.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b49ad-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="b49ad-105">Suggestion</span></span>

<span data-ttu-id="b49ad-106">Se questa funzionalità non è auspicabile per motivi di compatibilità, è possibile disabilitarla impostando la proprietà <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName> di una stringa di connessione (o <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName>) su 0.</span><span class="sxs-lookup"><span data-stu-id="b49ad-106">If this feature is undesirable due to compatibility concerns, it can be disabled by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName> property of a connection string (or <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName>) to 0.</span></span>

| <span data-ttu-id="b49ad-107">Nome</span><span class="sxs-lookup"><span data-stu-id="b49ad-107">Name</span></span>    | <span data-ttu-id="b49ad-108">Valore</span><span class="sxs-lookup"><span data-stu-id="b49ad-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b49ad-109">Scope</span><span class="sxs-lookup"><span data-stu-id="b49ad-109">Scope</span></span>   |<span data-ttu-id="b49ad-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b49ad-110">Edge</span></span>|
|<span data-ttu-id="b49ad-111">Version</span><span class="sxs-lookup"><span data-stu-id="b49ad-111">Version</span></span>|<span data-ttu-id="b49ad-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="b49ad-112">4.5.1</span></span>|
|<span data-ttu-id="b49ad-113">Type</span><span class="sxs-lookup"><span data-stu-id="b49ad-113">Type</span></span>|<span data-ttu-id="b49ad-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="b49ad-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b49ad-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="b49ad-115">Affected APIs</span></span>

-<xref:System.Data.IDbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Configuration.ConnectionStringSettings.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnectionStringBuilder.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor(System.String)></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor(System.Boolean)></li></ul>|
