---
title: Metodo ICorDebugInstanceFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: 3d3c6881ecd54fc48be92e5ea0dc74a5cfdabd8f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209953"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="f632c-102">Metodo ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="f632c-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="f632c-103">Ottiene le dimensioni, in byte, del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="f632c-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f632c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f632c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f632c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f632c-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="f632c-106">[out] Puntatore alla lunghezza del campo.</span><span class="sxs-lookup"><span data-stu-id="f632c-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f632c-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f632c-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f632c-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f632c-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f632c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f632c-109">Requirements</span></span>  
 <span data-ttu-id="f632c-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f632c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f632c-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f632c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f632c-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f632c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f632c-113">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f632c-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f632c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f632c-114">See also</span></span>

- [<span data-ttu-id="f632c-115">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="f632c-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="f632c-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f632c-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
