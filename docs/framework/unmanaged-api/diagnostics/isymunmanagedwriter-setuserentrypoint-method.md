---
title: Metodo ISymUnmanagedWriter::SetUserEntryPoint
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11dc050e2fe16a64db4ac95bb1386e2d90535e81
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895030"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="2701b-102">Metodo ISymUnmanagedWriter::SetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="2701b-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="2701b-103">Specifica il metodo definito dall'utente che rappresenta il punto di ingresso per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="2701b-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="2701b-104">Questo punto di ingresso, ad esempio, potrebbe essere il metodo principale dell'utente anziché gli stub generati dal compilatore prima di Main.</span><span class="sxs-lookup"><span data-stu-id="2701b-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2701b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2701b-105">Syntax</span></span>  
  
```cpp  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2701b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2701b-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="2701b-107">in Token di metadati per il metodo che rappresenta il punto di ingresso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2701b-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2701b-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2701b-108">Return Value</span></span>  
 <span data-ttu-id="2701b-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="2701b-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2701b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2701b-110">Requirements</span></span>  
 <span data-ttu-id="2701b-111">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="2701b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2701b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2701b-112">See also</span></span>

- [<span data-ttu-id="2701b-113">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="2701b-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
