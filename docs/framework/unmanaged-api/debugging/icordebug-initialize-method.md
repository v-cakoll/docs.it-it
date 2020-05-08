---
title: Metodo ICorDebug::Initialize
ms.date: 03/30/2017
api_name:
- ICorDebug.Initialize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Initialize
helpviewer_keywords:
- Initialize method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Initialize method [.NET Framework debugging]
ms.assetid: 6fae3b23-5c9f-47c0-85d8-6bb75e050786
topic_type:
- apiref
ms.openlocfilehash: aeecf19cb85ce5d7781c3dfedca079e97cab76ce
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895351"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="8aa16-102">Metodo ICorDebug::Initialize</span><span class="sxs-lookup"><span data-stu-id="8aa16-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="8aa16-103">Inizializza l'oggetto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="8aa16-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aa16-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8aa16-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8aa16-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8aa16-105">Remarks</span></span>  
 <span data-ttu-id="8aa16-106">Il debugger deve chiamare `Initialize` in fase di creazione per inizializzare i servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="8aa16-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="8aa16-107">Questo metodo deve essere chiamato prima di chiamare qualsiasi altro `ICorDebug` metodo su.</span><span class="sxs-lookup"><span data-stu-id="8aa16-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8aa16-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8aa16-108">Requirements</span></span>  
 <span data-ttu-id="8aa16-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8aa16-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8aa16-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8aa16-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8aa16-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8aa16-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8aa16-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8aa16-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aa16-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8aa16-113">See also</span></span>

- [<span data-ttu-id="8aa16-114">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="8aa16-114">ICorDebug Interface</span></span>](icordebug-interface.md)
