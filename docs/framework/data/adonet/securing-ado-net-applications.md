---
title: Protezione delle applicazioni
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: c1bdf4329665e4d29a47c26fb7dba8eb41c1cc3a
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980028"
---
# <a name="securing-adonet-applications"></a><span data-ttu-id="8716e-102">Protezione delle applicazioni ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8716e-102">Securing ADO.NET Applications</span></span>
<span data-ttu-id="8716e-103">Per scrivere un'applicazione ADO.NET protetta, non è sufficiente evitare i problemi più comuni di codifica, ad esempio la mancata convalida dell'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8716e-103">Writing a secure ADO.NET application involves more than avoiding common coding pitfalls such as not validating user input.</span></span> <span data-ttu-id="8716e-104">Un'applicazione che consente di accedere ai dati può presentare molti punti di errore, che possono essere sfruttati da utenti non autorizzati per recuperare, modificare o eliminare definitivamente dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="8716e-104">An application that accesses data has many potential points of failure that an attacker can exploit to retrieve, manipulate, or destroy sensitive data.</span></span> <span data-ttu-id="8716e-105">È pertanto importante considerare tutti gli aspetti della sicurezza, a partire dal processo di classificazione dei rischi durante la fase di progettazione dell'applicazione, fino all'eventuale distribuzione e alla manutenzione costante.</span><span class="sxs-lookup"><span data-stu-id="8716e-105">It is therefore important to understand all aspects of security, from the process of threat modeling during the design phase of your application, to its eventual deployment and ongoing maintenance.</span></span>  
  
 <span data-ttu-id="8716e-106">Con .NET Framework vengono forniti numerosi servizi, classi e strumenti utili per la protezione e l'amministrazione di applicazioni di database.</span><span class="sxs-lookup"><span data-stu-id="8716e-106">The .NET Framework provides many useful classes, services, and tools for securing and administering database applications.</span></span> <span data-ttu-id="8716e-107">Common Language Runtime (CLR) fornisce un ambiente indipendente dai tipi in cui eseguire il codice, con una Sicurezza dall'accesso di codice (CAS, Code Access Security) per limitare ulteriormente le autorizzazioni del codice gestito.</span><span class="sxs-lookup"><span data-stu-id="8716e-107">The common language runtime (CLR) provides a type-safe environment for code to run in, with code access security (CAS) to restrict further the permissions of managed code.</span></span> <span data-ttu-id="8716e-108">Attenendosi alle tecniche per la generazione di codice di accesso ai dati protetto, è possibile limitare i danni inflitti da un potenziale utente non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="8716e-108">Following secure data access coding practices limits the damage that can be inflicted by a potential attacker.</span></span>  
  
 <span data-ttu-id="8716e-109">Il codice protetto non difende dai problemi di sicurezza che si possono verificare quando si usano risorse non gestite quali i database.</span><span class="sxs-lookup"><span data-stu-id="8716e-109">Writing secure code does not guard against self-inflicted security holes when working with unmanaged resources such as databases.</span></span> <span data-ttu-id="8716e-110">La maggior parte dei database di server, ad esempio SQL Server, dispone di sistemi di sicurezza interni, che aumentano la protezione se correttamente implementati.</span><span class="sxs-lookup"><span data-stu-id="8716e-110">Most server databases, such as SQL Server, have their own security systems, which enhance security when implemented correctly.</span></span> <span data-ttu-id="8716e-111">Tuttavia, anche un'origine dati con un sistema di sicurezza efficace può subire danni da un attacco se non è configurata in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="8716e-111">However, even a data source with a robust security system can be victimized in an attack if it is not configured appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8716e-112">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="8716e-112">In This Section</span></span>  
 [<span data-ttu-id="8716e-113">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="8716e-113">Security Overview</span></span>](security-overview.md)  
 <span data-ttu-id="8716e-114">Vengono forniti consigli per la progettazione di applicazioni ADO.NET protette.</span><span class="sxs-lookup"><span data-stu-id="8716e-114">Provides recommendations for designing secure ADO.NET applications.</span></span>  
  
 [<span data-ttu-id="8716e-115">Accesso sicuro ai dati</span><span class="sxs-lookup"><span data-stu-id="8716e-115">Secure Data Access</span></span>](secure-data-access.md)  
 <span data-ttu-id="8716e-116">Viene descritto come usare i dati di un'origine dati protetta.</span><span class="sxs-lookup"><span data-stu-id="8716e-116">Describes how to work with data from a secured data source.</span></span>  
  
 [<span data-ttu-id="8716e-117">Applicazioni client sicure</span><span class="sxs-lookup"><span data-stu-id="8716e-117">Secure Client Applications</span></span>](secure-client-applications.md)  
 <span data-ttu-id="8716e-118">Vengono riportate alcune considerazioni sulla sicurezza per le applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="8716e-118">Describes security considerations for client applications.</span></span>  
  
 [<span data-ttu-id="8716e-119">Sicurezza dell'accesso di codice e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8716e-119">Code Access Security and ADO.NET</span></span>](code-access-security.md)  
 <span data-ttu-id="8716e-120">Viene descritto come usare la sicurezza dall'accesso di codice per migliorare la protezione del codice ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="8716e-120">Describes how CAS can help protect ADO.NET code.</span></span> <span data-ttu-id="8716e-121">Viene inoltre illustrato come operare in un contesto di attendibilità parziale.</span><span class="sxs-lookup"><span data-stu-id="8716e-121">Also discusses how to work with partial trust.</span></span>  
  
 [<span data-ttu-id="8716e-122">Privacy e sicurezza dei dati</span><span class="sxs-lookup"><span data-stu-id="8716e-122">Privacy and Data Security</span></span>](privacy-and-data-security.md)  
 <span data-ttu-id="8716e-123">Vengono descritte le opzioni di crittografia disponibili per le applicazioni ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="8716e-123">Describes encryption options for ADO.NET applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8716e-124">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="8716e-124">Related Sections</span></span>  
 [<span data-ttu-id="8716e-125">Sicurezza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="8716e-125">SQL Server Security</span></span>](./sql/sql-server-security.md)  
 <span data-ttu-id="8716e-126">Vengono descritte le funzionalità di sicurezza di SQL Server dal punto di vista di uno sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="8716e-126">Describes SQL Server security features from a developer's perspective.</span></span>  
  
 [<span data-ttu-id="8716e-127">Considerazioni sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="8716e-127">Security Considerations</span></span>](./ef/security-considerations.md)  
 <span data-ttu-id="8716e-128">Viene descritta la sicurezza per le applicazioni Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="8716e-128">Describes security for Entity Framework applications.</span></span>  
  
 [<span data-ttu-id="8716e-129">Security</span><span class="sxs-lookup"><span data-stu-id="8716e-129">Security</span></span>](../../../standard/security/index.md)  
 <span data-ttu-id="8716e-130">Contiene collegamenti ad argomenti in cui vengono descritti tutti gli aspetti della sicurezza in .NET.</span><span class="sxs-lookup"><span data-stu-id="8716e-130">Contains links to topics describing all aspects of security in .NET.</span></span>  
  
 <span data-ttu-id="8716e-131">[Strumenti di sicurezza](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="8716e-131">[Security Tools](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span></span>  
 <span data-ttu-id="8716e-132">Vengono fornite informazioni sugli strumenti di .NET Framework per la protezione e l'amministrazione dei criteri di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8716e-132">.NET Framework tools for securing and administering security policy.</span></span>  
  
 <span data-ttu-id="8716e-133">[Risorse per la creazione di applicazioni sicure](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8716e-133">[Resources for Creating Secure Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span></span>  
 <span data-ttu-id="8716e-134">Vengono forniti collegamenti ad argomenti relativi alla creazione di applicazioni protette.</span><span class="sxs-lookup"><span data-stu-id="8716e-134">Provides links to topics for creating secure applications.</span></span>  
  
 [<span data-ttu-id="8716e-135">Bibliografia sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="8716e-135">Security Bibliography</span></span>](/visualstudio/ide/securing-applications)  
 <span data-ttu-id="8716e-136">Vengono forniti collegamenti a risorse esterne disponibili online e in formato cartaceo.</span><span class="sxs-lookup"><span data-stu-id="8716e-136">Provides links to external resources available online and in print.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8716e-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8716e-137">See also</span></span>

- [<span data-ttu-id="8716e-138">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8716e-138">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="8716e-139">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8716e-139">ADO.NET Overview</span></span>](ado-net-overview.md)
