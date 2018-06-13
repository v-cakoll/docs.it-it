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
ms.openlocfilehash: 71be697a8a1decd9b5f780d047c3dbb397e351d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426889"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="e7c4f-102">Metodo ISymUnmanagedWriter::CloseMethod</span><span class="sxs-lookup"><span data-stu-id="e7c4f-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="e7c4f-103">Chiude il metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="e7c4f-103">Closes the current method.</span></span> <span data-ttu-id="e7c4f-104">Dopo un metodo è stato chiuso, non vi sono ulteriori simboli possono essere definiti all'interno di esso.</span><span class="sxs-lookup"><span data-stu-id="e7c4f-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7c4f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7c4f-105">Syntax</span></span>  
  
```  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e7c4f-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e7c4f-106">Return Value</span></span>  
 <span data-ttu-id="e7c4f-107">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="e7c4f-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7c4f-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e7c4f-108">Requirements</span></span>  
 <span data-ttu-id="e7c4f-109">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e7c4f-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7c4f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7c4f-110">See Also</span></span>  
 [<span data-ttu-id="e7c4f-111">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="e7c4f-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="e7c4f-112">Metodo OpenMethod</span><span class="sxs-lookup"><span data-stu-id="e7c4f-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
