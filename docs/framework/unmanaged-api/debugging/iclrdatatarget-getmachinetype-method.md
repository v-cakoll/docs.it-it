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
ms.openlocfilehash: 9d86b23b91702929a86334f557a8d647e19861a4
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860599"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="88c73-102">Metodo ICLRDataTarget::GetMachineType</span><span class="sxs-lookup"><span data-stu-id="88c73-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="88c73-103">Ottiene l'identificatore per il tipo di set di istruzioni utilizzato dal processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="88c73-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88c73-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="88c73-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88c73-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="88c73-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="88c73-106">out Puntatore a un valore che indica il set di istruzioni utilizzato dal processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="88c73-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="88c73-107">L'oggetto `machineType` restituito è una delle costanti IMAGE_FILE_MACHINE, definite nel file di intestazione Winnt. h.</span><span class="sxs-lookup"><span data-stu-id="88c73-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88c73-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="88c73-108">Requirements</span></span>  
 <span data-ttu-id="88c73-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88c73-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88c73-110">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="88c73-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="88c73-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88c73-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88c73-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88c73-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88c73-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88c73-113">See also</span></span>

- [<span data-ttu-id="88c73-114">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="88c73-114">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
