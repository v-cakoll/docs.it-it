---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d000e61736f3250c677014cce50a2b7dcdecf1b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491687"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="331ea-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="331ea-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="331ea-103">Imposta l'offset per il gestore catch generato dal compilatore che esegue il wrapping di un metodo asincrono IL.</span><span class="sxs-lookup"><span data-stu-id="331ea-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="331ea-104">L'offset IL di catch generato viene utilizzato dal debugger per gestire la cattura come se fossero codice non utente anche se potrebbe verificarsi in un metodo del codice utente.</span><span class="sxs-lookup"><span data-stu-id="331ea-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="331ea-105">In particolare, viene usato in risposta a un **CatchHandlerFound** evento dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="331ea-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="331ea-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="331ea-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="331ea-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="331ea-107">Parameters</span></span>  
  
|<span data-ttu-id="331ea-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="331ea-108">Parameter</span></span>|<span data-ttu-id="331ea-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="331ea-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="331ea-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="331ea-110">Return Value</span></span>  
 <span data-ttu-id="331ea-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="331ea-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="331ea-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="331ea-112">Requirements</span></span>  
 <span data-ttu-id="331ea-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="331ea-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="331ea-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="331ea-114">See also</span></span>
- [<span data-ttu-id="331ea-115">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="331ea-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
