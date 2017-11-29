---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3bae0e2dfb56883a674b282acd385ba45a25bebb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="c0ad8-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="c0ad8-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="c0ad8-103">Imposta l'offset per il gestore catch generato dal compilatore che esegue il wrapping di un metodo asincrono IL.</span><span class="sxs-lookup"><span data-stu-id="c0ad8-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="c0ad8-104">Offset IL di catch generato viene utilizzata dal debugger per gestire catch come se si trattasse di codice non utente, anche se potrebbe verificarsi in un metodo del codice utente.</span><span class="sxs-lookup"><span data-stu-id="c0ad8-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="c0ad8-105">In particolare, viene utilizzato in risposta a un **CatchHandlerFound** evento dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c0ad8-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0ad8-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c0ad8-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0ad8-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="c0ad8-107">Parameters</span></span>  
  
|<span data-ttu-id="c0ad8-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="c0ad8-108">Parameter</span></span>|<span data-ttu-id="c0ad8-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0ad8-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="c0ad8-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c0ad8-110">Return Value</span></span>  
 <span data-ttu-id="c0ad8-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="c0ad8-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0ad8-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c0ad8-112">Requirements</span></span>  
 <span data-ttu-id="c0ad8-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c0ad8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ad8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0ad8-114">See Also</span></span>  
 [<span data-ttu-id="c0ad8-115">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="c0ad8-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
