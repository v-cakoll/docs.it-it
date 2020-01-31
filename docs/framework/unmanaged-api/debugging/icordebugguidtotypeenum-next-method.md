---
title: Metodo ICorDebugGuidToTypeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
ms.openlocfilehash: 76cab0b8b5f16f24c62e31be2707c95c7e557034
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777636"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="2014a-102">Metodo ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="2014a-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="2014a-103">Ottiene il numero specificato di istanze di [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) che mappano i GUID alle informazioni sul tipo.</span><span class="sxs-lookup"><span data-stu-id="2014a-103">Gets the specified number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2014a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2014a-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2014a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2014a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2014a-106">in Numero di oggetti mapping da GUID a tipo da recuperare.</span><span class="sxs-lookup"><span data-stu-id="2014a-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="2014a-107">out Matrice di puntatori, ciascuno dei quali punta a un oggetto [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) che esegue il mapping di un GUID Windows Runtime al relativo oggetto ICorDebugType corrispondente.</span><span class="sxs-lookup"><span data-stu-id="2014a-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) object that maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="2014a-108">out Puntatore al numero di oggetti [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) effettivamente restituiti in `values`.</span><span class="sxs-lookup"><span data-stu-id="2014a-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2014a-109">Note</span><span class="sxs-lookup"><span data-stu-id="2014a-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2014a-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="2014a-110">Requirements</span></span>  
 <span data-ttu-id="2014a-111">**Piattaforme:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="2014a-111">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="2014a-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2014a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2014a-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2014a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2014a-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2014a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2014a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2014a-115">See also</span></span>

- [<span data-ttu-id="2014a-116">Interfaccia ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="2014a-116">ICorDebugGuidToTypeEnum Interface</span></span>](icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="2014a-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="2014a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
