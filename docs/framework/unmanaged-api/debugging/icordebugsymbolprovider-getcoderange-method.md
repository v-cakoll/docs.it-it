---
title: Metodo ICorDebugSymbolProvider::GetCodeRange
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
ms.openlocfilehash: a9c1a4a625196d7430e365916cc7c2b67bf94127
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83376086"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a><span data-ttu-id="4af37-102">Metodo ICorDebugSymbolProvider::GetCodeRange</span><span class="sxs-lookup"><span data-stu-id="4af37-102">ICorDebugSymbolProvider::GetCodeRange Method</span></span>
<span data-ttu-id="4af37-103">Ottiene l'indirizzo iniziale del metodo e la dimensione sulla base di un indirizzo RVA (Relative Virtual Address) in un metodo.</span><span class="sxs-lookup"><span data-stu-id="4af37-103">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4af37-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4af37-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,
   [out] ULONG32* pCodeStartAddress,
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4af37-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4af37-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="4af37-106">[in] Indirizzo RVA (Relative Virtual Address) in un metodo</span><span class="sxs-lookup"><span data-stu-id="4af37-106">[in] The relative virtual address (RVA) in a method.</span></span>  
  
 `pCodeStartAddress`  
 <span data-ttu-id="4af37-107">[out] Puntatore all'indirizzo iniziale del metodo.</span><span class="sxs-lookup"><span data-stu-id="4af37-107">[out] A pointer to the starting address of the method.</span></span>  
  
 `pCodeSize`  
 <span data-ttu-id="4af37-108">Puntatore alla dimensione del codice del metodo (numero di byte del codice del metodo).</span><span class="sxs-lookup"><span data-stu-id="4af37-108">A pointer to the method code size (the number of bytes of the method's code).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4af37-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4af37-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4af37-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4af37-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4af37-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4af37-111">Requirements</span></span>  
 <span data-ttu-id="4af37-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4af37-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4af37-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4af37-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4af37-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4af37-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4af37-115">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4af37-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af37-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4af37-116">See also</span></span>

- [<span data-ttu-id="4af37-117">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="4af37-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="4af37-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4af37-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
