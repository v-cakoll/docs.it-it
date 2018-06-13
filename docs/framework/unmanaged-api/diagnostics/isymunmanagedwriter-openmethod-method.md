---
title: Metodo ISymUnmanagedWriter::OpenMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc41acd6a4f2ef2557d3b39523c5e398c887c454
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427908"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="9b66d-102">Metodo ISymUnmanagedWriter::OpenMethod</span><span class="sxs-lookup"><span data-stu-id="9b66d-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="9b66d-103">Apre un metodo nel quale simbolo vengono create le informazioni.</span><span class="sxs-lookup"><span data-stu-id="9b66d-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="9b66d-104">Il metodo specificato diventa il metodo corrente per le chiamate definire punti di sequenza, parametri e gli ambiti lessicali.</span><span class="sxs-lookup"><span data-stu-id="9b66d-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="9b66d-105">È un ambito lessicale implicito l'intero metodo.</span><span class="sxs-lookup"><span data-stu-id="9b66d-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="9b66d-106">Riaprire un metodo che è stata chiusa in precedenza verranno cancellati i simboli definiti in precedenza per tale metodo.</span><span class="sxs-lookup"><span data-stu-id="9b66d-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="9b66d-107">Può esistere un solo metodo aperto alla volta.</span><span class="sxs-lookup"><span data-stu-id="9b66d-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b66d-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b66d-108">Syntax</span></span>  
  
```  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b66d-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="9b66d-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="9b66d-110">[in] Il token di metadati per il metodo da aprire.</span><span class="sxs-lookup"><span data-stu-id="9b66d-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b66d-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9b66d-111">Return Value</span></span>  
 <span data-ttu-id="9b66d-112">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="9b66d-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b66d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9b66d-113">Requirements</span></span>  
 <span data-ttu-id="9b66d-114">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9b66d-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b66d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b66d-115">See Also</span></span>  
 [<span data-ttu-id="9b66d-116">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="9b66d-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="9b66d-117">Metodo CloseMethod</span><span class="sxs-lookup"><span data-stu-id="9b66d-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)  
 [<span data-ttu-id="9b66d-118">Metodo OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="9b66d-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
