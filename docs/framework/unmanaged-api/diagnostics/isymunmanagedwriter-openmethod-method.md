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
ms.openlocfilehash: 7b13ca9884516e95e0bb922efc5bc1a845344e38
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427925"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="ec780-102">Metodo ISymUnmanagedWriter::OpenMethod</span><span class="sxs-lookup"><span data-stu-id="ec780-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="ec780-103">Apre un metodo in cui vengono emesse le informazioni sui simboli.</span><span class="sxs-lookup"><span data-stu-id="ec780-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="ec780-104">Il metodo specificato diventa il metodo corrente per le chiamate a per definire i punti di sequenza, i parametri e gli ambiti lessicali.</span><span class="sxs-lookup"><span data-stu-id="ec780-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="ec780-105">È presente un ambito lessicale implicito intorno all'intero metodo.</span><span class="sxs-lookup"><span data-stu-id="ec780-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="ec780-106">La riapertura di un metodo precedentemente chiuso Cancella tutti i simboli definiti in precedenza per il metodo.</span><span class="sxs-lookup"><span data-stu-id="ec780-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="ec780-107">Può essere presente un solo metodo Open alla volta.</span><span class="sxs-lookup"><span data-stu-id="ec780-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec780-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec780-108">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec780-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="ec780-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="ec780-110">in Token di metadati per il metodo da aprire.</span><span class="sxs-lookup"><span data-stu-id="ec780-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec780-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ec780-111">Return Value</span></span>  
 <span data-ttu-id="ec780-112">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="ec780-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec780-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ec780-113">Requirements</span></span>  
 <span data-ttu-id="ec780-114">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ec780-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec780-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec780-115">See also</span></span>

- [<span data-ttu-id="ec780-116">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="ec780-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="ec780-117">Metodo CloseMethod</span><span class="sxs-lookup"><span data-stu-id="ec780-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="ec780-118">Metodo OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="ec780-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
