---
title: Metodo IDebugAutoAttach::AutoAttach
ms.date: 03/30/2017
api_name:
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b45b5e1a7589329b788160df3ac4493efa48197
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663518"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="d6aa2-102">Metodo IDebugAutoAttach::AutoAttach</span><span class="sxs-lookup"><span data-stu-id="d6aa2-102">IDebugAutoAttach::AutoAttach Method</span></span>
<span data-ttu-id="d6aa2-103">Esegue automaticamente richiamato server debugger collegare.</span><span class="sxs-lookup"><span data-stu-id="d6aa2-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6aa2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6aa2-104">Syntax</span></span>  
  
```  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6aa2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d6aa2-105">Parameters</span></span>  
 `guidPort`  
 <span data-ttu-id="d6aa2-106">[in] Sempre impostato su `GUID_NULL`.</span><span class="sxs-lookup"><span data-stu-id="d6aa2-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="d6aa2-107">[in] ID processo, in genere recuperato con il `GetCurrentProcessId` (funzione).</span><span class="sxs-lookup"><span data-stu-id="d6aa2-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="d6aa2-108">[in] Tipo di programma: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, o `AUTOATTACH_PROGRAM_UNKNOWN`.</span><span class="sxs-lookup"><span data-stu-id="d6aa2-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="d6aa2-109">[in] ID programma.</span><span class="sxs-lookup"><span data-stu-id="d6aa2-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="d6aa2-110">[in] Stringa passata per il verbo debug.</span><span class="sxs-lookup"><span data-stu-id="d6aa2-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6aa2-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d6aa2-111">Return Value</span></span>  
 <span data-ttu-id="d6aa2-112">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d6aa2-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6aa2-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d6aa2-113">Requirements</span></span>  
 <span data-ttu-id="d6aa2-114">**Intestazione:** DbgAutoAttach.h</span><span class="sxs-lookup"><span data-stu-id="d6aa2-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6aa2-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6aa2-115">See also</span></span>
- [<span data-ttu-id="d6aa2-116">Interfaccia IDebugAutoAttach</span><span class="sxs-lookup"><span data-stu-id="d6aa2-116">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)
