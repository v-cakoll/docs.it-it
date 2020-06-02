---
title: Autenticazione in SQL Server
description: Informazioni sull'autenticazione con SQL Server per ADO.NET, incluse la modalità di autenticazione di Windows e la modalità mista.
ms.date: 05/22/2018
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
ms.openlocfilehash: e9915598acfbdefb59069d6a9c6ef4b7c824e4c6
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286546"
---
# <a name="authentication-in-sql-server"></a><span data-ttu-id="7d39a-103">Autenticazione in SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d39a-103">Authentication in SQL Server</span></span>
<span data-ttu-id="7d39a-104">SQL Server supporta due modalità di autenticazione: la modalità di autenticazione di Windows e la modalità mista.</span><span class="sxs-lookup"><span data-stu-id="7d39a-104">SQL Server supports two authentication modes, Windows authentication mode and mixed mode.</span></span>  
  
- <span data-ttu-id="7d39a-105">L'autenticazione di Windows è l'impostazione predefinita e viene spesso definita sicurezza integrata perché questo modello di sicurezza di SQL Server è strettamente integrato con Windows.</span><span class="sxs-lookup"><span data-stu-id="7d39a-105">Windows authentication is the default, and is often referred to as integrated security because this SQL Server security model is tightly integrated with Windows.</span></span> <span data-ttu-id="7d39a-106">Vi sono account utente e di gruppo di Windows specifici considerati attendibili per accedere a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7d39a-106">Specific Windows user and group accounts are trusted to log in to SQL Server.</span></span> <span data-ttu-id="7d39a-107">Gli utenti di Windows che sono già stati autenticati non devono presentare credenziali aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="7d39a-107">Windows users who have already been authenticated do not have to present additional credentials.</span></span>  
  
- <span data-ttu-id="7d39a-108">La modalità mista supporta l'autenticazione di Windows e quella di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7d39a-108">Mixed mode supports authentication both by Windows and by SQL Server.</span></span> <span data-ttu-id="7d39a-109">Le coppie di nome utente e password vengono mantenute in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7d39a-109">User name and password pairs are maintained within SQL Server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7d39a-110">È consigliabile usare l'autenticazione di Windows, se possibile.</span><span class="sxs-lookup"><span data-stu-id="7d39a-110">We recommend using Windows authentication wherever possible.</span></span> <span data-ttu-id="7d39a-111">Questa modalità usa una serie di messaggi crittografati per autenticare gli utenti in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7d39a-111">Windows authentication uses a series of encrypted messages to authenticate users in SQL Server.</span></span> <span data-ttu-id="7d39a-112">Quando vengono usati gli account di accesso di SQL Server, i nomi e le password vengono passati attraverso la rete, riducendone la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7d39a-112">When SQL Server logins are used, SQL Server login names and encrypted passwords are passed across the network, which makes them less secure.</span></span>  
  
 <span data-ttu-id="7d39a-113">Con l'autenticazione di Windows, gli utenti sono già connessi a Windows e non devono eseguire separatamente l'accesso a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7d39a-113">With Windows authentication, users are already logged onto Windows and do not have to log on separately to SQL Server.</span></span> <span data-ttu-id="7d39a-114">L'oggetto `SqlConnection.ConnectionString` seguente specifica l'autenticazione di Windows senza richiedere agli utenti di immettere nome utente o password.</span><span class="sxs-lookup"><span data-stu-id="7d39a-114">The following `SqlConnection.ConnectionString` specifies Windows authentication without requiring users to provide a user name or password.</span></span>  
  
```csharp  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;"
```  
  
> [!NOTE]
> <span data-ttu-id="7d39a-115">Gli account di accesso sono distinti dagli utenti del database.</span><span class="sxs-lookup"><span data-stu-id="7d39a-115">Logins are distinct from database users.</span></span> <span data-ttu-id="7d39a-116">È necessario eseguire il mapping degli account di accesso o dei gruppi di Windows a utenti o ruoli del database in un'operazione separata.</span><span class="sxs-lookup"><span data-stu-id="7d39a-116">You must map logins or Windows groups to database users or roles in a separate operation.</span></span> <span data-ttu-id="7d39a-117">È quindi possibile concedere le autorizzazioni a utenti o ruoli per accedere agli oggetti del database.</span><span class="sxs-lookup"><span data-stu-id="7d39a-117">You then grant permissions to users or roles to access database objects.</span></span>  
  
## <a name="authentication-scenarios"></a><span data-ttu-id="7d39a-118">Scenari di autenticazione</span><span class="sxs-lookup"><span data-stu-id="7d39a-118">Authentication Scenarios</span></span>  
 <span data-ttu-id="7d39a-119">L'autenticazione di Windows è in genere la scelta migliore nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7d39a-119">Windows authentication is usually the best choice in the following situations:</span></span>  
  
- <span data-ttu-id="7d39a-120">Presenza di un controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="7d39a-120">There is a domain controller.</span></span>  
  
- <span data-ttu-id="7d39a-121">L'applicazione e il database si trovano nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="7d39a-121">The application and the database are on the same computer.</span></span>  
  
- <span data-ttu-id="7d39a-122">Si usa un'istanza di SQL Server Express o Local DB.</span><span class="sxs-lookup"><span data-stu-id="7d39a-122">You are using an instance of SQL Server Express or LocalDB.</span></span>  
  
 <span data-ttu-id="7d39a-123">Gli account di accesso SQL Server vengono spesso usati nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7d39a-123">SQL Server logins are often used in the following situations:</span></span>  
  
- <span data-ttu-id="7d39a-124">È presente un gruppo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7d39a-124">If you have a workgroup.</span></span>  
  
- <span data-ttu-id="7d39a-125">Gli utenti si connettono da domini diversi non attendibili.</span><span class="sxs-lookup"><span data-stu-id="7d39a-125">Users connect from different, non-trusted domains.</span></span>  
  
- <span data-ttu-id="7d39a-126">Uso di applicazioni Internet, come ad esempio ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="7d39a-126">Internet applications, such as ASP.NET.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d39a-127">Se si specifica l'autenticazione di Windows, gli account di accesso di SQL Server non vengono disabilitati.</span><span class="sxs-lookup"><span data-stu-id="7d39a-127">Specifying Windows authentication does not disable SQL Server logins.</span></span> <span data-ttu-id="7d39a-128">Usare l'istruzione Transact-SQL ALTER LOGIN DISABLE per disabilitare gli account di accesso di SQL Server con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="7d39a-128">Use the ALTER LOGIN DISABLE Transact-SQL statement to disable highly-privileged SQL Server logins.</span></span>  
  
## <a name="login-types"></a><span data-ttu-id="7d39a-129">Tipi di account di accesso</span><span class="sxs-lookup"><span data-stu-id="7d39a-129">Login Types</span></span>  
 <span data-ttu-id="7d39a-130">SQL Server supporta tre tipi di account di accesso:</span><span class="sxs-lookup"><span data-stu-id="7d39a-130">SQL Server supports three types of logins:</span></span>  
  
- <span data-ttu-id="7d39a-131">Un account utente locale di Windows o un account di dominio attendibile.</span><span class="sxs-lookup"><span data-stu-id="7d39a-131">A local Windows user account or trusted domain account.</span></span> <span data-ttu-id="7d39a-132">SQL Server si affida a Windows per l'autenticazione degli account utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="7d39a-132">SQL Server relies on Windows to authenticate the Windows user accounts.</span></span>  
  
- <span data-ttu-id="7d39a-133">Gruppo di Windows.</span><span class="sxs-lookup"><span data-stu-id="7d39a-133">Windows group.</span></span> <span data-ttu-id="7d39a-134">La concessione dell'accesso a un gruppo di Windows concede l'accesso a tutti gli account utente di Windows che sono membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="7d39a-134">Granting access to a Windows group grants access to all Windows user logins that are members of the group.</span></span>  
  
- <span data-ttu-id="7d39a-135">Account di accesso di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7d39a-135">SQL Server login.</span></span> <span data-ttu-id="7d39a-136">SQL Server archivia sia il nome utente che un hash della password nel database master, usando metodi di autenticazione interni per verificare i tentativi di accesso.</span><span class="sxs-lookup"><span data-stu-id="7d39a-136">SQL Server stores both the username and a hash of the password in the master database, by using internal authentication methods to verify login attempts.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d39a-137">SQL Server fornisce account di accesso creati da certificati o chiavi asimmetriche, usati solo per la firma del codice,</span><span class="sxs-lookup"><span data-stu-id="7d39a-137">SQL Server provides logins created from certificates or asymmetric keys that are used only for code signing.</span></span> <span data-ttu-id="7d39a-138">e non possono essere usati per la connessione a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7d39a-138">They cannot be used to connect to SQL Server.</span></span>  
  
## <a name="mixed-mode-authentication"></a><span data-ttu-id="7d39a-139">Autenticazione in modalità mista</span><span class="sxs-lookup"><span data-stu-id="7d39a-139">Mixed Mode Authentication</span></span>  
 <span data-ttu-id="7d39a-140">Se è necessario usare l'autenticazione in modalità mista, occorre creare account di accesso di SQL Server, che vengono archiviati in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7d39a-140">If you must use mixed mode authentication, you must create SQL Server logins, which are stored in SQL Server.</span></span> <span data-ttu-id="7d39a-141">È quindi necessario specificare il nome utente e la password di SQL Server in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7d39a-141">You then have to supply the SQL Server user name and password at run time.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7d39a-142">SQL Server viene installato con un account di accesso di SQL Server denominato `sa` (abbreviazione di "system administrator", amministratore di sistema).</span><span class="sxs-lookup"><span data-stu-id="7d39a-142">SQL Server installs with a SQL Server login named `sa` (an abbreviation of "system administrator").</span></span> <span data-ttu-id="7d39a-143">Assegnare una password complessa all'account di accesso `sa` e non usare l'account di accesso `sa` nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7d39a-143">Assign a strong password to the `sa` login and do not use the `sa` login in your application.</span></span> <span data-ttu-id="7d39a-144">L'account di accesso `sa` viene mappato al ruolo predefinito del server `sysadmin`, che ha credenziali amministrative irrevocabili per l'intero server.</span><span class="sxs-lookup"><span data-stu-id="7d39a-144">The `sa` login maps to the `sysadmin` fixed server role, which has irrevocable administrative credentials on the whole server.</span></span> <span data-ttu-id="7d39a-145">Se un utente malintenzionato ottiene l'accesso come amministratore di sistema, non vi sono limiti ai danni potenziali che potrebbe creare.</span><span class="sxs-lookup"><span data-stu-id="7d39a-145">There are no limits to the potential damage if an attacker gains access as a system administrator.</span></span> <span data-ttu-id="7d39a-146">Per impostazione predefinita, tutti i membri del gruppo `BUILTIN\Administrators` di Windows (il gruppo di amministratori locali) sono membri del ruolo `sysadmin`, ma possono essere rimossi da tale ruolo.</span><span class="sxs-lookup"><span data-stu-id="7d39a-146">All members of the Windows `BUILTIN\Administrators` group (the local administrator's group) are members of the `sysadmin` role by default, but can be removed from that role.</span></span>  
  
 <span data-ttu-id="7d39a-147">SQL Server fornisce i meccanismi di criteri password di Windows per gli account di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7d39a-147">SQL Server provides Windows password policy mechanisms for SQL Server logins.</span></span> <span data-ttu-id="7d39a-148">I criteri di complessità delle password sono progettati per fungere da deterrente agli attacchi a forza bruta aumentando il numero di password possibili.</span><span class="sxs-lookup"><span data-stu-id="7d39a-148">Password complexity policies are designed to deter brute force attacks by increasing the number of possible passwords.</span></span> <span data-ttu-id="7d39a-149">SQL Server possibile applicare gli stessi criteri di complessità e scadenza alle password utilizzate all'interno SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7d39a-149">SQL Server can apply the same complexity and expiration policies to passwords used inside SQL Server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7d39a-150">La concatenazione di stringhe di connessione dall'input dell'utente può rendere vulnerabili a un attacco injection alla stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="7d39a-150">Concatenating connection strings from user input can leave you vulnerable to a connection string injection attack.</span></span> <span data-ttu-id="7d39a-151">Usare <xref:System.Data.SqlClient.SqlConnectionStringBuilder> per creare stringhe di connessione sintatticamente valide in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7d39a-151">Use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="7d39a-152">Per altre informazioni, vedere [Compilatori di stringhe di connessione](../connection-string-builders.md).</span><span class="sxs-lookup"><span data-stu-id="7d39a-152">For more information, see [Connection String Builders](../connection-string-builders.md).</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="7d39a-153">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="7d39a-153">External Resources</span></span>  
 <span data-ttu-id="7d39a-154">Per ulteriori informazioni, vedere le risorse seguenti.</span><span class="sxs-lookup"><span data-stu-id="7d39a-154">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="7d39a-155">Resource</span><span class="sxs-lookup"><span data-stu-id="7d39a-155">Resource</span></span>|<span data-ttu-id="7d39a-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d39a-156">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="7d39a-157">Principals</span><span class="sxs-lookup"><span data-stu-id="7d39a-157">Principals</span></span>](/sql/relational-databases/security/authentication-access/principals-database-engine)|<span data-ttu-id="7d39a-158">Vengono descritti gli account di accesso e altre entità di sicurezza disponibili in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7d39a-158">Describes logins and other security principals in SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d39a-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d39a-159">See also</span></span>

- [<span data-ttu-id="7d39a-160">Protezione delle applicazioni ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7d39a-160">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="7d39a-161">Scenari di sicurezza delle applicazioni in SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d39a-161">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="7d39a-162">Connessione a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="7d39a-162">Connecting to a Data Source</span></span>](../connecting-to-a-data-source.md)
- [<span data-ttu-id="7d39a-163">Stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="7d39a-163">Connection Strings</span></span>](../connection-strings.md)
- [<span data-ttu-id="7d39a-164">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7d39a-164">ADO.NET Overview</span></span>](../ado-net-overview.md)
