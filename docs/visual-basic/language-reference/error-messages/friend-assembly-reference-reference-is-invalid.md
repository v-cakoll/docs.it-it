---
title: Riferimento all'assembly Friend &lt;riferimento&gt; non è valido
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: cdedcc18aa82f6efd8c52cdca5d915d7d78e269f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611930"
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a><span data-ttu-id="8f50c-102">Riferimento all'assembly Friend &lt;riferimento&gt; non è valido</span><span class="sxs-lookup"><span data-stu-id="8f50c-102">Friend assembly reference &lt;reference&gt; is invalid</span></span>
<span data-ttu-id="8f50c-103">Riferimento all'assembly Friend \<riferimento > non è valido.</span><span class="sxs-lookup"><span data-stu-id="8f50c-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="8f50c-104">Gli assembly firmati con nome sicuro devono specificare una chiave pubblica nelle relative dichiarazioni InternalsVisibleTo.</span><span class="sxs-lookup"><span data-stu-id="8f50c-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="8f50c-105">Il nome dell'assembly passato per il <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> costruttore di attributo identifica un assembly con nome sicuro, ma non include un `PublicKey` attributo.</span><span class="sxs-lookup"><span data-stu-id="8f50c-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="8f50c-106">**ID errore:** BC31535</span><span class="sxs-lookup"><span data-stu-id="8f50c-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8f50c-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="8f50c-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="8f50c-108">Determinare la chiave pubblica dell'assembly friend sicuro.</span><span class="sxs-lookup"><span data-stu-id="8f50c-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="8f50c-109">Includere la chiave pubblica come parte del nome dell'assembly passato al <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> costruttore di attributo tramite la `PublicKey` attributo.</span><span class="sxs-lookup"><span data-stu-id="8f50c-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f50c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f50c-110">See also</span></span>
- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="8f50c-111">Assembly Friend</span><span class="sxs-lookup"><span data-stu-id="8f50c-111">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)


