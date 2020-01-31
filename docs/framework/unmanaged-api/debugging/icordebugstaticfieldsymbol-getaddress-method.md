---
title: Metodo ICorDebugStaticFieldSymbol::GetAddress
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
ms.openlocfilehash: be4d59fe668026c4b40be4c6d0afcf718c8157bd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791840"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="a6521-102">Metodo ICorDebugStaticFieldSymbol::GetAddress</span><span class="sxs-lookup"><span data-stu-id="a6521-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="a6521-103">Ottiene l'indirizzo di un campo statico.</span><span class="sxs-lookup"><span data-stu-id="a6521-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6521-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6521-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6521-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a6521-105">Parameters</span></span>  
 <span data-ttu-id="a6521-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="a6521-106">pRVA</span></span>  
 <span data-ttu-id="a6521-107">[out] Puntatore all'indirizzo RVA (Relative Virtual Address) del campo statico.</span><span class="sxs-lookup"><span data-stu-id="a6521-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6521-108">Note</span><span class="sxs-lookup"><span data-stu-id="a6521-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6521-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a6521-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6521-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="a6521-110">Requirements</span></span>  
 <span data-ttu-id="a6521-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6521-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6521-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6521-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6521-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6521-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6521-114">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6521-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6521-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6521-115">See also</span></span>

- [<span data-ttu-id="a6521-116">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="a6521-116">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="a6521-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a6521-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
