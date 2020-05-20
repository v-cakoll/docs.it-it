---
title: Metodo ISymUnmanagedScope::GetEndOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
ms.openlocfilehash: 4d6bd239a15bd196f840007af120cb062499f4c9
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614851"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="afbe0-102">Metodo ISymUnmanagedScope::GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="afbe0-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="afbe0-103">Ottiene l'offset finale per questo ambito.</span><span class="sxs-lookup"><span data-stu-id="afbe0-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afbe0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="afbe0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afbe0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="afbe0-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="afbe0-106">out Puntatore a un oggetto `ULONG32` che riceve l'offset finale.</span><span class="sxs-lookup"><span data-stu-id="afbe0-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="afbe0-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="afbe0-107">Return Value</span></span>  
 <span data-ttu-id="afbe0-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="afbe0-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afbe0-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="afbe0-109">Requirements</span></span>  
 <span data-ttu-id="afbe0-110">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="afbe0-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afbe0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afbe0-111">See also</span></span>

- [<span data-ttu-id="afbe0-112">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="afbe0-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="afbe0-113">Metodo GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="afbe0-113">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)
