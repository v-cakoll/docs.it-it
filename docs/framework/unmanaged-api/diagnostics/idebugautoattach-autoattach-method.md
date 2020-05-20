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
ms.openlocfilehash: aae03b0dc76639c50f4615d41eef73990226b5f7
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442124"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="a43d8-102">Metodo IDebugAutoAttach::AutoAttach</span><span class="sxs-lookup"><span data-stu-id="a43d8-102">IDebugAutoAttach::AutoAttach Method</span></span>
<span data-ttu-id="a43d8-103">Esegue la connessione automatica al debugger richiamato dal server.</span><span class="sxs-lookup"><span data-stu-id="a43d8-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a43d8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a43d8-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="a43d8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a43d8-105">Parameters</span></span>  
 `guidPort`  
 <span data-ttu-id="a43d8-106">in Sempre impostato su `GUID_NULL` .</span><span class="sxs-lookup"><span data-stu-id="a43d8-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="a43d8-107">in ID processo, normalmente recuperato con la `GetCurrentProcessId` funzione.</span><span class="sxs-lookup"><span data-stu-id="a43d8-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="a43d8-108">in Tipo di programma: `AUTOATTACH_PROGRAM_WIN32` , `AUTOATTACH_PROGRAM_COMPLUS` o `AUTOATTACH_PROGRAM_UNKNOWN` .</span><span class="sxs-lookup"><span data-stu-id="a43d8-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="a43d8-109">in ID programma.</span><span class="sxs-lookup"><span data-stu-id="a43d8-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="a43d8-110">in Stringa passata dal verbo di debug.</span><span class="sxs-lookup"><span data-stu-id="a43d8-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a43d8-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a43d8-111">Return Value</span></span>  
 <span data-ttu-id="a43d8-112">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a43d8-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a43d8-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a43d8-113">Requirements</span></span>  
 <span data-ttu-id="a43d8-114">**Intestazione:** DbgAutoAttach. h</span><span class="sxs-lookup"><span data-stu-id="a43d8-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a43d8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a43d8-115">See also</span></span>

- [<span data-ttu-id="a43d8-116">Interfaccia IDebugAutoAttach</span><span class="sxs-lookup"><span data-stu-id="a43d8-116">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)
