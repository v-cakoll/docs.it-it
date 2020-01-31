---
title: Metodo ICorDebugProcess5::GetArrayLayout
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetArrayLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetArrayLayout
helpviewer_keywords:
- ICorDebugProcess5::GetArrayLayout method [.NET Framework debugging]
- GetArrayLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 9a7393b9-9735-43c6-8616-afb103c432fd
topic_type:
- apiref
ms.openlocfilehash: ea7630efedb7b667dc58174eda0cb98d9f382cfc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792392"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="d9fc8-102">Metodo ICorDebugProcess5::GetArrayLayout</span><span class="sxs-lookup"><span data-stu-id="d9fc8-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="d9fc8-103">Fornisce informazioni sul layout dei tipi di matrice.</span><span class="sxs-lookup"><span data-stu-id="d9fc8-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9fc8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9fc8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9fc8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d9fc8-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="d9fc8-106">in Token [COR_TYPEID](cor-typeid-structure.md) che specifica la matrice di cui si desidera il layout.</span><span class="sxs-lookup"><span data-stu-id="d9fc8-106">[in] A [COR_TYPEID](cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="d9fc8-107">out Puntatore a una struttura [COR_ARRAY_LAYOUT](cor-array-layout-structure.md) che contiene informazioni sul layout della matrice in memoria.</span><span class="sxs-lookup"><span data-stu-id="d9fc8-107">[out] A pointer to a [COR_ARRAY_LAYOUT](cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9fc8-108">Note</span><span class="sxs-lookup"><span data-stu-id="d9fc8-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9fc8-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="d9fc8-109">Requirements</span></span>  
 <span data-ttu-id="d9fc8-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9fc8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9fc8-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9fc8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9fc8-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9fc8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9fc8-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9fc8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9fc8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9fc8-114">See also</span></span>

- [<span data-ttu-id="d9fc8-115">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="d9fc8-115">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="d9fc8-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d9fc8-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
