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
ms.openlocfilehash: 2e305ca13e419a40e9838a46a61fe7a435b7ce56
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="15e81-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="15e81-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="15e81-103">Definire un gruppo di async await operazioni nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="15e81-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="15e81-104">Istruzione return di un await, che identifica un potenziale rendimento corrisponde a ogni offset yield.</span><span class="sxs-lookup"><span data-stu-id="15e81-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="15e81-105">Ogni `breakpointMethod` / `breakpointOffset` coppia indica dove verrà ripreso l'operazione asincrona, (che può essere un altro metodo.</span><span class="sxs-lookup"><span data-stu-id="15e81-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume,(which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15e81-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="15e81-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15e81-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="15e81-107">Parameters</span></span>  
  
|<span data-ttu-id="15e81-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="15e81-108">Parameter</span></span>|<span data-ttu-id="15e81-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15e81-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="15e81-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="15e81-110">Return Value</span></span>  
 <span data-ttu-id="15e81-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="15e81-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15e81-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="15e81-112">Requirements</span></span>  
 <span data-ttu-id="15e81-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="15e81-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15e81-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15e81-114">See Also</span></span>  
 [<span data-ttu-id="15e81-115">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="15e81-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
