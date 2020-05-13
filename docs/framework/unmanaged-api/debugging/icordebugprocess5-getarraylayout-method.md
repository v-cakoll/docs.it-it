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
ms.openlocfilehash: aac3d54d25b50d0e2ce3e93cdfba5a17679e1f76
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209669"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="013bf-102">Metodo ICorDebugProcess5::GetArrayLayout</span><span class="sxs-lookup"><span data-stu-id="013bf-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="013bf-103">Fornisce informazioni sul layout dei tipi di matrice.</span><span class="sxs-lookup"><span data-stu-id="013bf-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="013bf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="013bf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="013bf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="013bf-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="013bf-106">in Token [COR_TYPEID](cor-typeid-structure.md) che specifica la matrice di cui si desidera il layout.</span><span class="sxs-lookup"><span data-stu-id="013bf-106">[in] A [COR_TYPEID](cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="013bf-107">out Puntatore a una struttura [COR_ARRAY_LAYOUT](cor-array-layout-structure.md) che contiene informazioni sul layout della matrice in memoria.</span><span class="sxs-lookup"><span data-stu-id="013bf-107">[out] A pointer to a [COR_ARRAY_LAYOUT](cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="013bf-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="013bf-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="013bf-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="013bf-109">Requirements</span></span>  
 <span data-ttu-id="013bf-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="013bf-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="013bf-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="013bf-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="013bf-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="013bf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="013bf-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="013bf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="013bf-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="013bf-114">See also</span></span>

- [<span data-ttu-id="013bf-115">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="013bf-115">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="013bf-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="013bf-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
