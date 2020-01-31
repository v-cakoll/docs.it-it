---
title: Metodo ICorDebugLoadedModule::GetName
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
ms.openlocfilehash: 628f85f3045533ead7ace47b11573a0b1a46df46
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782041"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="16cae-102">Metodo ICorDebugLoadedModule::GetName</span><span class="sxs-lookup"><span data-stu-id="16cae-102">ICorDebugLoadedModule::GetName Method</span></span>
<span data-ttu-id="16cae-103">Ottiene il nome del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="16cae-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16cae-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16cae-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16cae-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="16cae-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="16cae-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="16cae-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="16cae-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="16cae-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="16cae-108">[out] Matrice di caratteri che contiene il nome del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="16cae-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16cae-109">Note</span><span class="sxs-lookup"><span data-stu-id="16cae-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16cae-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="16cae-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16cae-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="16cae-111">Requirements</span></span>  
 <span data-ttu-id="16cae-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16cae-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16cae-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16cae-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16cae-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16cae-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16cae-115">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16cae-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16cae-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16cae-116">See also</span></span>

- [<span data-ttu-id="16cae-117">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="16cae-117">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="16cae-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="16cae-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
