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
ms.openlocfilehash: ab248c6a624fbed1a6783383566be093c449ff97
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609885"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="8aeab-102">Metodo ISymUnmanagedWriter::OpenNamespace</span><span class="sxs-lookup"><span data-stu-id="8aeab-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="8aeab-103">Apre un nuovo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8aeab-103">Opens a new namespace.</span></span> <span data-ttu-id="8aeab-104">Chiamare questo metodo prima di definire metodi o variabili che occupano uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8aeab-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="8aeab-105">Gli spazi dei nomi possono essere annidati.</span><span class="sxs-lookup"><span data-stu-id="8aeab-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aeab-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8aeab-106">Syntax</span></span>  
  
```cpp  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8aeab-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="8aeab-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="8aeab-108">in Puntatore al nome del nuovo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8aeab-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8aeab-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8aeab-109">Return Value</span></span>  
 <span data-ttu-id="8aeab-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="8aeab-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8aeab-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8aeab-111">Requirements</span></span>  
 <span data-ttu-id="8aeab-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8aeab-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aeab-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8aeab-113">See also</span></span>

- [<span data-ttu-id="8aeab-114">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="8aeab-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="8aeab-115">Metodo CloseNamespace</span><span class="sxs-lookup"><span data-stu-id="8aeab-115">CloseNamespace Method</span></span>](isymunmanagedwriter-closenamespace-method.md)
