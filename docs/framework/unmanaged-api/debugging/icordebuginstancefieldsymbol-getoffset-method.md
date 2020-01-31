---
title: Metodo ICorDebugInstanceFieldSymbol::GetOffset
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: f7c13d397b39698bdf1a22f14820680e1fd0a25f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782294"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="2d54b-102">Metodo ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="2d54b-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="2d54b-103">Ottiene l'offset, in byte, di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="2d54b-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d54b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2d54b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d54b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2d54b-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="2d54b-106">Puntatore al numero di byte di offset di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="2d54b-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d54b-107">Note</span><span class="sxs-lookup"><span data-stu-id="2d54b-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d54b-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2d54b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d54b-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="2d54b-109">Requirements</span></span>  
 <span data-ttu-id="2d54b-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d54b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d54b-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d54b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d54b-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d54b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d54b-113">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d54b-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d54b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d54b-114">See also</span></span>

- [<span data-ttu-id="2d54b-115">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="2d54b-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="2d54b-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="2d54b-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
