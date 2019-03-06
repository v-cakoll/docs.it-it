---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: defd38798453c8b82ec23605d12d41e5b90aaabc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352906"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="ab3ff-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="ab3ff-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="ab3ff-103">Definire un gruppo di async await operazioni nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="ab3ff-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="ab3ff-104">Istruzione di restituzione di un await, che identifica un potenziale rendimento corrisponde a ogni offset yield.</span><span class="sxs-lookup"><span data-stu-id="ab3ff-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="ab3ff-105">Ciascuna `breakpointMethod` / `breakpointOffset` coppia indica dove l'operazione asincrona riprenderà a cui potrebbe trovarsi in un altro metodo.</span><span class="sxs-lookup"><span data-stu-id="ab3ff-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab3ff-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab3ff-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab3ff-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="ab3ff-107">Parameters</span></span>  
  
|<span data-ttu-id="ab3ff-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="ab3ff-108">Parameter</span></span>|<span data-ttu-id="ab3ff-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ab3ff-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="ab3ff-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ab3ff-110">Return Value</span></span>  
 <span data-ttu-id="ab3ff-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="ab3ff-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab3ff-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ab3ff-112">Requirements</span></span>  
 <span data-ttu-id="ab3ff-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ab3ff-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab3ff-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab3ff-114">See also</span></span>
- [<span data-ttu-id="ab3ff-115">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="ab3ff-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
