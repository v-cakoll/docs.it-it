---
title: 'Metodo metodo icordebugmergedassemblyrecord:: getsimplename'
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
ms.openlocfilehash: 565e27b47f2454dec1e4c2b89ee46ac5279b08b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130554"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="5f356-102">Metodo metodo icordebugmergedassemblyrecord:: getsimplename</span><span class="sxs-lookup"><span data-stu-id="5f356-102">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>
<span data-ttu-id="5f356-103">Ottiene il nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="5f356-103">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f356-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f356-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f356-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5f356-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="5f356-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="5f356-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="5f356-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="5f356-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="5f356-108">Puntatore a una matrice di caratteri.</span><span class="sxs-lookup"><span data-stu-id="5f356-108">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f356-109">Note</span><span class="sxs-lookup"><span data-stu-id="5f356-109">Remarks</span></span>  
 <span data-ttu-id="5f356-110">Questo metodo recupera il nome semplice di un assembly, ad esempio "System. Collections", senza estensione di file, versione, impostazioni cultura o token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="5f356-110">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="5f356-111">Corrisponde alla proprietà <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="5f356-111">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f356-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5f356-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f356-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f356-113">Requirements</span></span>  
 <span data-ttu-id="5f356-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f356-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f356-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f356-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f356-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f356-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f356-117">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f356-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f356-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f356-118">See also</span></span>

- [<span data-ttu-id="5f356-119">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="5f356-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="5f356-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5f356-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
