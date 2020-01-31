---
title: Metodo ICorDebugInstanceFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: eb70c441441954e2ffce6ca832c58369c606b128
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782286"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="7e3e5-102">Metodo ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="7e3e5-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="7e3e5-103">Ottiene le dimensioni, in byte, del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="7e3e5-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e3e5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e3e5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e3e5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7e3e5-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="7e3e5-106">[out] Puntatore alla lunghezza del campo.</span><span class="sxs-lookup"><span data-stu-id="7e3e5-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e3e5-107">Note</span><span class="sxs-lookup"><span data-stu-id="7e3e5-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7e3e5-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7e3e5-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e3e5-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="7e3e5-109">Requirements</span></span>  
 <span data-ttu-id="7e3e5-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e3e5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e3e5-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e3e5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e3e5-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e3e5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e3e5-113">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e3e5-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e3e5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e3e5-114">See also</span></span>

- [<span data-ttu-id="7e3e5-115">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="7e3e5-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="7e3e5-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7e3e5-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
