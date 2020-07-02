---
ms.openlocfilehash: 87cb2570d3d47a2acb85b5557141c0fef885516a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621800"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a><span data-ttu-id="ae8db-101">Il tentativo di connessione TCP/IP a un database di SQL Server corrispondente a `localhost` non riesce</span><span class="sxs-lookup"><span data-stu-id="ae8db-101">Attempting a TCP/IP connection to a SQL Server database that resolves to `localhost` fails</span></span>

#### <a name="details"></a><span data-ttu-id="ae8db-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ae8db-102">Details</span></span>

<span data-ttu-id="ae8db-103">In .NET Framework 4.6 e 4.6.1, il tentativo di connessione TCP/IP a un database di SQL Server corrispondente a <code>localhost</code> ha esito negativo con l'errore &quot;Si è verificato un errore di rete o specifico dell'istanza mentre si cercava di stabilire una connessione con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ae8db-103">In the .NET Framework 4.6 and 4.6.1, attempting a TCP/IP connection to a SQL Server database that resolves to <code>localhost</code> fails with the error, &quot;A network-related or instance-specific error occurred while establishing a connection to SQL Server.</span></span> <span data-ttu-id="ae8db-104">Il server non è stato trovato o non è accessibile.</span><span class="sxs-lookup"><span data-stu-id="ae8db-104">The server was not found or was not accessible.</span></span> <span data-ttu-id="ae8db-105">Verificare che il nome dell'istanza sia corretto e che il server sia configurato in modo da consentire connessioni remote.</span><span class="sxs-lookup"><span data-stu-id="ae8db-105">Verify that the instance name is correct and that SQL Server is configured to allow remote connections.</span></span> <span data-ttu-id="ae8db-106">(provider: interfacce di rete SQL, errore: 26 - Errore nell'individuazione del server/dell'istanza specificata)&quot;</span><span class="sxs-lookup"><span data-stu-id="ae8db-106">(provider: SQL Network Interfaces, error: 26 - Error Locating Server/Instance Specified)&quot;</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ae8db-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="ae8db-107">Suggestion</span></span>

<span data-ttu-id="ae8db-108">Questo problema è stato risolto ed è stato ripristinato il comportamento precedente in .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="ae8db-108">This issue has been addressed and the previous behavior restored in the .NET Framework 4.6.2.</span></span> <span data-ttu-id="ae8db-109">Per connettersi a un database di SQL Server corrispondente a <code>localhost</code>, eseguire l'aggiornamento a .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="ae8db-109">To connect to a SQL Server database that resolves to <code>localhost</code>, upgrade to the .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="ae8db-110">Nome</span><span class="sxs-lookup"><span data-stu-id="ae8db-110">Name</span></span>    | <span data-ttu-id="ae8db-111">Valore</span><span class="sxs-lookup"><span data-stu-id="ae8db-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ae8db-112">Scope</span><span class="sxs-lookup"><span data-stu-id="ae8db-112">Scope</span></span>   |<span data-ttu-id="ae8db-113">Minorenne</span><span class="sxs-lookup"><span data-stu-id="ae8db-113">Minor</span></span>|
|<span data-ttu-id="ae8db-114">Version</span><span class="sxs-lookup"><span data-stu-id="ae8db-114">Version</span></span>|<span data-ttu-id="ae8db-115">4.6</span><span class="sxs-lookup"><span data-stu-id="ae8db-115">4.6</span></span>|
|<span data-ttu-id="ae8db-116">Type</span><span class="sxs-lookup"><span data-stu-id="ae8db-116">Type</span></span>|<span data-ttu-id="ae8db-117">Runtime</span><span class="sxs-lookup"><span data-stu-id="ae8db-117">Runtime</span></span>|
