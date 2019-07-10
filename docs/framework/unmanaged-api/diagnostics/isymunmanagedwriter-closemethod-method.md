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
ms.openlocfilehash: 23f77f30b84622dffd8c76bb9302ad564f40ed41
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778180"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="d4b4a-102">Metodo ISymUnmanagedWriter::CloseMethod</span><span class="sxs-lookup"><span data-stu-id="d4b4a-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="d4b4a-103">Chiude il metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="d4b4a-103">Closes the current method.</span></span> <span data-ttu-id="d4b4a-104">Dopo che un metodo è stato chiuso, altri simboli non possono essere definiti all'interno di esso.</span><span class="sxs-lookup"><span data-stu-id="d4b4a-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4b4a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4b4a-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d4b4a-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d4b4a-106">Return Value</span></span>  
 <span data-ttu-id="d4b4a-107">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="d4b4a-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4b4a-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d4b4a-108">Requirements</span></span>  
 <span data-ttu-id="d4b4a-109">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d4b4a-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4b4a-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4b4a-110">See also</span></span>

- [<span data-ttu-id="d4b4a-111">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="d4b4a-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="d4b4a-112">Metodo OpenMethod</span><span class="sxs-lookup"><span data-stu-id="d4b4a-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
