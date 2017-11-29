---
title: 'Procedura: Caricare e scaricare gli assembly (C#)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e4b7c9e257a1fff6236770ff39f5d26cd97224b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-load-and-unload-assemblies-c"></a><span data-ttu-id="799c8-102">Procedura: Caricare e scaricare gli assembly (C#)</span><span class="sxs-lookup"><span data-stu-id="799c8-102">How to: Load and Unload Assemblies (C#)</span></span>
<span data-ttu-id="799c8-103">Gli assembly cui il programma fa riferimento verranno caricati automaticamente in fase di compilazione, ma è anche possibile caricare assembly specifici nel dominio dell'applicazione corrente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="799c8-103">The assemblies referenced by your program will automatically be loaded at build time, but it is also possible to load specific assemblies into the current application domain at runtime.</span></span> <span data-ttu-id="799c8-104">Per altre informazioni, vedere: [Procedura: Caricare assembly in un dominio dell'applicazione](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="799c8-104">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
 <span data-ttu-id="799c8-105">Non è possibile scaricare un singolo assembly senza scaricare tutti i domini dell'applicazione che lo contengono.</span><span class="sxs-lookup"><span data-stu-id="799c8-105">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="799c8-106">Anche se l'assembly esce dall'ambito, il file effettivo dell'assembly rimane caricato finché non vengono scaricati tutti i domini dell'applicazione che lo contengono.</span><span class="sxs-lookup"><span data-stu-id="799c8-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span>  
  
 <span data-ttu-id="799c8-107">Se si vogliono scaricare alcuni assembly ma non altri, è consigliabile creare un nuovo dominio dell'applicazione, eseguire il codice all'interno del dominio, e quindi scaricare tale dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="799c8-107">If you want to unload some assemblies but not others, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="799c8-108">Per altre informazioni, vedere [Procedura: Scaricare un dominio dell'applicazione](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="799c8-108">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a><span data-ttu-id="799c8-109">Per caricare un assembly in un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="799c8-109">To load an assembly into an application domain</span></span>  
  
1.  <span data-ttu-id="799c8-110">Usare uno dei numerosi metodi di caricamento contenuti nelle classi <xref:System.AppDomain> e <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="799c8-110">Use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection>.</span></span> <span data-ttu-id="799c8-111">Per altre informazioni, vedere: [Procedura: Caricare assembly in un dominio dell'applicazione](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="799c8-111">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
### <a name="to-unload-an-application-domain"></a><span data-ttu-id="799c8-112">Per scaricare un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="799c8-112">To unload an application domain</span></span>  
  
1.  <span data-ttu-id="799c8-113">Non è possibile scaricare un singolo assembly senza scaricare tutti i domini dell'applicazione che lo contengono.</span><span class="sxs-lookup"><span data-stu-id="799c8-113">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="799c8-114">Per scaricare i domini dell'applicazione, usare il metodo `Unload` da <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="799c8-114">Use the `Unload` method from <xref:System.AppDomain> to unload the application domains.</span></span> <span data-ttu-id="799c8-115">Per altre informazioni, vedere [Procedura: Scaricare un dominio dell'applicazione](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="799c8-115">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="799c8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="799c8-116">See Also</span></span>  
 [<span data-ttu-id="799c8-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="799c8-117">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="799c8-118">Assembly e Global Assembly Cache (C#)</span><span class="sxs-lookup"><span data-stu-id="799c8-118">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="799c8-119">Procedura: Caricare assembly in un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="799c8-119">How to: Load Assemblies into an Application Domain</span></span>](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
