---
title: Metodo ICorDebugRegisterSet2::GetRegistersAvailable
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
ms.openlocfilehash: 2149c985519b95f89af2c50d05753ae7259babe4
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378215"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="8ff87-102">Metodo ICorDebugRegisterSet2::GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="8ff87-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="8ff87-103">Ottiene una matrice di byte che fornisce una bitmap dei registri disponibili.</span><span class="sxs-lookup"><span data-stu-id="8ff87-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ff87-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ff87-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ff87-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8ff87-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="8ff87-106">[in] Dimensione della matrice `availableRegChunks`.</span><span class="sxs-lookup"><span data-stu-id="8ff87-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="8ff87-107">out Matrice di byte, ogni bit corrispondente a un registro.</span><span class="sxs-lookup"><span data-stu-id="8ff87-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="8ff87-108">Se è disponibile un registro, viene impostato il bit corrispondente del registro.</span><span class="sxs-lookup"><span data-stu-id="8ff87-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ff87-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8ff87-109">Remarks</span></span>  
 <span data-ttu-id="8ff87-110">I valori dell'enumerazione CorDebugRegister specificano i registri di microprocessori diversi.</span><span class="sxs-lookup"><span data-stu-id="8ff87-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="8ff87-111">I cinque bit superiori di ogni valore sono l'indice nella `availableRegChunks` matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="8ff87-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="8ff87-112">I tre bit inferiori di ogni valore identificano la posizione del bit all'interno del byte indicizzato.</span><span class="sxs-lookup"><span data-stu-id="8ff87-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="8ff87-113">Dato un `CorDebugRegister` valore che specifica un registro particolare, la posizione del registro nella maschera viene determinata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="8ff87-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1. <span data-ttu-id="8ff87-114">Estrarre l'indice necessario per accedere al byte corretto nella `availableRegChunks` matrice:</span><span class="sxs-lookup"><span data-stu-id="8ff87-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="8ff87-115">`CorDebugRegister`valore >> 3</span><span class="sxs-lookup"><span data-stu-id="8ff87-115">`CorDebugRegister` value >> 3</span></span>  
  
2. <span data-ttu-id="8ff87-116">Estrae la posizione del bit all'interno del byte indicizzato, dove bit zero è il bit meno significativo:</span><span class="sxs-lookup"><span data-stu-id="8ff87-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="8ff87-117">`CorDebugRegister`valore & 7</span><span class="sxs-lookup"><span data-stu-id="8ff87-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ff87-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8ff87-118">Requirements</span></span>  
 <span data-ttu-id="8ff87-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ff87-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ff87-120">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ff87-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ff87-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ff87-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ff87-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ff87-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ff87-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ff87-123">See also</span></span>

- [<span data-ttu-id="8ff87-124">Interfaccia ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="8ff87-124">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="8ff87-125">Interfaccia ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="8ff87-125">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
