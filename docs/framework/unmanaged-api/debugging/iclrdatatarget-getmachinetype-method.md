---
title: Metodo ICLRDataTarget::GetMachineType
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetMachineType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetMachineType
helpviewer_keywords:
- ICLRDataTarget::GetMachineType method [.NET Framework debugging]
- GetMachineType method [.NET Framework debugging]
ms.assetid: 5f1f9c61-3e3b-48b2-b111-a4395f7623a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff9c88d534e0bfe51075a76581af37aba791a3da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698252"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="c84df-102">Metodo ICLRDataTarget::GetMachineType</span><span class="sxs-lookup"><span data-stu-id="c84df-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="c84df-103">Ottiene l'identificatore per il tipo di set di istruzioni che utilizza il processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c84df-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c84df-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c84df-104">Syntax</span></span>  
  
```  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c84df-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c84df-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="c84df-106">[out] Usa puntatore a un valore che indica che il set di istruzioni che il processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c84df-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="c84df-107">L'oggetto restituito `machineType` è una delle costanti IMAGE_FILE_MACHINE, che sono definite nel file di intestazione Winnt. H.</span><span class="sxs-lookup"><span data-stu-id="c84df-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c84df-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c84df-108">Requirements</span></span>  
 <span data-ttu-id="c84df-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c84df-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c84df-110">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="c84df-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c84df-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c84df-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c84df-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c84df-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c84df-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c84df-113">See also</span></span>

- [<span data-ttu-id="c84df-114">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="c84df-114">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
