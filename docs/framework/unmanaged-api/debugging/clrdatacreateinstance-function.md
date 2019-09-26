---
title: Funzione CLRDataCreateInstance
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- COM
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5d44f9b5dc42147959d3f1d127a64d39258f515
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274273"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="6ceb5-102">Funzione CLRDataCreateInstance</span><span class="sxs-lookup"><span data-stu-id="6ceb5-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="6ceb5-103">Crea un oggetto interfaccia per l'elemento di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ceb5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ceb5-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ceb5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6ceb5-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="6ceb5-106">in Identificatore dell'interfaccia di cui creare un'istanza.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="6ceb5-107">in Puntatore a un oggetto [ICLRDataTarget](iclrdatatarget-interface.md) implementato dall'utente che rappresenta l'elemento di destinazione per il quale creare l'oggetto interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-107">[in] A pointer to a user-implemented [ICLRDataTarget](iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="6ceb5-108">out Puntatore all'indirizzo dell'oggetto interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ceb5-109">Note</span><span class="sxs-lookup"><span data-stu-id="6ceb5-109">Remarks</span></span>  
 <span data-ttu-id="6ceb5-110">L' `ICLRDataTarget` oggetto viene implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="6ceb5-111">L'implementazione dipende dal tipo di elemento di destinazione rappresentato.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="6ceb5-112">L'elemento di destinazione può essere un processo, un dump della memoria, un computer remoto e così via.</span><span class="sxs-lookup"><span data-stu-id="6ceb5-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ceb5-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ceb5-113">Requirements</span></span>  
 <span data-ttu-id="6ceb5-114">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ceb5-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ceb5-115">**Intestazione:** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="6ceb5-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="6ceb5-116">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ceb5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ceb5-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ceb5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ceb5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ceb5-118">See also</span></span>

- [<span data-ttu-id="6ceb5-119">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="6ceb5-119">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
