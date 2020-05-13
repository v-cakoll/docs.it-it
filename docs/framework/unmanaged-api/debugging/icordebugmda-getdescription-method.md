---
title: Metodo ICorDebugMDA::GetDescription
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetDescription
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetDescription
helpviewer_keywords:
- GetDescription method [.NET Framework debugging]
- ICorDebugMDA::GetDescription method [.NET Framework debugging]
ms.assetid: 01d1b481-ca67-4712-8744-d342ec0df639
topic_type:
- apiref
ms.openlocfilehash: 522e992e6d7e9a64f7590bbec0e9106e0e1f8f47
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212139"
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="6e3fa-102">Metodo ICorDebugMDA::GetDescription</span><span class="sxs-lookup"><span data-stu-id="6e3fa-102">ICorDebugMDA::GetDescription Method</span></span>
<span data-ttu-id="6e3fa-103">Ottiene una stringa contenente la descrizione dell'assistente al debug gestito (MDA) rappresentato da [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6e3fa-103">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e3fa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e3fa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e3fa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6e3fa-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="6e3fa-106">in Dimensioni del buffer di stringa in cui viene archiviata la descrizione.</span><span class="sxs-lookup"><span data-stu-id="6e3fa-106">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="6e3fa-107">out Puntatore al numero di byte restituiti nel buffer di stringa.</span><span class="sxs-lookup"><span data-stu-id="6e3fa-107">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="6e3fa-108">out Buffer di stringa contenente la descrizione dell'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="6e3fa-108">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e3fa-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6e3fa-109">Remarks</span></span>  
 <span data-ttu-id="6e3fa-110">La stringa può essere di lunghezza zero.</span><span class="sxs-lookup"><span data-stu-id="6e3fa-110">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e3fa-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6e3fa-111">Requirements</span></span>  
 <span data-ttu-id="6e3fa-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e3fa-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e3fa-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e3fa-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e3fa-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e3fa-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e3fa-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e3fa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e3fa-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e3fa-116">See also</span></span>

- [<span data-ttu-id="6e3fa-117">Interfaccia ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="6e3fa-117">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="6e3fa-118">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="6e3fa-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
