---
title: Metodo ISymUnmanagedWriter::Close
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Close
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type:
- apiref
ms.openlocfilehash: 0a7ecd475a8031fedb2c8474593b45045fcc6fb9
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610132"
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="eaa6c-102">Metodo ISymUnmanagedWriter::Close</span><span class="sxs-lookup"><span data-stu-id="eaa6c-102">ISymUnmanagedWriter::Close Method</span></span>
<span data-ttu-id="eaa6c-103">Chiude il writer di simboli dopo aver eseguito il commit dei simboli nell'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="eaa6c-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaa6c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eaa6c-104">Syntax</span></span>  
  
```cpp  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="eaa6c-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="eaa6c-105">Return Value</span></span>  
 <span data-ttu-id="eaa6c-106">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="eaa6c-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eaa6c-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="eaa6c-107">Remarks</span></span>  
 <span data-ttu-id="eaa6c-108">Dopo questa chiamata, il writer di simboli diventa non valido per ulteriori aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="eaa6c-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="eaa6c-109">Per chiudere il writer di simboli senza eseguire il commit dei simboli, usare invece il metodo [ISymUnmanagedWriter:: Abort](isymunmanagedwriter-abort-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eaa6c-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaa6c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eaa6c-110">Requirements</span></span>  
 <span data-ttu-id="eaa6c-111">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="eaa6c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaa6c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eaa6c-112">See also</span></span>

- [<span data-ttu-id="eaa6c-113">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="eaa6c-113">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
