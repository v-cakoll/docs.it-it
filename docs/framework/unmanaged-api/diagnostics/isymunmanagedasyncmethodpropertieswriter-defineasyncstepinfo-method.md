---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c33403c48e6f395d8d0e10c7fddcea327d87529a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="1ef79-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="1ef79-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="1ef79-103">Definire un gruppo di async await operazioni nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="1ef79-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="1ef79-104">Istruzione return di un await, che identifica un potenziale rendimento corrisponde a ogni offset yield.</span><span class="sxs-lookup"><span data-stu-id="1ef79-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="1ef79-105">Ogni `breakpointMethod` / `breakpointOffset` coppia indica dove verrà ripreso l'operazione asincrona, (che può essere un altro metodo.</span><span class="sxs-lookup"><span data-stu-id="1ef79-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume,(which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ef79-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1ef79-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1ef79-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="1ef79-107">Parameters</span></span>  
  
|<span data-ttu-id="1ef79-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="1ef79-108">Parameter</span></span>|<span data-ttu-id="1ef79-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ef79-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="1ef79-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1ef79-110">Return Value</span></span>  
 <span data-ttu-id="1ef79-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="1ef79-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ef79-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1ef79-112">Requirements</span></span>  
 <span data-ttu-id="1ef79-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1ef79-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ef79-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ef79-114">See Also</span></span>  
 [<span data-ttu-id="1ef79-115">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="1ef79-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
