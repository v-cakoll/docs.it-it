---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 923c85a9dff11753a338fcfd3673d3590fca607a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940127"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="95c5f-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="95c5f-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="95c5f-103">Imposta l'offset per il gestore catch generato dal compilatore che esegue il wrapping di un metodo asincrono IL.</span><span class="sxs-lookup"><span data-stu-id="95c5f-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="95c5f-104">L'offset IL di catch generato viene utilizzato dal debugger per gestire la cattura come se fossero codice non utente anche se potrebbe verificarsi in un metodo del codice utente.</span><span class="sxs-lookup"><span data-stu-id="95c5f-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="95c5f-105">In particolare, viene usato in risposta a un **CatchHandlerFound** evento dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="95c5f-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95c5f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95c5f-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95c5f-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="95c5f-107">Parameters</span></span>  
  
|<span data-ttu-id="95c5f-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="95c5f-108">Parameter</span></span>|<span data-ttu-id="95c5f-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95c5f-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="95c5f-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="95c5f-110">Return Value</span></span>  
 <span data-ttu-id="95c5f-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="95c5f-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95c5f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95c5f-112">Requirements</span></span>  
 <span data-ttu-id="95c5f-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="95c5f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95c5f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95c5f-114">See also</span></span>

- [<span data-ttu-id="95c5f-115">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="95c5f-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
