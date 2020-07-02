---
ms.openlocfilehash: 241184d61d718fedfea396260e739d2dbc05c305
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620284"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a><span data-ttu-id="8de54-101">SqlConnection non può più connettersi a SQL Server 1997 o a database che usano l'adapter VIA</span><span class="sxs-lookup"><span data-stu-id="8de54-101">SqlConnection can no longer connect to SQL Server 1997 or databases using the VIA adapter</span></span>

#### <a name="details"></a><span data-ttu-id="8de54-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8de54-102">Details</span></span>

<span data-ttu-id="8de54-103">Le connessioni ai database SQL Server tramite il [protocollo Virtual Interface Adapter (via)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="8de54-103">Connections to SQL Server databases using the [Virtual Interface Adapter (VIA) protocol](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) are no longer supported.</span></span> <span data-ttu-id="8de54-104">Il protocollo usato per connettersi a un database di SQL Server è visibile nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="8de54-104">The protocol used to connect to a SQL Server database is visible in the connection string.</span></span> <span data-ttu-id="8de54-105">Una connessione VIA conterrà via:&lt;nomeserver&gt;.</span><span class="sxs-lookup"><span data-stu-id="8de54-105">A VIA connection will contain via:&lt;servername&gt;.</span></span> <span data-ttu-id="8de54-106">Se l'app si connette a SQL tramite un protocollo diverso da VIA (TCP: o NP: ad esempio), non verrà rilevata alcuna modifica di rilievo.</span><span class="sxs-lookup"><span data-stu-id="8de54-106">If this app is connecting to SQL via a protocol other than VIA (tcp: or np: for example), then no breaking change will be encountered.</span></span> <span data-ttu-id="8de54-107">Inoltre, le connessioni a SQL Server 7 (1997) non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="8de54-107">Also, connections to SQL Server 7 (1997) are no longer supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8de54-108">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="8de54-108">Suggestion</span></span>

<span data-ttu-id="8de54-109">Il protocollo VIA è deprecato, pertanto deve essere usato un protocollo alternativo per connettersi ai database SQL.</span><span class="sxs-lookup"><span data-stu-id="8de54-109">The VIA protocol is deprecated, so an alternative protocol should be used to connect to SQL databases.</span></span> <span data-ttu-id="8de54-110">Il protocollo più comune usato è TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="8de54-110">The most common protocol used is TCP/IP.</span></span> <span data-ttu-id="8de54-111">Per altre informazioni sulle connessioni tramite TCP/IP, vedere [Abilitare il protocollo TCP/IP per un'istanza di database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="8de54-111">For more information about connecting through TCP/IP, see [Enable the TCP/IP protocol for a database instance](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)).</span></span> <span data-ttu-id="8de54-112">Se il database è accessibile solo all'interno di una rete Intranet, il protocollo pipe condiviso può offrire prestazioni migliori se la rete è lenta.</span><span class="sxs-lookup"><span data-stu-id="8de54-112">If the database is only accessed from within an intranet, the shared pipes protocol may provide better performance if the network is slow.</span></span>

| <span data-ttu-id="8de54-113">Nome</span><span class="sxs-lookup"><span data-stu-id="8de54-113">Name</span></span>    | <span data-ttu-id="8de54-114">Valore</span><span class="sxs-lookup"><span data-stu-id="8de54-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8de54-115">Scope</span><span class="sxs-lookup"><span data-stu-id="8de54-115">Scope</span></span>   |<span data-ttu-id="8de54-116">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8de54-116">Edge</span></span>|
|<span data-ttu-id="8de54-117">Version</span><span class="sxs-lookup"><span data-stu-id="8de54-117">Version</span></span>|<span data-ttu-id="8de54-118">4.5</span><span class="sxs-lookup"><span data-stu-id="8de54-118">4.5</span></span>|
|<span data-ttu-id="8de54-119">Type</span><span class="sxs-lookup"><span data-stu-id="8de54-119">Type</span></span>|<span data-ttu-id="8de54-120">Runtime</span><span class="sxs-lookup"><span data-stu-id="8de54-120">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8de54-121">API interessate</span><span class="sxs-lookup"><span data-stu-id="8de54-121">Affected APIs</span></span>

-<xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)></li></ul>|
