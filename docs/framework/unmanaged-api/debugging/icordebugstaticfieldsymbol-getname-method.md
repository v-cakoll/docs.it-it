---
title: Metodo ICorDebugStaticFieldSymbol::GetName
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
ms.openlocfilehash: 0e4c52ff1ae6113ee2c3990a9d91682e10141902
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791825"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="9a3e0-102">Metodo ICorDebugStaticFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="9a3e0-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="9a3e0-103">Ottiene il nome del campo statico.</span><span class="sxs-lookup"><span data-stu-id="9a3e0-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a3e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a3e0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a3e0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a3e0-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="9a3e0-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="9a3e0-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="9a3e0-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="9a3e0-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="9a3e0-108">[out] Matrice di caratteri contenente il nome restituito.</span><span class="sxs-lookup"><span data-stu-id="9a3e0-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a3e0-109">Note</span><span class="sxs-lookup"><span data-stu-id="9a3e0-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9a3e0-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9a3e0-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a3e0-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9a3e0-111">Requirements</span></span>  
 <span data-ttu-id="9a3e0-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a3e0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a3e0-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a3e0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a3e0-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a3e0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a3e0-115">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a3e0-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a3e0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a3e0-116">See also</span></span>

- [<span data-ttu-id="9a3e0-117">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="9a3e0-117">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="9a3e0-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9a3e0-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
