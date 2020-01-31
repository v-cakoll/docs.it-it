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
ms.openlocfilehash: 9153503fc114b0e4052265fca7c9399510d687ef
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792325"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="23c86-102">Metodo ICorDebugProcess5::GetTypeID</span><span class="sxs-lookup"><span data-stu-id="23c86-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="23c86-103">Converte un indirizzo di oggetto in un identificatore [COR_TYPEID](cor-typeid-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="23c86-103">Converts an object address to a [COR_TYPEID](cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23c86-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23c86-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23c86-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="23c86-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="23c86-106">in Indirizzo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="23c86-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="23c86-107">Puntatore al valore [COR_TYPEID](cor-typeid-structure.md) che identifica l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="23c86-107">A pointer to the [COR_TYPEID](cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23c86-108">Note</span><span class="sxs-lookup"><span data-stu-id="23c86-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23c86-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="23c86-109">Requirements</span></span>  
 <span data-ttu-id="23c86-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23c86-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23c86-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23c86-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23c86-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23c86-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23c86-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23c86-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23c86-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23c86-114">See also</span></span>

- [<span data-ttu-id="23c86-115">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="23c86-115">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="23c86-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="23c86-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
