---
title: 'Metodo interfacce icordebugcode4:: EnumerateVariableHomes'
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
ms.openlocfilehash: 5f731b1459542c3f5378790b21f2ea576e89ad97
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893347"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="9c97a-102">Metodo interfacce icordebugcode4:: EnumerateVariableHomes</span><span class="sxs-lookup"><span data-stu-id="9c97a-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="9c97a-103">Ottiene un enumeratore per le variabili e gli argomenti locali in una funzione.</span><span class="sxs-lookup"><span data-stu-id="9c97a-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c97a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c97a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c97a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9c97a-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="9c97a-106">Puntatore all'indirizzo di un oggetto interfaccia [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) che è un enumeratore per le variabili e gli argomenti locali in una funzione.</span><span class="sxs-lookup"><span data-stu-id="9c97a-106">A pointer to the address of an [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c97a-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9c97a-107">Remarks</span></span>  
 <span data-ttu-id="9c97a-108">L'oggetto interfaccia [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) è un enumeratore standard derivato dall'interfaccia "ICorDebugEnum" che consente di enumerare gli oggetti [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9c97a-108">The [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="9c97a-109">La raccolta può includere più oggetti [ICorDebugVariableHome](icordebugvariablehome-interface.md) per lo stesso indice di slot o di argomento se hanno case diverse in punti diversi della funzione.</span><span class="sxs-lookup"><span data-stu-id="9c97a-109">The collection may include multiple [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c97a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9c97a-110">Requirements</span></span>  
 <span data-ttu-id="9c97a-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c97a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c97a-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c97a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c97a-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c97a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c97a-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c97a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c97a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c97a-115">See also</span></span>

- [<span data-ttu-id="9c97a-116">Interfaccia ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="9c97a-116">ICorDebugCode4 Interface</span></span>](icordebugcode4-interface.md)
- [<span data-ttu-id="9c97a-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9c97a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
