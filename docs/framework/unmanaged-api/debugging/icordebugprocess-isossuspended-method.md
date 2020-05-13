---
title: Metodo ICorDebugProcess::IsOSSuspended
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
ms.openlocfilehash: 9452f238bd84c9c185ca8e007acac563474d29df
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212061"
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="6b6d1-102">Metodo ICorDebugProcess::IsOSSuspended</span><span class="sxs-lookup"><span data-stu-id="6b6d1-102">ICorDebugProcess::IsOSSuspended Method</span></span>
<span data-ttu-id="6b6d1-103">Ottiene un valore che indica se il thread specificato è stato sospeso a causa dell'arresto del processo da parte del debugger.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b6d1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b6d1-104">Syntax</span></span>  
  
```cpp  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b6d1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6b6d1-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="6b6d1-106">in ID del thread in questione.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="6b6d1-107">out Puntatore a un valore booleano che è `true` se il thread specificato è stato sospeso; in caso contrario, \* `pbSuspended` è `false` .</span><span class="sxs-lookup"><span data-stu-id="6b6d1-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise \*`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b6d1-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6b6d1-108">Remarks</span></span>  
 <span data-ttu-id="6b6d1-109">Quando il thread specificato è stato sospeso a causa dell'arresto del processo da parte del debugger, il numero di sospensione Win32 del thread specificato viene incrementato di uno.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="6b6d1-110">L'interfaccia utente del debugger può voler prendere in considerazione queste informazioni se Visualizza il numero di sospensione del thread del sistema operativo per l'utente.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="6b6d1-111">Il `IsOSSuspended` metodo è utile solo nel contesto del debug non gestito.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="6b6d1-112">Durante il debug gestito, i thread vengono sospesi in modo cooperativo anziché sospesi dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6b6d1-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b6d1-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b6d1-113">Requirements</span></span>  
 <span data-ttu-id="6b6d1-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b6d1-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b6d1-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b6d1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b6d1-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b6d1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b6d1-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b6d1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
