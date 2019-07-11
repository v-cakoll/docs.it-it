---
title: Metodo ICorDebugMDA::GetXML
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetXML
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 003a6546b3316f2a2a65bce4537c60dcf62b3197
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752856"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="1caa2-102">Metodo ICorDebugMDA::GetXML</span><span class="sxs-lookup"><span data-stu-id="1caa2-102">ICorDebugMDA::GetXML Method</span></span>
<span data-ttu-id="1caa2-103">Ottiene il flusso XML completo associato con l'assistente al debug gestito (MDA) rappresentato da [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="1caa2-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1caa2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1caa2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1caa2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1caa2-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="1caa2-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="1caa2-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="1caa2-107">[out] Puntatore alla lunghezza del flusso XML.</span><span class="sxs-lookup"><span data-stu-id="1caa2-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="1caa2-108">[out] Matrice in cui archiviare il flusso XML.</span><span class="sxs-lookup"><span data-stu-id="1caa2-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="1caa2-109">La matrice può essere vuota.</span><span class="sxs-lookup"><span data-stu-id="1caa2-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1caa2-110">Note</span><span class="sxs-lookup"><span data-stu-id="1caa2-110">Remarks</span></span>  
 <span data-ttu-id="1caa2-111">Il `GetXML` metodo potenzialmente influire sulle prestazioni, a seconda delle dimensioni del flusso XML associato.</span><span class="sxs-lookup"><span data-stu-id="1caa2-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1caa2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1caa2-112">Requirements</span></span>  
 <span data-ttu-id="1caa2-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1caa2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1caa2-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1caa2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1caa2-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1caa2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1caa2-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1caa2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1caa2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1caa2-117">See also</span></span>

- [<span data-ttu-id="1caa2-118">Interfaccia ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="1caa2-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="1caa2-119">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="1caa2-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
