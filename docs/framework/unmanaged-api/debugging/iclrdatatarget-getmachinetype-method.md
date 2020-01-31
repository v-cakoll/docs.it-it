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
ms.openlocfilehash: 50ea9caf08b2ffb689760da95af4e5c3fdd77301
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793745"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="142f6-102">Metodo ICLRDataTarget::GetMachineType</span><span class="sxs-lookup"><span data-stu-id="142f6-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="142f6-103">Ottiene l'identificatore per il tipo di set di istruzioni utilizzato dal processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="142f6-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="142f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="142f6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="142f6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="142f6-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="142f6-106">out Puntatore a un valore che indica il set di istruzioni utilizzato dal processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="142f6-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="142f6-107">Il `machineType` restituito è una delle costanti IMAGE_FILE_MACHINE, definite nel file di intestazione WinNT. h.</span><span class="sxs-lookup"><span data-stu-id="142f6-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="142f6-108">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="142f6-108">Requirements</span></span>  
 <span data-ttu-id="142f6-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="142f6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="142f6-110">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="142f6-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="142f6-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="142f6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="142f6-112">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="142f6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="142f6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="142f6-113">See also</span></span>

- [<span data-ttu-id="142f6-114">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="142f6-114">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
