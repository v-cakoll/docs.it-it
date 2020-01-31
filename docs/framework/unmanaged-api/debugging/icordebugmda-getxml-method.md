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
ms.openlocfilehash: cd1882bdfca1258889514a041726a59435e126b8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793210"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="84c59-102">Metodo ICorDebugMDA::GetXML</span><span class="sxs-lookup"><span data-stu-id="84c59-102">ICorDebugMDA::GetXML Method</span></span>
<span data-ttu-id="84c59-103">Ottiene il flusso XML completo associato all'assistente al debug gestito (MDA) rappresentato da [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="84c59-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84c59-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84c59-104">Syntax</span></span>  
  
```cpp  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84c59-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="84c59-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="84c59-106">[in] Dimensione della matrice `szName`.</span><span class="sxs-lookup"><span data-stu-id="84c59-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="84c59-107">out Puntatore alla lunghezza del flusso XML.</span><span class="sxs-lookup"><span data-stu-id="84c59-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="84c59-108">out Matrice in cui archiviare il flusso XML.</span><span class="sxs-lookup"><span data-stu-id="84c59-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="84c59-109">La matrice può essere vuota.</span><span class="sxs-lookup"><span data-stu-id="84c59-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84c59-110">Note</span><span class="sxs-lookup"><span data-stu-id="84c59-110">Remarks</span></span>  
 <span data-ttu-id="84c59-111">Il metodo `GetXML` può potenzialmente influire sulle prestazioni, a seconda delle dimensioni del flusso XML associato.</span><span class="sxs-lookup"><span data-stu-id="84c59-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84c59-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="84c59-112">Requirements</span></span>  
 <span data-ttu-id="84c59-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84c59-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84c59-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84c59-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84c59-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84c59-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84c59-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84c59-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84c59-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84c59-117">See also</span></span>

- [<span data-ttu-id="84c59-118">Interfaccia ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="84c59-118">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="84c59-119">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="84c59-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
