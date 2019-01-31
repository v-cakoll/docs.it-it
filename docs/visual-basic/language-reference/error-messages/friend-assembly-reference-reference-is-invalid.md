---
title: Il riferimento all'assembly Friend <reference> non è valido
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: ff2cdbebe13f6224209ef8da62600c99348c911b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286819"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="4b48a-102">Riferimento all'assembly Friend \<riferimento > non è valido</span><span class="sxs-lookup"><span data-stu-id="4b48a-102">Friend assembly reference \<reference> is invalid</span></span>
<span data-ttu-id="4b48a-103">Riferimento all'assembly Friend \<riferimento > non è valido.</span><span class="sxs-lookup"><span data-stu-id="4b48a-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="4b48a-104">Gli assembly firmati con nome sicuro devono specificare una chiave pubblica nelle relative dichiarazioni InternalsVisibleTo.</span><span class="sxs-lookup"><span data-stu-id="4b48a-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="4b48a-105">Il nome dell'assembly passato per il <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> costruttore di attributo identifica un assembly con nome sicuro, ma non include un `PublicKey` attributo.</span><span class="sxs-lookup"><span data-stu-id="4b48a-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="4b48a-106">**ID errore:** BC31535</span><span class="sxs-lookup"><span data-stu-id="4b48a-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4b48a-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="4b48a-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="4b48a-108">Determinare la chiave pubblica dell'assembly friend sicuro.</span><span class="sxs-lookup"><span data-stu-id="4b48a-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="4b48a-109">Includere la chiave pubblica come parte del nome dell'assembly passato al <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> costruttore di attributo tramite la `PublicKey` attributo.</span><span class="sxs-lookup"><span data-stu-id="4b48a-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b48a-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b48a-110">See also</span></span>
- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="4b48a-111">Assembly Friend</span><span class="sxs-lookup"><span data-stu-id="4b48a-111">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)


