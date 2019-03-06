---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bac541909e07aadff06006fba8c3cfcf4dc5465
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486225"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="c9466-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="c9466-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="c9466-103">Definire un gruppo di async await operazioni nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="c9466-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="c9466-104">Istruzione di restituzione di un await, che identifica un potenziale rendimento corrisponde a ogni offset yield.</span><span class="sxs-lookup"><span data-stu-id="c9466-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="c9466-105">Ciascuna `breakpointMethod` / `breakpointOffset` coppia indica dove l'operazione asincrona riprenderà a cui potrebbe trovarsi in un altro metodo.</span><span class="sxs-lookup"><span data-stu-id="c9466-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9466-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9466-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9466-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="c9466-107">Parameters</span></span>  
  
|<span data-ttu-id="c9466-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="c9466-108">Parameter</span></span>|<span data-ttu-id="c9466-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9466-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="c9466-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c9466-110">Return Value</span></span>  
 <span data-ttu-id="c9466-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="c9466-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9466-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c9466-112">Requirements</span></span>  
 <span data-ttu-id="c9466-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c9466-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9466-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9466-114">See also</span></span>
- [<span data-ttu-id="c9466-115">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="c9466-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
