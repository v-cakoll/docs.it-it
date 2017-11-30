---
title: 'Procedura: Scaricare un dominio dell''applicazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Unload method
- application domains, unloading
- unloading application domains
ms.assetid: f356116d-e415-4f7c-a332-6e6a60227192
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 58fd1477715bafa4e3455a3e476acbae3a098dbe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-unload-an-application-domain"></a><span data-ttu-id="f0ea3-102">Procedura: Scaricare un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="f0ea3-102">How to: Unload an Application Domain</span></span>
<span data-ttu-id="f0ea3-103">Dopo aver usato un dominio dell'applicazione, scaricare il dominio usando il metodo <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-103">When you have finished using an application domain, unload it using the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f0ea3-104">Il metodo **Unload** consente di chiudere normalmente il dominio dell'applicazione specificato.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-104">The **Unload** method gracefully shuts down the specified application domain.</span></span> <span data-ttu-id="f0ea3-105">Durante il processo di scaricamento, nessun nuovo thread può accedere al dominio dell'applicazione e tutte le strutture dei dati specifiche del dominio dell'applicazione vengono liberate.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-105">During the unloading process, no new threads can access the application domain, and all application domain–specific data structures are freed.</span></span>  
  
 <span data-ttu-id="f0ea3-106">Gli assembly caricati nel dominio dell'applicazione vengono rimossi e non risultano più disponibili.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-106">Assemblies loaded into the application domain are removed and are no longer available.</span></span> <span data-ttu-id="f0ea3-107">Se un assembly nel dominio dell'applicazione è indipendente dal dominio, i dati relativi all'assembly rimarranno in memoria fino alla chiusura dell'intero processo.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-107">If an assembly in the application domain is domain-neutral, data for the assembly remains in memory until the entire process is shut down.</span></span> <span data-ttu-id="f0ea3-108">L'unico meccanismo che consente lo scaricamento di un assembly indipendente dal dominio consiste nella chiusura dell'intero processo.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-108">There is no mechanism to unload a domain-neutral assembly other than shutting down the entire process.</span></span> <span data-ttu-id="f0ea3-109">In alcune situazioni non è possibile scaricare un dominio dell'applicazione e viene generata un'eccezione <xref:System.CannotUnloadAppDomainException>.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-109">There are situations where the request to unload an application domain does not work and results in a <xref:System.CannotUnloadAppDomainException>.</span></span>  
  
 <span data-ttu-id="f0ea3-110">L'esempio seguente consente di creare un nuovo dominio dell'applicazione denominato `MyDomain`, stampare alcune informazioni nella console e quindi scaricare il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-110">The following example creates a new application domain called `MyDomain`, prints some information to the console, and then unloads the application domain.</span></span> <span data-ttu-id="f0ea3-111">Si noti che il codice tenta in seguito di stampare il nome descrittivo del dominio dell'applicazione scaricato nella console.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-111">Note that the code then attempts to print the friendly name of the unloaded application domain to the console.</span></span> <span data-ttu-id="f0ea3-112">Questa operazione genera un'eccezione che viene gestita da istruzioni try/catch alla fine del programma.</span><span class="sxs-lookup"><span data-stu-id="f0ea3-112">This action generates an exception that is handled by the try/catch statements at the end of the program.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0ea3-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="f0ea3-113">Example</span></span>  
 [!code-cpp[System.AppDomain.Load#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source3.cpp#3)]
 [!code-csharp[System.AppDomain.Load#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source3.cs#3)]
 [!code-vb[System.AppDomain.Load#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source3.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="f0ea3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0ea3-114">See Also</span></span>  
 [<span data-ttu-id="f0ea3-115">Programmazione con i domini applicazione</span><span class="sxs-lookup"><span data-stu-id="f0ea3-115">Programming with Application Domains</span></span>](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131)  
 [<span data-ttu-id="f0ea3-116">Procedura: Creare un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="f0ea3-116">How to: Create an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 [<span data-ttu-id="f0ea3-117">Uso dei domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="f0ea3-117">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
