---
title: Metodo ISymUnmanagedWriter::OpenMethod
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.OpenMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 61d63fb96635e34e07c3997c1aad838e67c70742
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="f7846-102">Metodo ISymUnmanagedWriter::OpenMethod</span><span class="sxs-lookup"><span data-stu-id="f7846-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="f7846-103">Apre un metodo nel quale simbolo vengono create le informazioni.</span><span class="sxs-lookup"><span data-stu-id="f7846-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="f7846-104">Il metodo specificato diventa il metodo corrente per le chiamate definire punti di sequenza, parametri e gli ambiti lessicali.</span><span class="sxs-lookup"><span data-stu-id="f7846-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="f7846-105">È un ambito lessicale implicito l'intero metodo.</span><span class="sxs-lookup"><span data-stu-id="f7846-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="f7846-106">Riaprire un metodo che è stata chiusa in precedenza verranno cancellati i simboli definiti in precedenza per tale metodo.</span><span class="sxs-lookup"><span data-stu-id="f7846-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="f7846-107">Può esistere un solo metodo aperto alla volta.</span><span class="sxs-lookup"><span data-stu-id="f7846-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7846-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7846-108">Syntax</span></span>  
  
```  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7846-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="f7846-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="f7846-110">[in] Il token di metadati per il metodo da aprire.</span><span class="sxs-lookup"><span data-stu-id="f7846-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7846-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f7846-111">Return Value</span></span>  
 <span data-ttu-id="f7846-112">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="f7846-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7846-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7846-113">Requirements</span></span>  
 <span data-ttu-id="f7846-114">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f7846-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7846-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7846-115">See Also</span></span>  
 [<span data-ttu-id="f7846-116">ISymUnmanagedWriter (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f7846-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="f7846-117">CloseMethod (metodo)</span><span class="sxs-lookup"><span data-stu-id="f7846-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)  
 [<span data-ttu-id="f7846-118">OpenMethod2 (metodo)</span><span class="sxs-lookup"><span data-stu-id="f7846-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
