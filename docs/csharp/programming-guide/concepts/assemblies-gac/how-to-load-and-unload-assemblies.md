---
title: 'Procedura: Caricare e scaricare gli assembly (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6bf6de24f4cbc3f3bd855b6d2cafa8120ebd90ee
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-load-and-unload-assemblies-c"></a><span data-ttu-id="94135-102">Procedura: Caricare e scaricare gli assembly (C#)</span><span class="sxs-lookup"><span data-stu-id="94135-102">How to: Load and Unload Assemblies (C#)</span></span>
<span data-ttu-id="94135-103">Gli assembly cui il programma fa riferimento verranno caricati automaticamente in fase di compilazione, ma è anche possibile caricare assembly specifici nel dominio dell'applicazione corrente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="94135-103">The assemblies referenced by your program will automatically be loaded at build time, but it is also possible to load specific assemblies into the current application domain at runtime.</span></span> <span data-ttu-id="94135-104">Per altre informazioni, vedere: [Procedura: Caricare assembly in un dominio dell'applicazione](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="94135-104">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
 <span data-ttu-id="94135-105">Non è possibile scaricare un singolo assembly senza scaricare tutti i domini dell'applicazione che lo contengono.</span><span class="sxs-lookup"><span data-stu-id="94135-105">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="94135-106">Anche se l'assembly esce dall'ambito, il file effettivo dell'assembly rimane caricato finché non vengono scaricati tutti i domini dell'applicazione che lo contengono.</span><span class="sxs-lookup"><span data-stu-id="94135-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span>  
  
 <span data-ttu-id="94135-107">Se si vogliono scaricare alcuni assembly ma non altri, è consigliabile creare un nuovo dominio dell'applicazione, eseguire il codice all'interno del dominio, e quindi scaricare tale dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="94135-107">If you want to unload some assemblies but not others, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="94135-108">Per altre informazioni, vedere [Procedura: Scaricare un dominio dell'applicazione](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="94135-108">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a><span data-ttu-id="94135-109">Per caricare un assembly in un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="94135-109">To load an assembly into an application domain</span></span>  
  
1.  <span data-ttu-id="94135-110">Usare uno dei numerosi metodi di caricamento contenuti nelle classi <xref:System.AppDomain> e <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="94135-110">Use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection>.</span></span> <span data-ttu-id="94135-111">Per altre informazioni, vedere: [Procedura: Caricare assembly in un dominio dell'applicazione](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="94135-111">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
### <a name="to-unload-an-application-domain"></a><span data-ttu-id="94135-112">Per scaricare un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="94135-112">To unload an application domain</span></span>  
  
1.  <span data-ttu-id="94135-113">Non è possibile scaricare un singolo assembly senza scaricare tutti i domini dell'applicazione che lo contengono.</span><span class="sxs-lookup"><span data-stu-id="94135-113">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="94135-114">Per scaricare i domini dell'applicazione, usare il metodo `Unload` da <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="94135-114">Use the `Unload` method from <xref:System.AppDomain> to unload the application domains.</span></span> <span data-ttu-id="94135-115">Per altre informazioni, vedere [Procedura: Scaricare un dominio dell'applicazione](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="94135-115">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94135-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94135-116">See Also</span></span>  
 <span data-ttu-id="94135-117">[Guida per programmatori C#](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="94135-117">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="94135-118">[Assembly e Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="94135-118">[Assemblies and the Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
 [<span data-ttu-id="94135-119">Procedura: Caricare assembly in un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="94135-119">How to: Load Assemblies into an Application Domain</span></span>](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)

