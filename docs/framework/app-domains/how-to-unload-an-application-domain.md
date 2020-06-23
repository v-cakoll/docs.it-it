---
title: "Procedura: Scaricare un dominio dell'applicazione"
description: Leggere come scaricare un dominio applicazione in .NET, usando il metodo AppDomain. Unload per arrestare normalmente il dominio applicazione specificato.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Unload method
- application domains, unloading
- unloading application domains
ms.assetid: f356116d-e415-4f7c-a332-6e6a60227192
ms.openlocfilehash: b64a9553f63aa4a8deb57f23a97fa464edd64fee
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104661"
---
# <a name="how-to-unload-an-application-domain"></a><span data-ttu-id="7120d-103">Procedura: Scaricare un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="7120d-103">How to: Unload an Application Domain</span></span>
<span data-ttu-id="7120d-104">Dopo aver usato un dominio dell'applicazione, scaricare il dominio usando il metodo <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7120d-104">When you have finished using an application domain, unload it using the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7120d-105">Il metodo **Unload** consente di chiudere normalmente il dominio dell'applicazione specificato.</span><span class="sxs-lookup"><span data-stu-id="7120d-105">The **Unload** method gracefully shuts down the specified application domain.</span></span> <span data-ttu-id="7120d-106">Durante il processo di scaricamento, nessun nuovo thread può accedere al dominio dell'applicazione e tutte le strutture dei dati specifiche del dominio dell'applicazione vengono liberate.</span><span class="sxs-lookup"><span data-stu-id="7120d-106">During the unloading process, no new threads can access the application domain, and all application domain–specific data structures are freed.</span></span>  
  
 <span data-ttu-id="7120d-107">Gli assembly caricati nel dominio dell'applicazione vengono rimossi e non risultano più disponibili.</span><span class="sxs-lookup"><span data-stu-id="7120d-107">Assemblies loaded into the application domain are removed and are no longer available.</span></span> <span data-ttu-id="7120d-108">Se un assembly nel dominio dell'applicazione è indipendente dal dominio, i dati relativi all'assembly rimarranno in memoria fino alla chiusura dell'intero processo.</span><span class="sxs-lookup"><span data-stu-id="7120d-108">If an assembly in the application domain is domain-neutral, data for the assembly remains in memory until the entire process is shut down.</span></span> <span data-ttu-id="7120d-109">L'unico meccanismo che consente lo scaricamento di un assembly indipendente dal dominio consiste nella chiusura dell'intero processo.</span><span class="sxs-lookup"><span data-stu-id="7120d-109">There is no mechanism to unload a domain-neutral assembly other than shutting down the entire process.</span></span> <span data-ttu-id="7120d-110">In alcune situazioni non è possibile scaricare un dominio dell'applicazione e viene generata un'eccezione <xref:System.CannotUnloadAppDomainException>.</span><span class="sxs-lookup"><span data-stu-id="7120d-110">There are situations where the request to unload an application domain does not work and results in a <xref:System.CannotUnloadAppDomainException>.</span></span>  
  
 <span data-ttu-id="7120d-111">L'esempio seguente consente di creare un nuovo dominio dell'applicazione denominato `MyDomain`, stampare alcune informazioni nella console e quindi scaricare il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7120d-111">The following example creates a new application domain called `MyDomain`, prints some information to the console, and then unloads the application domain.</span></span> <span data-ttu-id="7120d-112">Si noti che il codice tenta in seguito di stampare il nome descrittivo del dominio dell'applicazione scaricato nella console.</span><span class="sxs-lookup"><span data-stu-id="7120d-112">Note that the code then attempts to print the friendly name of the unloaded application domain to the console.</span></span> <span data-ttu-id="7120d-113">Questa operazione genera un'eccezione che viene gestita da istruzioni try/catch alla fine del programma.</span><span class="sxs-lookup"><span data-stu-id="7120d-113">This action generates an exception that is handled by the try/catch statements at the end of the program.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7120d-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="7120d-114">Example</span></span>  
 [!code-cpp[System.AppDomain.Load#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source3.cpp#3)]
 [!code-csharp[System.AppDomain.Load#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source3.cs#3)]
 [!code-vb[System.AppDomain.Load#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source3.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="7120d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7120d-115">See also</span></span>

- [<span data-ttu-id="7120d-116">Programmazione con i domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="7120d-116">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="7120d-117">Procedura: Creare un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="7120d-117">How to: Create an Application Domain</span></span>](how-to-create-an-application-domain.md)
- [<span data-ttu-id="7120d-118">Uso dei domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="7120d-118">Using Application Domains</span></span>](use.md)
