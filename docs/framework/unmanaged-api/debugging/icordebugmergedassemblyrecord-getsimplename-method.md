---
title: Metodo ICorDebugMergedAssemblyRecord::GetSimpleName
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
ms.openlocfilehash: 99ba27171e129e8725c3e0555a6991ef08b893da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178710"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="e0e7a-102">Metodo ICorDebugMergedAssemblyRecord::GetSimpleName</span><span class="sxs-lookup"><span data-stu-id="e0e7a-102">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>
<span data-ttu-id="e0e7a-103">Ottiene il nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e0e7a-103">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0e7a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e0e7a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0e7a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e0e7a-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="e0e7a-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="e0e7a-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="e0e7a-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="e0e7a-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="e0e7a-108">Puntatore a una matrice di caratteri.</span><span class="sxs-lookup"><span data-stu-id="e0e7a-108">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0e7a-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e0e7a-109">Remarks</span></span>  
 <span data-ttu-id="e0e7a-110">Questo metodo recupera il nome semplice di un assembly, ad esempio "System. Collections", senza estensione di file, versione, impostazioni cultura o token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="e0e7a-110">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="e0e7a-111">Corrisponde alla proprietà <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="e0e7a-111">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0e7a-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e0e7a-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0e7a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e0e7a-113">Requirements</span></span>  
 <span data-ttu-id="e0e7a-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0e7a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0e7a-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0e7a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0e7a-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0e7a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0e7a-117">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0e7a-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0e7a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0e7a-118">See also</span></span>

- [<span data-ttu-id="e0e7a-119">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="e0e7a-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="e0e7a-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e0e7a-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
