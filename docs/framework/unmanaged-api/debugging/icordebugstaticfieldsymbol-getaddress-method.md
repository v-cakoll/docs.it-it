---
title: Metodo ICorDebugStaticFieldSymbol::GetAddress
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
ms.openlocfilehash: 7b8072234df172eeafd77db90287ea3319c08ec7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378758"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="89b10-102">Metodo ICorDebugStaticFieldSymbol::GetAddress</span><span class="sxs-lookup"><span data-stu-id="89b10-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="89b10-103">Ottiene l'indirizzo di un campo statico.</span><span class="sxs-lookup"><span data-stu-id="89b10-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89b10-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89b10-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89b10-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="89b10-105">Parameters</span></span>  
 <span data-ttu-id="89b10-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="89b10-106">pRVA</span></span>  
 <span data-ttu-id="89b10-107">[out] Puntatore all'indirizzo RVA (Relative Virtual Address) del campo statico.</span><span class="sxs-lookup"><span data-stu-id="89b10-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89b10-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="89b10-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="89b10-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="89b10-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89b10-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="89b10-110">Requirements</span></span>  
 <span data-ttu-id="89b10-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89b10-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89b10-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89b10-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89b10-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89b10-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89b10-114">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89b10-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89b10-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89b10-115">See also</span></span>

- [<span data-ttu-id="89b10-116">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="89b10-116">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="89b10-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="89b10-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
