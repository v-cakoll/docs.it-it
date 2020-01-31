---
title: Metodo ICorDebugMergedAssemblyRecord::GetPublicKey
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
ms.openlocfilehash: c8c6e9adcb9d29f5e234dd1b8dfd351fac575301
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793111"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="fd361-102">Metodo ICorDebugMergedAssemblyRecord::GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="fd361-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="fd361-103">Ottiene la chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="fd361-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd361-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd361-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd361-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fd361-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="fd361-106">[in] Numero massimo di byte nella matrice di `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="fd361-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="fd361-107">[out] Puntatore al numero effettivo di byte scritti nella matrice di `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="fd361-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="fd361-108">[in] Puntatore a una matrice di byte che contiene la chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="fd361-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd361-109">Note</span><span class="sxs-lookup"><span data-stu-id="fd361-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd361-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fd361-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd361-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="fd361-111">Requirements</span></span>  
 <span data-ttu-id="fd361-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd361-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd361-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd361-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd361-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd361-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd361-115">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd361-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd361-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd361-116">See also</span></span>

- [<span data-ttu-id="fd361-117">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="fd361-117">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="fd361-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="fd361-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
