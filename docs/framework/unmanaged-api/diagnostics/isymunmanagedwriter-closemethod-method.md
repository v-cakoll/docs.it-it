---
title: Metodo ISymUnmanagedWriter::CloseMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 591279a80b7d6a770127fb98eb71c056c48bdffd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59231214"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="21e15-102">Metodo ISymUnmanagedWriter::CloseMethod</span><span class="sxs-lookup"><span data-stu-id="21e15-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="21e15-103">Chiude il metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="21e15-103">Closes the current method.</span></span> <span data-ttu-id="21e15-104">Dopo che un metodo è stato chiuso, altri simboli non possono essere definiti all'interno di esso.</span><span class="sxs-lookup"><span data-stu-id="21e15-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21e15-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="21e15-105">Syntax</span></span>  
  
```  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="21e15-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="21e15-106">Return Value</span></span>  
 <span data-ttu-id="21e15-107">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="21e15-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21e15-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="21e15-108">Requirements</span></span>  
 <span data-ttu-id="21e15-109">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="21e15-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21e15-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21e15-110">See also</span></span>

- [<span data-ttu-id="21e15-111">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="21e15-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="21e15-112">Metodo OpenMethod</span><span class="sxs-lookup"><span data-stu-id="21e15-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
