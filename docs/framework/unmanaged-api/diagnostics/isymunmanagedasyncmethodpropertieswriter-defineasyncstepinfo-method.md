---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b165501b3e090cf309f3b4053649644b87b47f22
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555570"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="9a66d-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="9a66d-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="9a66d-103">Definire un gruppo di async await operazioni nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="9a66d-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="9a66d-104">Istruzione di restituzione di un await, che identifica un potenziale rendimento corrisponde a ogni offset yield.</span><span class="sxs-lookup"><span data-stu-id="9a66d-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="9a66d-105">Ciascuna `breakpointMethod` / `breakpointOffset` coppia per indicare dove verrà ripresa dell'operazione asincrona, (che può essere un altro metodo.</span><span class="sxs-lookup"><span data-stu-id="9a66d-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume,(which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a66d-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a66d-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a66d-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a66d-107">Parameters</span></span>  
  
|<span data-ttu-id="9a66d-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="9a66d-108">Parameter</span></span>|<span data-ttu-id="9a66d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a66d-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="9a66d-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9a66d-110">Return Value</span></span>  
 <span data-ttu-id="9a66d-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="9a66d-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a66d-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a66d-112">Requirements</span></span>  
 <span data-ttu-id="9a66d-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9a66d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a66d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a66d-114">See also</span></span>
- [<span data-ttu-id="9a66d-115">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="9a66d-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
