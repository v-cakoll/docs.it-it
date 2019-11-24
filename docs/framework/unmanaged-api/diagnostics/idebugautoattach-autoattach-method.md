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
ms.openlocfilehash: 766aeb31436101babeab31b615a1c633578bfcc5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445519"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="3eadd-102">Metodo IDebugAutoAttach::AutoAttach</span><span class="sxs-lookup"><span data-stu-id="3eadd-102">IDebugAutoAttach::AutoAttach Method</span></span>
<span data-ttu-id="3eadd-103">Performs server-invoked debugger auto attach.</span><span class="sxs-lookup"><span data-stu-id="3eadd-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eadd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3eadd-104">Syntax</span></span>  
  
```cpp  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3eadd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3eadd-105">Parameters</span></span>  
 `guidPort`  
 <span data-ttu-id="3eadd-106">[in] Always set to `GUID_NULL`.</span><span class="sxs-lookup"><span data-stu-id="3eadd-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="3eadd-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span><span class="sxs-lookup"><span data-stu-id="3eadd-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="3eadd-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span><span class="sxs-lookup"><span data-stu-id="3eadd-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="3eadd-109">[in] Program ID.</span><span class="sxs-lookup"><span data-stu-id="3eadd-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="3eadd-110">[in] String passed by the debug verb.</span><span class="sxs-lookup"><span data-stu-id="3eadd-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3eadd-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3eadd-111">Return Value</span></span>  
 <span data-ttu-id="3eadd-112">S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="3eadd-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eadd-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3eadd-113">Requirements</span></span>  
 <span data-ttu-id="3eadd-114">**Header:** DbgAutoAttach.h</span><span class="sxs-lookup"><span data-stu-id="3eadd-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eadd-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3eadd-115">See also</span></span>

- [<span data-ttu-id="3eadd-116">Interfaccia IDebugAutoAttach</span><span class="sxs-lookup"><span data-stu-id="3eadd-116">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)
