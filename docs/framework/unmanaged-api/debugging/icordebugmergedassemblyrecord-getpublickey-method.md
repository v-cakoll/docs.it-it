---
title: 'Metodo metodo icordebugmergedassemblyrecord:: GetPublicKey'
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
ms.openlocfilehash: 9cf5f6b6d12303b3f59588c5fb663c457da79cb9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131388"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="d7d89-102">Metodo metodo icordebugmergedassemblyrecord:: GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="d7d89-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="d7d89-103">Ottiene la chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="d7d89-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7d89-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7d89-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7d89-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d7d89-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="d7d89-106">[in] Numero massimo di byte nella matrice di `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="d7d89-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="d7d89-107">[out] Puntatore al numero effettivo di byte scritti nella matrice di `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="d7d89-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="d7d89-108">[in] Puntatore a una matrice di byte che contiene la chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="d7d89-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7d89-109">Note</span><span class="sxs-lookup"><span data-stu-id="d7d89-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7d89-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d7d89-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7d89-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d7d89-111">Requirements</span></span>  
 <span data-ttu-id="d7d89-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7d89-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7d89-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7d89-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7d89-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7d89-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7d89-115">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7d89-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7d89-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7d89-116">See also</span></span>

- [<span data-ttu-id="d7d89-117">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="d7d89-117">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="d7d89-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d7d89-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
