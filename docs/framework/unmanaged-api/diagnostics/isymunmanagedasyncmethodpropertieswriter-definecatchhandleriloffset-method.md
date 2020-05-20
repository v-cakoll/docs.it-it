---
title: Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
ms.openlocfilehash: 58dde2fcce3f4bf578907171e5b575c30c678cfc
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441773"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="288b9-102">Metodo ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="288b9-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="288b9-103">Imposta l'offset il per il gestore catch generato dal compilatore che esegue il wrapping di un metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="288b9-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="288b9-104">L'offset il dell'operazione catch generata viene utilizzato dal debugger per gestire l'oggetto Catch come se fosse un codice non utente, anche se potrebbe verificarsi in un metodo del codice utente.</span><span class="sxs-lookup"><span data-stu-id="288b9-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="288b9-105">In particolare, viene usato in risposta a un evento di eccezione **CatchHandlerFound** .</span><span class="sxs-lookup"><span data-stu-id="288b9-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="288b9-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="288b9-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="288b9-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="288b9-107">Parameters</span></span>  
  
|<span data-ttu-id="288b9-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="288b9-108">Parameter</span></span>|<span data-ttu-id="288b9-109">Description</span><span class="sxs-lookup"><span data-stu-id="288b9-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="288b9-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="288b9-110">Return Value</span></span>  
 <span data-ttu-id="288b9-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="288b9-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="288b9-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="288b9-112">Requirements</span></span>  
 <span data-ttu-id="288b9-113">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="288b9-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="288b9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="288b9-114">See also</span></span>

- [<span data-ttu-id="288b9-115">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="288b9-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
