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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6c417eec9583ff069c9d61fa31e9c14f3931130
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778517"
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="9f054-102">Enumerazione AssemblyComparisonResult</span><span class="sxs-lookup"><span data-stu-id="9f054-102">AssemblyComparisonResult Enumeration</span></span>
<span data-ttu-id="9f054-103">Indica l'equivalenza dei due identità di assembly, come determinato dal [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="9f054-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f054-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f054-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="9f054-105">Membri</span><span class="sxs-lookup"><span data-stu-id="9f054-105">Members</span></span>  
  
|<span data-ttu-id="9f054-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="9f054-106">Member name</span></span>|<span data-ttu-id="9f054-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f054-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="9f054-108">Indica che i campi degli assembly in corrispondenza il confronto.</span><span class="sxs-lookup"><span data-stu-id="9f054-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="9f054-109">Indica che gli assembly sono considerati equivalenti base unificazione degli versione (CLR) il common language runtime dei numeri di versione di assembly in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="9f054-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="9f054-110">Indica una corrispondenza parziale degli assembly di base dell'unificazione CLR dei numeri di versione di assembly in .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="9f054-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="9f054-111">Indica una corrispondenza parziale degli assembly.</span><span class="sxs-lookup"><span data-stu-id="9f054-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="9f054-112">Indica una corrispondenza parziale degli assembly in base all'unificazione legacy di numeri di versione.</span><span class="sxs-lookup"><span data-stu-id="9f054-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="9f054-113">Indica una corrispondenza parziale di assembly con nome semplice.</span><span class="sxs-lookup"><span data-stu-id="9f054-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="9f054-114">Indica che gli assembly sono considerati equivalenti in base l'unificazione CLR di numeri di versione in versioni legacy di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9f054-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="9f054-115">Indica una corrispondenza tra i due assembly denominati semplicemente cui numeri di versione sono stati ignorati.</span><span class="sxs-lookup"><span data-stu-id="9f054-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="9f054-116">Indica che si è verificata alcuna corrispondenza tra i due assembly.</span><span class="sxs-lookup"><span data-stu-id="9f054-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="9f054-117">Indica che i due assembly corrisponde, ad eccezione dei numeri di versione che corrispondono solo parzialmente.</span><span class="sxs-lookup"><span data-stu-id="9f054-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="9f054-118">Indica che i due assembly corrisponde, ad eccezione dei numeri di versione che non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="9f054-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="9f054-119">Indica che non è noto il motivo per determinarne la non equivalenza.</span><span class="sxs-lookup"><span data-stu-id="9f054-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f054-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9f054-120">Requirements</span></span>  
 <span data-ttu-id="9f054-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f054-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f054-122">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="9f054-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9f054-123">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9f054-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9f054-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f054-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f054-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f054-125">See also</span></span>

- [<span data-ttu-id="9f054-126">Funzione CompareAssemblyIdentity</span><span class="sxs-lookup"><span data-stu-id="9f054-126">CompareAssemblyIdentity Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)
- [<span data-ttu-id="9f054-127">Enumerazioni Fusion</span><span class="sxs-lookup"><span data-stu-id="9f054-127">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
