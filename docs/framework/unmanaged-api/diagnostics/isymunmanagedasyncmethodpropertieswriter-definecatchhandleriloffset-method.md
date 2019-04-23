---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 923c85a9dff11753a338fcfd3673d3590fca607a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196749"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="17762-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="17762-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="17762-103">Imposta l'offset per il gestore catch generato dal compilatore che esegue il wrapping di un metodo asincrono IL.</span><span class="sxs-lookup"><span data-stu-id="17762-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="17762-104">L'offset IL di catch generato viene utilizzato dal debugger per gestire la cattura come se fossero codice non utente anche se potrebbe verificarsi in un metodo del codice utente.</span><span class="sxs-lookup"><span data-stu-id="17762-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="17762-105">In particolare, viene usato in risposta a un **CatchHandlerFound** evento dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="17762-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17762-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17762-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17762-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="17762-107">Parameters</span></span>  
  
|<span data-ttu-id="17762-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="17762-108">Parameter</span></span>|<span data-ttu-id="17762-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="17762-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="17762-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="17762-110">Return Value</span></span>  
 <span data-ttu-id="17762-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="17762-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17762-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17762-112">Requirements</span></span>  
 <span data-ttu-id="17762-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="17762-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17762-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17762-114">See also</span></span>

- [<span data-ttu-id="17762-115">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="17762-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
