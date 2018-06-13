---
title: Metodo ICorDebugMergedAssemblyRecord::GetSimpleName
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8c5499b63e5201fbf42ece07f4f3eff52129e09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417492"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="43660-102">Metodo ICorDebugMergedAssemblyRecord::GetSimpleName</span><span class="sxs-lookup"><span data-stu-id="43660-102">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>
<span data-ttu-id="43660-103">Ottiene il nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="43660-103">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43660-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43660-104">Syntax</span></span>  
  
```  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43660-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="43660-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="43660-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="43660-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="43660-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="43660-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="43660-108">Puntatore a una matrice di caratteri.</span><span class="sxs-lookup"><span data-stu-id="43660-108">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43660-109">Note</span><span class="sxs-lookup"><span data-stu-id="43660-109">Remarks</span></span>  
 <span data-ttu-id="43660-110">Questo metodo recupera il nome semplice di un assembly, ad esempio "System. Collections", senza estensione di file, versione, impostazioni cultura o token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="43660-110">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="43660-111">Corrisponde alla proprietà <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="43660-111">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43660-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="43660-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43660-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="43660-113">Requirements</span></span>  
 <span data-ttu-id="43660-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43660-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43660-115">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="43660-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43660-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="43660-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43660-117">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43660-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43660-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43660-118">See Also</span></span>  
 [<span data-ttu-id="43660-119">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="43660-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="43660-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="43660-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
