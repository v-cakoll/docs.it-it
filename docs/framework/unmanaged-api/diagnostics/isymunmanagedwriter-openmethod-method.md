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
ms.openlocfilehash: 1a5e50327e74e0b893bd5f8e6f716827f2168e37
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557955"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="59b34-102">Metodo ISymUnmanagedWriter::OpenMethod</span><span class="sxs-lookup"><span data-stu-id="59b34-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="59b34-103">Apre un metodo nel quale simbolo vengono create le informazioni.</span><span class="sxs-lookup"><span data-stu-id="59b34-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="59b34-104">Il metodo specificato diventa il metodo corrente per le chiamate definire punti di sequenza, parametri e gli ambiti lessicali.</span><span class="sxs-lookup"><span data-stu-id="59b34-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="59b34-105">È un ambito lessicale implicito l'intero metodo.</span><span class="sxs-lookup"><span data-stu-id="59b34-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="59b34-106">La riapertura di un metodo che era stato precedentemente chiuso Cancella qualsiasi simboli definiti in precedenza per tale metodo.</span><span class="sxs-lookup"><span data-stu-id="59b34-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="59b34-107">Può esistere un solo metodo open alla volta.</span><span class="sxs-lookup"><span data-stu-id="59b34-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59b34-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59b34-108">Syntax</span></span>  
  
```  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59b34-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="59b34-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="59b34-110">[in] Il token di metadati per il metodo da aprire.</span><span class="sxs-lookup"><span data-stu-id="59b34-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59b34-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="59b34-111">Return Value</span></span>  
 <span data-ttu-id="59b34-112">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="59b34-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59b34-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="59b34-113">Requirements</span></span>  
 <span data-ttu-id="59b34-114">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="59b34-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59b34-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59b34-115">See also</span></span>
- [<span data-ttu-id="59b34-116">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="59b34-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="59b34-117">Metodo CloseMethod</span><span class="sxs-lookup"><span data-stu-id="59b34-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="59b34-118">Metodo OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="59b34-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
