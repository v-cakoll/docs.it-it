---
title: 'Procedura: Caricare e scaricare gli assembly'
ms.date: 08/19/2019
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
ms.openlocfilehash: 77ea97c2fc324287e9c697d630def98241432c9f
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "70973201"
---
# <a name="how-to-load-and-unload-assemblies"></a><span data-ttu-id="4050e-102">Procedura: Caricare e scaricare gli assembly</span><span class="sxs-lookup"><span data-stu-id="4050e-102">How to: Load and unload assemblies</span></span>
<span data-ttu-id="4050e-103">Gli assembly a cui fa riferimento il programma verranno caricati automaticamente dal Common Language Runtime, ma è anche possibile caricare in modo dinamico assembly specifici nel dominio applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="4050e-103">The assemblies referenced by your program will automatically be loaded by the common language runtime, but it is also possible to dynamically load specific assemblies into the current application domain.</span></span> <span data-ttu-id="4050e-104">Per altre informazioni, vedere [Procedura: Caricare gli assembly in un dominio](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)applicazione.</span><span class="sxs-lookup"><span data-stu-id="4050e-104">For more information, see [How to: Load assemblies into an application domain](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>

<span data-ttu-id="4050e-105">In .NET Framework non esiste alcun modo per scaricare un singolo assembly senza scaricare tutti i domini applicazione che lo contengono.</span><span class="sxs-lookup"><span data-stu-id="4050e-105">In .NET Framework, there is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="4050e-106">Anche se l'assembly esce dall'ambito, il file effettivo dell'assembly rimane caricato finché non vengono scaricati tutti i domini dell'applicazione che lo contengono.</span><span class="sxs-lookup"><span data-stu-id="4050e-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span> <span data-ttu-id="4050e-107">In .NET Core la <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> classe gestisce lo scaricamento degli assembly.</span><span class="sxs-lookup"><span data-stu-id="4050e-107">In .NET Core, the <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> class handles the unloading of assemblies.</span></span> <span data-ttu-id="4050e-108">Per altre informazioni, vedere [come usare ed eseguire il debug dello scaricamento di assembly in .NET Core](unloadability.md).</span><span class="sxs-lookup"><span data-stu-id="4050e-108">For more information, see [How to use and debug assembly unloadability in .NET Core](unloadability.md).</span></span>

## <a name="load-and-unload-assemblies"></a><span data-ttu-id="4050e-109">Caricare e scaricare gli assembly</span><span class="sxs-lookup"><span data-stu-id="4050e-109">Load and unload assemblies</span></span>

<span data-ttu-id="4050e-110">Per caricare un assembly in un dominio applicazione, usare uno dei diversi metodi di caricamento contenuti nelle classi <xref:System.AppDomain> e. <xref:System.Reflection.Assembly></span><span class="sxs-lookup"><span data-stu-id="4050e-110">To load an assembly into an application domain, use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection.Assembly>.</span></span> <span data-ttu-id="4050e-111">Per altre informazioni, vedere [Procedura: Caricare gli assembly in un dominio](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)applicazione.</span><span class="sxs-lookup"><span data-stu-id="4050e-111">For more information, see [How to: Load assemblies into an application domain](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span> <span data-ttu-id="4050e-112">Si noti che .NET Core supporta solo un singolo dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="4050e-112">Note that .NET Core supports only a single application domain.</span></span> 

<span data-ttu-id="4050e-113">Per scaricare un assembly nella .NET Framework, è necessario scaricare tutti i domini applicazione che lo contengono.</span><span class="sxs-lookup"><span data-stu-id="4050e-113">To unload an assembly in the .NET Framework, you must unload all of the application domains that contain it.</span></span> <span data-ttu-id="4050e-114">Per scaricare un dominio applicazione, utilizzare il <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="4050e-114">To unload an application domain, use the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4050e-115">Per altre informazioni, vedere [Procedura: Scarica un dominio](../../framework/app-domains/how-to-unload-an-application-domain.md)applicazione.</span><span class="sxs-lookup"><span data-stu-id="4050e-115">For more information, see [How to: Unload an application domain](../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>

<span data-ttu-id="4050e-116">Se si desidera scaricare alcuni assembly ma non altri in un'applicazione .NET Framework, è consigliabile creare un nuovo dominio applicazione, eseguire il codice all'interno del dominio e quindi scaricare tale dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="4050e-116">If you want to unload some assemblies but not others in a .NET Framework application, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="4050e-117">Per altre informazioni, vedere [Procedura: Scarica un dominio](../../framework/app-domains/how-to-unload-an-application-domain.md)applicazione.</span><span class="sxs-lookup"><span data-stu-id="4050e-117">For more information, see [How to: Unload an application domain](../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="4050e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4050e-118">See also</span></span>

- [<span data-ttu-id="4050e-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4050e-119">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="4050e-120">Concetti di programmazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4050e-120">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="4050e-121">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="4050e-121">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="4050e-122">Procedura: Caricare assembly in un dominio applicazione</span><span class="sxs-lookup"><span data-stu-id="4050e-122">How to: Load assemblies into an application domain</span></span>](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)