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
ms.openlocfilehash: d2d16ab0a29fadd3a64d906a64fc46c422e01c45
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610041"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="09554-102">Metodo ISymUnmanagedWriter::OpenMethod</span><span class="sxs-lookup"><span data-stu-id="09554-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="09554-103">Apre un metodo in cui vengono emesse le informazioni sui simboli.</span><span class="sxs-lookup"><span data-stu-id="09554-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="09554-104">Il metodo specificato diventa il metodo corrente per le chiamate a per definire i punti di sequenza, i parametri e gli ambiti lessicali.</span><span class="sxs-lookup"><span data-stu-id="09554-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="09554-105">È presente un ambito lessicale implicito intorno all'intero metodo.</span><span class="sxs-lookup"><span data-stu-id="09554-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="09554-106">La riapertura di un metodo precedentemente chiuso Cancella tutti i simboli definiti in precedenza per il metodo.</span><span class="sxs-lookup"><span data-stu-id="09554-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="09554-107">Può essere presente un solo metodo Open alla volta.</span><span class="sxs-lookup"><span data-stu-id="09554-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09554-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09554-108">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09554-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="09554-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="09554-110">in Token di metadati per il metodo da aprire.</span><span class="sxs-lookup"><span data-stu-id="09554-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09554-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="09554-111">Return Value</span></span>  
 <span data-ttu-id="09554-112">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="09554-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09554-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="09554-113">Requirements</span></span>  
 <span data-ttu-id="09554-114">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="09554-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09554-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09554-115">See also</span></span>

- [<span data-ttu-id="09554-116">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="09554-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="09554-117">Metodo CloseMethod</span><span class="sxs-lookup"><span data-stu-id="09554-117">CloseMethod Method</span></span>](isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="09554-118">Metodo OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="09554-118">OpenMethod2 Method</span></span>](isymunmanagedwriter3-openmethod2-method.md)
