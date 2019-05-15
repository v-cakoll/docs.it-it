---
title: Posizione dell'assembly
ms.date: 03/30/2017
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c736b4fe2a4bc38d4345413fa00d4cf7e5a80be7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607728"
---
# <a name="assembly-location"></a><span data-ttu-id="d0f30-102">Posizione dell'assembly</span><span class="sxs-lookup"><span data-stu-id="d0f30-102">Assembly Location</span></span>
<span data-ttu-id="d0f30-103">La posizione dell'assembly determina se Common Language Runtime può individuarlo quando rileva un riferimento all'assembly e può determinare se l'assembly è condivisibile con altri assembly.</span><span class="sxs-lookup"><span data-stu-id="d0f30-103">An assembly's location determines whether the common language runtime can locate it when referenced, and can also determine whether the assembly can be shared with other assemblies.</span></span> <span data-ttu-id="d0f30-104">È possibile distribuire un assembly nelle seguenti posizioni:</span><span class="sxs-lookup"><span data-stu-id="d0f30-104">You can deploy an assembly in the following locations:</span></span>  
  
- <span data-ttu-id="d0f30-105">Directory o sottodirectory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d0f30-105">The application's directory or subdirectories.</span></span>  
  
     <span data-ttu-id="d0f30-106">Questa è la posizione più comune per la distribuzione di un assembly.</span><span class="sxs-lookup"><span data-stu-id="d0f30-106">This is the most common location for deploying an assembly.</span></span> <span data-ttu-id="d0f30-107">Le sottodirectory della directory radice di un'applicazione possono essere basate sulla lingua o sulle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="d0f30-107">The subdirectories of an application's root directory can be based on language or culture.</span></span> <span data-ttu-id="d0f30-108">Se un assembly dispone di informazioni nell'attributo delle impostazioni cultura, deve trovarsi in una sottodirectory della directory dell'applicazione con il nome delle impostazioni cultura specificato nell'attributo.</span><span class="sxs-lookup"><span data-stu-id="d0f30-108">If an assembly has information in the culture attribute, it must be in a subdirectory under the application directory with that culture's name.</span></span>  
  
- <span data-ttu-id="d0f30-109">Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="d0f30-109">The global assembly cache.</span></span>  
  
     <span data-ttu-id="d0f30-110">Cache di codice a livello dell'intero computer che viene installata nella stessa posizione di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="d0f30-110">This is a machine-wide code cache that is installed wherever the common language runtime is installed.</span></span> <span data-ttu-id="d0f30-111">Nella maggior parte dei casi se si prevede di condividere un assembly con più applicazioni è cosigliabile distribuirlo nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="d0f30-111">In most cases, if you intend to share an assembly with multiple applications, you should deploy it into the global assembly cache.</span></span>  
  
- <span data-ttu-id="d0f30-112">In un server HTTP.</span><span class="sxs-lookup"><span data-stu-id="d0f30-112">On an HTTP server.</span></span>  
  
     <span data-ttu-id="d0f30-113">Un assembly distribuito in un server HTTP deve avere un nome sicuro. È possibile specificare l'assembly nella sezione codebase del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d0f30-113">An assembly deployed on an HTTP server must have a strong name; you point to the assembly in the codebase section of the application's configuration file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0f30-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0f30-114">See also</span></span>

- [<span data-ttu-id="d0f30-115">Creazione degli assembly</span><span class="sxs-lookup"><span data-stu-id="d0f30-115">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)
- [<span data-ttu-id="d0f30-116">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="d0f30-116">Global Assembly Cache</span></span>](../../../docs/framework/app-domains/gac.md)
- [<span data-ttu-id="d0f30-117">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="d0f30-117">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="d0f30-118">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="d0f30-118">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
