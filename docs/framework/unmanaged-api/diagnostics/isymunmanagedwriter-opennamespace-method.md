---
title: Metodo ISymUnmanagedWriter::OpenNamespace
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1585acce8bba0dff327c961f5e32ef6b46794401
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986024"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="95eca-102">Metodo ISymUnmanagedWriter::OpenNamespace</span><span class="sxs-lookup"><span data-stu-id="95eca-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="95eca-103">Apre un nuovo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="95eca-103">Opens a new namespace.</span></span> <span data-ttu-id="95eca-104">Chiamare questo metodo prima di definire i metodi o le variabili che occupano uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="95eca-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="95eca-105">Gli spazi dei nomi possono essere annidate.</span><span class="sxs-lookup"><span data-stu-id="95eca-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95eca-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95eca-106">Syntax</span></span>  
  
```  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95eca-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="95eca-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="95eca-108">[in] Puntatore al nome del nuovo spazio dei nomi specificato.</span><span class="sxs-lookup"><span data-stu-id="95eca-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95eca-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="95eca-109">Return Value</span></span>  
 <span data-ttu-id="95eca-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="95eca-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95eca-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95eca-111">Requirements</span></span>  
 <span data-ttu-id="95eca-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="95eca-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95eca-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95eca-113">See also</span></span>

- [<span data-ttu-id="95eca-114">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="95eca-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="95eca-115">Metodo CloseNamespace</span><span class="sxs-lookup"><span data-stu-id="95eca-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
