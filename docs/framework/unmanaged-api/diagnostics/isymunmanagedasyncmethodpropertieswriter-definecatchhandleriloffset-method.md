---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce462c4e7e9c8fb11ee74a91f3ece2465a44a834
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425431"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="5dd53-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="5dd53-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="5dd53-103">Imposta l'offset per il gestore catch generato dal compilatore che esegue il wrapping di un metodo asincrono IL.</span><span class="sxs-lookup"><span data-stu-id="5dd53-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="5dd53-104">Offset IL di catch generato viene utilizzata dal debugger per gestire catch come se si trattasse di codice non utente, anche se potrebbe verificarsi in un metodo del codice utente.</span><span class="sxs-lookup"><span data-stu-id="5dd53-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="5dd53-105">In particolare, viene utilizzato in risposta a un **CatchHandlerFound** evento dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5dd53-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dd53-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5dd53-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5dd53-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="5dd53-107">Parameters</span></span>  
  
|<span data-ttu-id="5dd53-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="5dd53-108">Parameter</span></span>|<span data-ttu-id="5dd53-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5dd53-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="5dd53-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5dd53-110">Return Value</span></span>  
 <span data-ttu-id="5dd53-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="5dd53-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dd53-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5dd53-112">Requirements</span></span>  
 <span data-ttu-id="5dd53-113">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5dd53-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dd53-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dd53-114">See Also</span></span>  
 [<span data-ttu-id="5dd53-115">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="5dd53-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
