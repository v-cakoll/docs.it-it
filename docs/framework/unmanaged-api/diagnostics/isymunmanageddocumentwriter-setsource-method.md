---
title: Metodo ISymUnmanagedDocumentWriter::SetSource
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetSource
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetSource method [.NET Framework debugging]
- SetSource method [.NET Framework debugging]
ms.assetid: ea5b9d9f-ff06-4bd3-8de5-6435343aba59
topic_type:
- apiref
ms.openlocfilehash: 06c6f9b05d34ea98dde437393ded289cbab2f61d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615527"
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="26000-102">Metodo ISymUnmanagedDocumentWriter::SetSource</span><span class="sxs-lookup"><span data-stu-id="26000-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>
<span data-ttu-id="26000-103">Imposta l'origine incorporata per un documento in corso di scrittura.</span><span class="sxs-lookup"><span data-stu-id="26000-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26000-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26000-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26000-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="26000-105">Parameters</span></span>  
 `sourceSize`  
 <span data-ttu-id="26000-106">in Oggetto `ULONG32` che contiene la dimensione del `source` buffer.</span><span class="sxs-lookup"><span data-stu-id="26000-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="26000-107">in Buffer in cui è archiviata l'origine incorporata.</span><span class="sxs-lookup"><span data-stu-id="26000-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26000-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="26000-108">Return Value</span></span>  
 <span data-ttu-id="26000-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="26000-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26000-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="26000-110">Requirements</span></span>  
 <span data-ttu-id="26000-111">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="26000-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26000-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26000-112">See also</span></span>

- [<span data-ttu-id="26000-113">Interfaccia ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="26000-113">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)
