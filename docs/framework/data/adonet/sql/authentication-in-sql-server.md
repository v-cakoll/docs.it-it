---
title: Autenticazione in SQL Server
ms.date: 05/22/2018
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
ms.openlocfilehash: 0fb92f9e854e2a7a800335390d0195243a749b33
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "74959966"
---
# <a name="authentication-in-sql-server"></a><span data-ttu-id="3ff27-102">Autenticazione in SQL Server</span><span class="sxs-lookup"><span data-stu-id="3ff27-102">Authentication in SQL Server</span></span>
<span data-ttu-id="3ff27-103">In SQL Server sono supportate due modalità di autenticazione: la modalità dell'autenticazione di Windows e la modalità mista.</span><span class="sxs-lookup"><span data-stu-id="3ff27-103">SQL Server supports two authentication modes, Windows authentication mode and mixed mode.</span></span>  
  
- <span data-ttu-id="3ff27-104">L'autenticazione di Windows è l'impostazione predefinita e viene spesso definita sicurezza integrata perché questo modello di sicurezza di SQL Server è strettamente integrato con Windows.</span><span class="sxs-lookup"><span data-stu-id="3ff27-104">Windows authentication is the default, and is often referred to as integrated security because this SQL Server security model is tightly integrated with Windows.</span></span> <span data-ttu-id="3ff27-105">Determinati account utente e gruppi di Windows vengono considerati attendibili per l'accesso a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3ff27-105">Specific Windows user and group accounts are trusted to log in to SQL Server.</span></span> <span data-ttu-id="3ff27-106">Gli utenti di Windows che sono già stati autenticati non devono presentare credenziali aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="3ff27-106">Windows users who have already been authenticated do not have to present additional credentials.</span></span>  
  
- <span data-ttu-id="3ff27-107">La modalità mista supporta l'autenticazione di Windows e quella di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3ff27-107">Mixed mode supports authentication both by Windows and by SQL Server.</span></span> <span data-ttu-id="3ff27-108">Le coppie di nome utente e password vengono mantenute in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3ff27-108">User name and password pairs are maintained within SQL Server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3ff27-109">Se possibile, si consiglia di usare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="3ff27-109">We recommend using Windows authentication wherever possible.</span></span> <span data-ttu-id="3ff27-110">In questa modalità viene utilizzata una serie di messaggi crittografati per autenticare gli utenti in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3ff27-110">Windows authentication uses a series of encrypted messages to authenticate users in SQL Server.</span></span> <span data-ttu-id="3ff27-111">Quando vengono usati gli account di accesso di SQL Server, i nomi e le password vengono passati attraverso la rete, riducendone la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3ff27-111">When SQL Server logins are used, SQL Server login names and encrypted passwords are passed across the network, which makes them less secure.</span></span>  
  
 <span data-ttu-id="3ff27-112">Con l'autenticazione di Windows, gli utenti sono già connessi a Windows e non devono eseguire separatamente l'accesso a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3ff27-112">With Windows authentication, users are already logged onto Windows and do not have to log on separately to SQL Server.</span></span> <span data-ttu-id="3ff27-113">L'oggetto `SqlConnection.ConnectionString` seguente specifica l'autenticazione di Windows senza richiedere agli utenti di immettere nome utente o password.</span><span class="sxs-lookup"><span data-stu-id="3ff27-113">The following `SqlConnection.ConnectionString` specifies Windows authentication without requiring users to provide a user name or password.</span></span>  
  
```csharp  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;"
```  
  
> [!NOTE]
> <span data-ttu-id="3ff27-114">Gli account di accesso sono distinti dagli utenti del database.</span><span class="sxs-lookup"><span data-stu-id="3ff27-114">Logins are distinct from database users.</span></span> <span data-ttu-id="3ff27-115">È necessario eseguire il mapping degli account di accesso o gruppi di Windows agli utenti o ruoli del database in un'operazione separata.</span><span class="sxs-lookup"><span data-stu-id="3ff27-115">You must map logins or Windows groups to database users or roles in a separate operation.</span></span> <span data-ttu-id="3ff27-116">È quindi possibile concedere le autorizzazioni agli utenti o ai ruoli per l'accesso agli oggetti di database.</span><span class="sxs-lookup"><span data-stu-id="3ff27-116">You then grant permissions to users or roles to access database objects.</span></span>  
  
## <a name="authentication-scenarios"></a><span data-ttu-id="3ff27-117">Scenari di autenticazione</span><span class="sxs-lookup"><span data-stu-id="3ff27-117">Authentication Scenarios</span></span>  
 <span data-ttu-id="3ff27-118">L'autenticazione di Windows risulta in genere la soluzione ideale nelle seguenti situazioni:</span><span class="sxs-lookup"><span data-stu-id="3ff27-118">Windows authentication is usually the best choice in the following situations:</span></span>  
  
- <span data-ttu-id="3ff27-119">È presente un controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="3ff27-119">There is a domain controller.</span></span>  
  
- <span data-ttu-id="3ff27-120">L'applicazione e il database si trovano nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="3ff27-120">The application and the database are on the same computer.</span></span>  
  
- <span data-ttu-id="3ff27-121">Si usa un'istanza di SQL Server Express o Local DB.</span><span class="sxs-lookup"><span data-stu-id="3ff27-121">You are using an instance of SQL Server Express or LocalDB.</span></span>  
  
 <span data-ttu-id="3ff27-122">Gli account di accesso di SQL Server vengono in genere usati nelle seguenti situazioni:</span><span class="sxs-lookup"><span data-stu-id="3ff27-122">SQL Server logins are often used in the following situations:</span></span>  
  
- <span data-ttu-id="3ff27-123">Si dispone di un gruppo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3ff27-123">If you have a workgroup.</span></span>  
  
- <span data-ttu-id="3ff27-124">Gli utenti si connettono da domini diversi, non attendibili.</span><span class="sxs-lookup"><span data-stu-id="3ff27-124">Users connect from different, non-trusted domains.</span></span>  
  
- <span data-ttu-id="3ff27-125">Applicazioni Internet, ad esempio ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3ff27-125">Internet applications, such as ASP.NET.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3ff27-126">Se si specifica l'autenticazione di Windows, gli account di accesso di SQL Server non vengono disabilitati.</span><span class="sxs-lookup"><span data-stu-id="3ff27-126">Specifying Windows authentication does not disable SQL Server logins.</span></span> <span data-ttu-id="3ff27-127">Utilizzare l'istruzione Transact-SQL ALTER LOGIN DISABLE per disabilitare gli account di accesso di SQL Server con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="3ff27-127">Use the ALTER LOGIN DISABLE Transact-SQL statement to disable highly-privileged SQL Server logins.</span></span>  
  
## <a name="login-types"></a><span data-ttu-id="3ff27-128">Tipi di account di accesso</span><span class="sxs-lookup"><span data-stu-id="3ff27-128">Login Types</span></span>  
 <span data-ttu-id="3ff27-129">SQL Server supporta tre tipi di account di accesso:</span><span class="sxs-lookup"><span data-stu-id="3ff27-129">SQL Server supports three types of logins:</span></span>  
  
- <span data-ttu-id="3ff27-130">Account utente di Windows locale o account di dominio attendibile.</span><span class="sxs-lookup"><span data-stu-id="3ff27-130">A local Windows user account or trusted domain account.</span></span> <span data-ttu-id="3ff27-131">SQL Server si affida a Windows per l'autenticazione degli account utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="3ff27-131">SQL Server relies on Windows to authenticate the Windows user accounts.</span></span>  
  
- <span data-ttu-id="3ff27-132">Gruppo di Windows.</span><span class="sxs-lookup"><span data-stu-id="3ff27-132">Windows group.</span></span> <span data-ttu-id="3ff27-133">L'accesso concesso a un gruppo di Windows viene assegnato a tutti gli account di accesso degli utenti di Windows che sono membri di tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="3ff27-133">Granting access to a Windows group grants access to all Windows user logins that are members of the group.</span></span>  
  
- <span data-ttu-id="3ff27-134">Account di accesso di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3ff27-134">SQL Server login.</span></span> <span data-ttu-id="3ff27-135">In SQL Server sia il nome utente che un hash della password vengono archiviati nel database master, utilizzando metodi di autenticazione interni per verificare i tentativi di accesso.</span><span class="sxs-lookup"><span data-stu-id="3ff27-135">SQL Server stores both the username and a hash of the password in the master database, by using internal authentication methods to verify login attempts.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3ff27-136">SQL Server fornisce account di accesso creati da certificati o chiavi asimmetriche, usati solo per la firma del codice,</span><span class="sxs-lookup"><span data-stu-id="3ff27-136">SQL Server provides logins created from certificates or asymmetric keys that are used only for code signing.</span></span> <span data-ttu-id="3ff27-137">che non possono essere utilizzati per la connessione a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3ff27-137">They cannot be used to connect to SQL Server.</span></span>  
  
## <a name="mixed-mode-authentication"></a><span data-ttu-id="3ff27-138">Autenticazione in modalità mista</span><span class="sxs-lookup"><span data-stu-id="3ff27-138">Mixed Mode Authentication</span></span>  
 <span data-ttu-id="3ff27-139">Se è necessario utilizzare l'autenticazione in modalità mista, occorre creare account di accesso di SQL Server, che vengono archiviati in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3ff27-139">If you must use mixed mode authentication, you must create SQL Server logins, which are stored in SQL Server.</span></span> <span data-ttu-id="3ff27-140">È quindi necessario specificare il nome utente e la password di SQL Server in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3ff27-140">You then have to supply the SQL Server user name and password at run time.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3ff27-141">SQL Server viene installato con un account di accesso denominato `sa` (abbreviazione di "system administrator").</span><span class="sxs-lookup"><span data-stu-id="3ff27-141">SQL Server installs with a SQL Server login named `sa` (an abbreviation of "system administrator").</span></span> <span data-ttu-id="3ff27-142">Assegnare una password complessa all'account di accesso `sa` e non usare l'account di accesso `sa` nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3ff27-142">Assign a strong password to the `sa` login and do not use the `sa` login in your application.</span></span> <span data-ttu-id="3ff27-143">L'account di accesso `sa` viene mappato al ruolo predefinito del server `sysadmin`, che dispone di credenziali amministrative irrevocabili nell'intero server.</span><span class="sxs-lookup"><span data-stu-id="3ff27-143">The `sa` login maps to the `sysadmin` fixed server role, which has irrevocable administrative credentials on the whole server.</span></span> <span data-ttu-id="3ff27-144">Non esistono limiti ai danni che potrebbero verificarsi se un utente non autorizzato ottiene accesso come amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="3ff27-144">There are no limits to the potential damage if an attacker gains access as a system administrator.</span></span> <span data-ttu-id="3ff27-145">Per impostazione predefinita, tutti i membri del gruppo `BUILTIN\Administrators` di Windows (il gruppo di amministratori locali) sono membri del ruolo `sysadmin`, ma possono essere rimossi da tale ruolo.</span><span class="sxs-lookup"><span data-stu-id="3ff27-145">All members of the Windows `BUILTIN\Administrators` group (the local administrator's group) are members of the `sysadmin` role by default, but can be removed from that role.</span></span>  
  
 <span data-ttu-id="3ff27-146">SQL Server fornisce i meccanismi di criteri password di Windows per gli account di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3ff27-146">SQL Server provides Windows password policy mechanisms for SQL Server logins.</span></span> <span data-ttu-id="3ff27-147">I criteri di complessità delle password sono progettati per fungere da deterrente agli attacchi a forza bruta aumentando il numero di password possibili.</span><span class="sxs-lookup"><span data-stu-id="3ff27-147">Password complexity policies are designed to deter brute force attacks by increasing the number of possible passwords.</span></span> <span data-ttu-id="3ff27-148">SQL Server possibile applicare gli stessi criteri di complessità e scadenza alle password utilizzate all'interno SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3ff27-148">SQL Server can apply the same complexity and expiration policies to passwords used inside SQL Server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3ff27-149">La concatenazione di stringhe di connessione dall'input dell'utente può lasciare il sistema vulnerabile a un attacco injection alle stringhe di connessione.</span><span class="sxs-lookup"><span data-stu-id="3ff27-149">Concatenating connection strings from user input can leave you vulnerable to a connection string injection attack.</span></span> <span data-ttu-id="3ff27-150">Usare <xref:System.Data.SqlClient.SqlConnectionStringBuilder> per creare stringhe di connessione sintatticamente valide in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3ff27-150">Use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="3ff27-151">Per altre informazioni, vedere [Compilatori di stringhe di connessione](../connection-string-builders.md).</span><span class="sxs-lookup"><span data-stu-id="3ff27-151">For more information, see [Connection String Builders](../connection-string-builders.md).</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="3ff27-152">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="3ff27-152">External Resources</span></span>  
 <span data-ttu-id="3ff27-153">Per altre informazioni, vedere le seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="3ff27-153">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="3ff27-154">Risorsa</span><span class="sxs-lookup"><span data-stu-id="3ff27-154">Resource</span></span>|<span data-ttu-id="3ff27-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ff27-155">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="3ff27-156">Entità</span><span class="sxs-lookup"><span data-stu-id="3ff27-156">Principals</span></span>](/sql/relational-databases/security/authentication-access/principals-database-engine)|<span data-ttu-id="3ff27-157">Vengono descritti gli account di accesso e altre entità di sicurezza disponibili in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3ff27-157">Describes logins and other security principals in SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ff27-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ff27-158">See also</span></span>

- [<span data-ttu-id="3ff27-159">Protezione delle applicazioni ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3ff27-159">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="3ff27-160">Scenari di sicurezza delle applicazioni in SQL Server</span><span class="sxs-lookup"><span data-stu-id="3ff27-160">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="3ff27-161">Connessione a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="3ff27-161">Connecting to a Data Source</span></span>](../connecting-to-a-data-source.md)
- [<span data-ttu-id="3ff27-162">Stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="3ff27-162">Connection Strings</span></span>](../connection-strings.md)
- [<span data-ttu-id="3ff27-163">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3ff27-163">ADO.NET Overview</span></span>](../ado-net-overview.md)
