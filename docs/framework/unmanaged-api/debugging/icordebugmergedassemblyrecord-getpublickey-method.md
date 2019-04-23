---
title: 'Metodo icordebugmergedassemblyrecord:: GetPublicKey'
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 610e46d5cb550a266c5558c49239d1818c1e85de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107276"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="4dd26-102">Metodo icordebugmergedassemblyrecord:: GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="4dd26-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="4dd26-103">Ottiene la chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4dd26-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dd26-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4dd26-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dd26-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4dd26-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="4dd26-106">[in] Numero massimo di byte nella matrice di `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="4dd26-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="4dd26-107">[out] Puntatore al numero effettivo di byte scritti nella matrice di `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="4dd26-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="4dd26-108">[in] Puntatore a una matrice di byte che contiene la chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4dd26-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4dd26-109">Note</span><span class="sxs-lookup"><span data-stu-id="4dd26-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4dd26-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4dd26-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dd26-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4dd26-111">Requirements</span></span>  
 <span data-ttu-id="4dd26-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dd26-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dd26-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4dd26-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4dd26-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4dd26-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4dd26-115">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dd26-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dd26-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4dd26-116">See also</span></span>

- [<span data-ttu-id="4dd26-117">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="4dd26-117">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="4dd26-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4dd26-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
