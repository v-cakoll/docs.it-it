---
title: Metodo ICorDebugInstanceFieldSymbol::GetOffset
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: 7d553c1a446e06f34c20da18c0edfe6773cfb597
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209981"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="d8a99-102">Metodo ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="d8a99-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="d8a99-103">Ottiene l'offset, in byte, di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="d8a99-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8a99-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8a99-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8a99-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d8a99-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="d8a99-106">Puntatore al numero di byte di offset di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="d8a99-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8a99-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d8a99-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d8a99-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d8a99-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8a99-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8a99-109">Requirements</span></span>  
 <span data-ttu-id="d8a99-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8a99-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8a99-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8a99-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8a99-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8a99-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8a99-113">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8a99-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8a99-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8a99-114">See also</span></span>

- [<span data-ttu-id="d8a99-115">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="d8a99-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="d8a99-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d8a99-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
