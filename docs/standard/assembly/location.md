---
title: Posizione dell'assembly
ms.date: 08/20/2019
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
ms.openlocfilehash: 0b84aba749625f0f86027cd9d09a5e9a2229a3f2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73733132"
---
# <a name="assembly-location"></a><span data-ttu-id="23313-102">Posizione dell'assembly</span><span class="sxs-lookup"><span data-stu-id="23313-102">Assembly location</span></span>
<span data-ttu-id="23313-103">La posizione dell'assembly determina se Common Language Runtime può individuarlo quando rileva un riferimento all'assembly e può determinare se l'assembly è condivisibile con altri assembly.</span><span class="sxs-lookup"><span data-stu-id="23313-103">An assembly's location determines whether the common language runtime can locate it when referenced, and can also determine whether the assembly can be shared with other assemblies.</span></span> <span data-ttu-id="23313-104">È possibile distribuire un assembly nelle seguenti posizioni:</span><span class="sxs-lookup"><span data-stu-id="23313-104">You can deploy an assembly in the following locations:</span></span>

- <span data-ttu-id="23313-105">Directory o sottodirectory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="23313-105">The application's directory or subdirectories.</span></span>

     <span data-ttu-id="23313-106">Questa è la posizione più comune per la distribuzione di un assembly.</span><span class="sxs-lookup"><span data-stu-id="23313-106">This is the most common location for deploying an assembly.</span></span> <span data-ttu-id="23313-107">Le sottodirectory della directory radice di un'applicazione possono essere basate sulla lingua o sulle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="23313-107">The subdirectories of an application's root directory can be based on language or culture.</span></span> <span data-ttu-id="23313-108">Se un assembly dispone di informazioni nell'attributo delle impostazioni cultura, deve trovarsi in una sottodirectory della directory dell'applicazione con il nome delle impostazioni cultura specificato nell'attributo.</span><span class="sxs-lookup"><span data-stu-id="23313-108">If an assembly has information in the culture attribute, it must be in a subdirectory under the application directory with that culture's name.</span></span>

- <span data-ttu-id="23313-109">Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="23313-109">The global assembly cache.</span></span>

     <span data-ttu-id="23313-110">Cache di codice a livello dell'intero computer che viene installata nella stessa posizione di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="23313-110">This is a machine-wide code cache that is installed wherever the common language runtime is installed.</span></span> <span data-ttu-id="23313-111">Nella maggior parte dei casi se si prevede di condividere un assembly con più applicazioni è cosigliabile distribuirlo nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="23313-111">In most cases, if you intend to share an assembly with multiple applications, you should deploy it into the global assembly cache.</span></span>

- <span data-ttu-id="23313-112">In un server HTTP.</span><span class="sxs-lookup"><span data-stu-id="23313-112">On an HTTP server.</span></span>

     <span data-ttu-id="23313-113">Un assembly distribuito in un server HTTP deve avere un nome sicuro. È possibile specificare l'assembly nella sezione codebase del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="23313-113">An assembly deployed on an HTTP server must have a strong name; you point to the assembly in the codebase section of the application's configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="23313-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23313-114">See also</span></span>

- [<span data-ttu-id="23313-115">Creare assembly</span><span class="sxs-lookup"><span data-stu-id="23313-115">Create assemblies</span></span>](create.md)
- [<span data-ttu-id="23313-116">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="23313-116">Global assembly cache</span></span>](../../framework/app-domains/gac.md)
- [<span data-ttu-id="23313-117">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="23313-117">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
