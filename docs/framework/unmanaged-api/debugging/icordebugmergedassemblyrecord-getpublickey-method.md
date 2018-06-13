---
title: Metodo ICorDebugMergedAssemblyRecord::GetPublicKey
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 743772b3578cdbd92f66a58d2599a97c896e8172
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413735"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="80d49-102">Metodo ICorDebugMergedAssemblyRecord::GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="80d49-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="80d49-103">Ottiene la chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="80d49-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80d49-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80d49-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80d49-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="80d49-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="80d49-106">[in] Numero massimo di byte nella matrice di `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="80d49-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="80d49-107">[out] Puntatore al numero effettivo di byte scritti nella matrice di `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="80d49-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="80d49-108">[in] Puntatore a una matrice di byte che contiene la chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="80d49-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80d49-109">Note</span><span class="sxs-lookup"><span data-stu-id="80d49-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80d49-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="80d49-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80d49-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="80d49-111">Requirements</span></span>  
 <span data-ttu-id="80d49-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80d49-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80d49-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="80d49-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80d49-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="80d49-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80d49-115">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80d49-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80d49-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80d49-116">See Also</span></span>  
 [<span data-ttu-id="80d49-117">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="80d49-117">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="80d49-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="80d49-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
