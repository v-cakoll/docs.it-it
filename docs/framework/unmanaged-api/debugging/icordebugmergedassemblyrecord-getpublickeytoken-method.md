---
title: Metodo ICorDebugMergedAssemblyRecord::GetPublicKeyToken
ms.date: 03/30/2017
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a4a8e5f99a845d2befe55f5939b41224f2aa47b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994903"
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a><span data-ttu-id="1dee3-102">Metodo ICorDebugMergedAssemblyRecord::GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="1dee3-102">ICorDebugMergedAssemblyRecord::GetPublicKeyToken Method</span></span>
<span data-ttu-id="1dee3-103">Ottiene il token di chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1dee3-103">Gets the assembly's public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dee3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1dee3-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
   [in] ULONG32 cbPublicKeyToken,   
   [out] ULONG32 *pcbPublicKeyToken,   
   [out, size_is(cbPublicKeyToken), length_is(*pcbPublicKeyToken)] BYTE pbPublicKeyToken[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1dee3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1dee3-105">Parameters</span></span>  
 `cbPublicKeyToken`  
 <span data-ttu-id="1dee3-106">[in] Numero massimo di byte nella matrice di `pbPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="1dee3-106">[in] The maximum number of bytes in the `pbPublicKeyToken` array.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="1dee3-107">[out] Puntatore al numero effettivo di byte scritti nella matrice di `pbPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="1dee3-107">[out] A pointer to the actual number of bytes written to the `pbPublicKeyToken` array.</span></span>  
  
 `pbPublicKeyToken`  
 <span data-ttu-id="1dee3-108">[out] Puntatore a una matrice di byte che contiene il token di chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1dee3-108">[out] A pointer to a byte array that contains the assembly's public key token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1dee3-109">Note</span><span class="sxs-lookup"><span data-stu-id="1dee3-109">Remarks</span></span>  
 <span data-ttu-id="1dee3-110">Il token di chiave pubblica di un assembly corrisponde agli ultimi otto byte di un hash SHA1 della relativa chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="1dee3-110">An assembly's public key token is the last eight bytes of a SHA1 hash of its public key.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1dee3-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="1dee3-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dee3-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1dee3-112">Requirements</span></span>  
 <span data-ttu-id="1dee3-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1dee3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dee3-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1dee3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1dee3-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1dee3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1dee3-116">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dee3-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dee3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1dee3-117">See also</span></span>

- [<span data-ttu-id="1dee3-118">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="1dee3-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="1dee3-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="1dee3-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
