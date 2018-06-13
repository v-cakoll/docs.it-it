---
title: Metodo ICorDebugFrame::GetCode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCode
helpviewer_keywords:
- GetCode method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCode method [.NET Framework debugging]
ms.assetid: fbaa0794-a031-4015-8beb-2749e47ac340
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15206fbd7724383b1ec6df123790d3171e58e9f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411918"
---
# <a name="icordebugframegetcode-method"></a><span data-ttu-id="96de6-102">Metodo ICorDebugFrame::GetCode</span><span class="sxs-lookup"><span data-stu-id="96de6-102">ICorDebugFrame::GetCode Method</span></span>
<span data-ttu-id="96de6-103">Ottiene un puntatore per il codice associato a questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="96de6-103">Gets a pointer to the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96de6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96de6-104">Syntax</span></span>  
  
```  
HRESULT GetCode (  
    [out] ICorDebugCode      **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96de6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="96de6-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="96de6-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugCode che rappresenta il codice associato a questo frame.</span><span class="sxs-lookup"><span data-stu-id="96de6-106">[out] A pointer to the address of an ICorDebugCode object that represents the code associated with this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96de6-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="96de6-107">Requirements</span></span>  
 <span data-ttu-id="96de6-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96de6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96de6-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="96de6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96de6-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="96de6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96de6-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96de6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
