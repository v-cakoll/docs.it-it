---
title: Metodo ICorDebugLoadedModule::GetName
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
ms.openlocfilehash: 4a0c4e99f23dc949b0bbaa8bbda35cff1537cf3c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209864"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="305da-102">Metodo ICorDebugLoadedModule::GetName</span><span class="sxs-lookup"><span data-stu-id="305da-102">ICorDebugLoadedModule::GetName Method</span></span>
<span data-ttu-id="305da-103">Ottiene il nome del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="305da-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="305da-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="305da-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="305da-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="305da-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="305da-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="305da-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="305da-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="305da-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="305da-108">[out] Matrice di caratteri che contiene il nome del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="305da-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="305da-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="305da-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="305da-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="305da-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="305da-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="305da-111">Requirements</span></span>  
 <span data-ttu-id="305da-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="305da-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="305da-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="305da-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="305da-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="305da-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="305da-115">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="305da-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="305da-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="305da-116">See also</span></span>

- [<span data-ttu-id="305da-117">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="305da-117">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="305da-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="305da-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
