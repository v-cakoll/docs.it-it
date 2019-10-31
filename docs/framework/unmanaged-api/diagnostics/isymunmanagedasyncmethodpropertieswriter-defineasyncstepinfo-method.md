---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
ms.openlocfilehash: 59e3a95a4d2573263600da60b4f852caa361138e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129202"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="82101-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="82101-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="82101-103">Definire un gruppo di operazioni di attesa asincrone nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="82101-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="82101-104">Ogni offset yield corrisponde a un'istruzione return di await, che identifica un potenziale rendimento.</span><span class="sxs-lookup"><span data-stu-id="82101-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="82101-105">Ogni coppia `breakpointMethod`/`breakpointOffset` indica il punto in cui l'operazione asincrona riprenderà, che potrebbe essere in un metodo diverso.</span><span class="sxs-lookup"><span data-stu-id="82101-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82101-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82101-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82101-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="82101-107">Parameters</span></span>  
  
|<span data-ttu-id="82101-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="82101-108">Parameter</span></span>|<span data-ttu-id="82101-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82101-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="82101-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="82101-110">Return Value</span></span>  
 <span data-ttu-id="82101-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="82101-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82101-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="82101-112">Requirements</span></span>  
 <span data-ttu-id="82101-113">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="82101-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82101-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82101-114">See also</span></span>

- [<span data-ttu-id="82101-115">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="82101-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
