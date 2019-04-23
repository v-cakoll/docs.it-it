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
ms.openlocfilehash: b05ba185a9ad4ab076d29d7d609734d41677b760
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194786"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="150df-102">Metodo ISymUnmanagedWriter::OpenMethod</span><span class="sxs-lookup"><span data-stu-id="150df-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="150df-103">Apre un metodo nel quale simbolo vengono create le informazioni.</span><span class="sxs-lookup"><span data-stu-id="150df-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="150df-104">Il metodo specificato diventa il metodo corrente per le chiamate definire punti di sequenza, parametri e gli ambiti lessicali.</span><span class="sxs-lookup"><span data-stu-id="150df-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="150df-105">È un ambito lessicale implicito l'intero metodo.</span><span class="sxs-lookup"><span data-stu-id="150df-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="150df-106">La riapertura di un metodo che era stato precedentemente chiuso Cancella qualsiasi simboli definiti in precedenza per tale metodo.</span><span class="sxs-lookup"><span data-stu-id="150df-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="150df-107">Può esistere un solo metodo open alla volta.</span><span class="sxs-lookup"><span data-stu-id="150df-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="150df-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="150df-108">Syntax</span></span>  
  
```  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a><span data-ttu-id="150df-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="150df-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="150df-110">[in] Il token di metadati per il metodo da aprire.</span><span class="sxs-lookup"><span data-stu-id="150df-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="150df-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="150df-111">Return Value</span></span>  
 <span data-ttu-id="150df-112">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="150df-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="150df-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="150df-113">Requirements</span></span>  
 <span data-ttu-id="150df-114">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="150df-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="150df-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="150df-115">See also</span></span>

- [<span data-ttu-id="150df-116">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="150df-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="150df-117">Metodo CloseMethod</span><span class="sxs-lookup"><span data-stu-id="150df-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="150df-118">Metodo OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="150df-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
