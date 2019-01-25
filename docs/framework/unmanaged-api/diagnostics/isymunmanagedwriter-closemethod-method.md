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
ms.openlocfilehash: a6f8c8b522aabfce3b83b6b624bd0ca9757448ad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666020"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="f43bb-102">Metodo ISymUnmanagedWriter::CloseMethod</span><span class="sxs-lookup"><span data-stu-id="f43bb-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="f43bb-103">Chiude il metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="f43bb-103">Closes the current method.</span></span> <span data-ttu-id="f43bb-104">Dopo che un metodo è stato chiuso, altri simboli non possono essere definiti all'interno di esso.</span><span class="sxs-lookup"><span data-stu-id="f43bb-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f43bb-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f43bb-105">Syntax</span></span>  
  
```  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f43bb-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f43bb-106">Return Value</span></span>  
 <span data-ttu-id="f43bb-107">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="f43bb-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f43bb-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f43bb-108">Requirements</span></span>  
 <span data-ttu-id="f43bb-109">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f43bb-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f43bb-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f43bb-110">See also</span></span>
- [<span data-ttu-id="f43bb-111">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="f43bb-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="f43bb-112">Metodo OpenMethod</span><span class="sxs-lookup"><span data-stu-id="f43bb-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
