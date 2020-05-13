---
title: Metodo ICorDebugStaticFieldSymbol::GetName
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
ms.openlocfilehash: 75f5324296f9b42406157d06351f7e680a749444
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378754"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="1b3dc-102">Metodo ICorDebugStaticFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="1b3dc-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="1b3dc-103">Ottiene il nome del campo statico.</span><span class="sxs-lookup"><span data-stu-id="1b3dc-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b3dc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b3dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b3dc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1b3dc-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="1b3dc-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="1b3dc-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="1b3dc-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="1b3dc-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="1b3dc-108">[out] Matrice di caratteri contenente il nome restituito.</span><span class="sxs-lookup"><span data-stu-id="1b3dc-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b3dc-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1b3dc-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1b3dc-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="1b3dc-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b3dc-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b3dc-111">Requirements</span></span>  
 <span data-ttu-id="1b3dc-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b3dc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b3dc-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b3dc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b3dc-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b3dc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b3dc-115">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b3dc-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b3dc-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b3dc-116">See also</span></span>

- [<span data-ttu-id="1b3dc-117">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="1b3dc-117">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="1b3dc-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="1b3dc-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
