---
title: Metodo ICorDebugProcess5::GetTypeID
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess5.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeID
helpviewer_keywords:
- ICorDebugProcess5::GetTypeID method [.NET Framework debugging]
- GetTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 47dbaea4-8857-462e-93ba-fff880fc9e50
topic_type:
- apiref
ms.openlocfilehash: 499e1fd859a66bb6992c6d02a46e38c514503bd8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205592"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="3db3b-102">Metodo ICorDebugProcess5::GetTypeID</span><span class="sxs-lookup"><span data-stu-id="3db3b-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="3db3b-103">Converte un indirizzo di oggetto in un identificatore [COR_TYPEID](cor-typeid-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="3db3b-103">Converts an object address to a [COR_TYPEID](cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3db3b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3db3b-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3db3b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3db3b-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="3db3b-106">in Indirizzo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="3db3b-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="3db3b-107">Puntatore al valore [COR_TYPEID](cor-typeid-structure.md) che identifica l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="3db3b-107">A pointer to the [COR_TYPEID](cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3db3b-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3db3b-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3db3b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3db3b-109">Requirements</span></span>  
 <span data-ttu-id="3db3b-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3db3b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3db3b-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3db3b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3db3b-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3db3b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3db3b-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3db3b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db3b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3db3b-114">See also</span></span>

- [<span data-ttu-id="3db3b-115">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="3db3b-115">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="3db3b-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3db3b-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
