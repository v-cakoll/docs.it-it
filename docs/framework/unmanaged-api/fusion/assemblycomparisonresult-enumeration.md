---
title: Enumerazione AssemblyComparisonResult
ms.date: 03/30/2017
api_name:
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
ms.openlocfilehash: 3d3fd88a2c1ac90f823b23d8d2bcb5b177a625c3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109004"
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="e9d1c-102">Enumerazione AssemblyComparisonResult</span><span class="sxs-lookup"><span data-stu-id="e9d1c-102">AssemblyComparisonResult Enumeration</span></span>
<span data-ttu-id="e9d1c-103">Indica l'equivalenza di due identità di assembly, come determinato dalla funzione [CompareAssemblyIdentity](compareassemblyidentity-function.md) .</span><span class="sxs-lookup"><span data-stu-id="e9d1c-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9d1c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9d1c-104">Syntax</span></span>  
  
```cpp  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,   
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,    
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,      
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,    
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion    
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a><span data-ttu-id="e9d1c-105">Members</span><span class="sxs-lookup"><span data-stu-id="e9d1c-105">Members</span></span>  
  
|<span data-ttu-id="e9d1c-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="e9d1c-106">Member name</span></span>|<span data-ttu-id="e9d1c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9d1c-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="e9d1c-108">Indica che tutti i campi di assembly nel confronto corrispondono.</span><span class="sxs-lookup"><span data-stu-id="e9d1c-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="e9d1c-109">Indica che gli assembly sono considerati equivalenti in base all'unificazione del Common Language Runtime versione (CLR) dei numeri di versione dell'assembly nella .NET Framework versione 2,0.</span><span class="sxs-lookup"><span data-stu-id="e9d1c-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="e9d1c-110">Indica una corrispondenza parziale degli assembly in base all'unificazione CLR dei numeri di versione dell'assembly nel .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="e9d1c-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="e9d1c-111">Indica una corrispondenza parziale degli assembly.</span><span class="sxs-lookup"><span data-stu-id="e9d1c-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="e9d1c-112">Indica una corrispondenza parziale degli assembly in base all'unificazione legacy dei numeri di versione.</span><span class="sxs-lookup"><span data-stu-id="e9d1c-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="e9d1c-113">Indica una corrispondenza parziale di assembly semplicemente denominati.</span><span class="sxs-lookup"><span data-stu-id="e9d1c-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="e9d1c-114">Indica che gli assembly sono considerati equivalenti in base all'unificazione CLR dei numeri di versione nelle versioni legacy del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e9d1c-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="e9d1c-115">Indica una corrispondenza tra due assembly con nome semplice i cui numeri di versione sono stati ignorati.</span><span class="sxs-lookup"><span data-stu-id="e9d1c-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="e9d1c-116">Indica che non è stata eseguita alcuna corrispondenza tra i due assembly.</span><span class="sxs-lookup"><span data-stu-id="e9d1c-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="e9d1c-117">Indica che i due assembly corrispondono a eccezione dei rispettivi numeri di versione, che corrispondono solo parzialmente.</span><span class="sxs-lookup"><span data-stu-id="e9d1c-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="e9d1c-118">Indica che i due assembly corrispondono ad eccezione dei numeri di versione, che non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="e9d1c-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="e9d1c-119">Indica che il motivo della mancata equivalenza non è noto.</span><span class="sxs-lookup"><span data-stu-id="e9d1c-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9d1c-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9d1c-120">Requirements</span></span>  
 <span data-ttu-id="e9d1c-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9d1c-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9d1c-122">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="e9d1c-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e9d1c-123">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e9d1c-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e9d1c-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9d1c-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d1c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9d1c-125">See also</span></span>

- [<span data-ttu-id="e9d1c-126">Funzione CompareAssemblyIdentity</span><span class="sxs-lookup"><span data-stu-id="e9d1c-126">CompareAssemblyIdentity Function</span></span>](compareassemblyidentity-function.md)
- [<span data-ttu-id="e9d1c-127">Enumerazioni Fusion</span><span class="sxs-lookup"><span data-stu-id="e9d1c-127">Fusion Enumerations</span></span>](fusion-enumerations.md)
