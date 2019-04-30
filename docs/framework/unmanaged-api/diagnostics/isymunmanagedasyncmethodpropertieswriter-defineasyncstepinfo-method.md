---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8305d0a562fd90e3fae32e372b663ca3942d2a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940140"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="d9248-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="d9248-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="d9248-103">Definire un gruppo di async await operazioni nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="d9248-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="d9248-104">Istruzione di restituzione di un await, che identifica un potenziale rendimento corrisponde a ogni offset yield.</span><span class="sxs-lookup"><span data-stu-id="d9248-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="d9248-105">Ciascuna `breakpointMethod` / `breakpointOffset` coppia indica dove l'operazione asincrona riprenderà a cui potrebbe trovarsi in un altro metodo.</span><span class="sxs-lookup"><span data-stu-id="d9248-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9248-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9248-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9248-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="d9248-107">Parameters</span></span>  
  
|<span data-ttu-id="d9248-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="d9248-108">Parameter</span></span>|<span data-ttu-id="d9248-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9248-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="d9248-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d9248-110">Return Value</span></span>  
 <span data-ttu-id="d9248-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="d9248-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9248-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d9248-112">Requirements</span></span>  
 <span data-ttu-id="d9248-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d9248-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9248-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9248-114">See also</span></span>

- [<span data-ttu-id="d9248-115">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="d9248-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
