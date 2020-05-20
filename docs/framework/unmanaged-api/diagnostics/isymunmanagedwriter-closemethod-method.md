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
ms.openlocfilehash: fdf24bb8533da7914128f9477987c427442383bb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610119"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="bc93b-102">Metodo ISymUnmanagedWriter::CloseMethod</span><span class="sxs-lookup"><span data-stu-id="bc93b-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="bc93b-103">Chiude il metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="bc93b-103">Closes the current method.</span></span> <span data-ttu-id="bc93b-104">Una volta chiuso un metodo, non è possibile definire altri simboli al suo interno.</span><span class="sxs-lookup"><span data-stu-id="bc93b-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc93b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bc93b-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="bc93b-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bc93b-106">Return Value</span></span>  
 <span data-ttu-id="bc93b-107">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="bc93b-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc93b-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bc93b-108">Requirements</span></span>  
 <span data-ttu-id="bc93b-109">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="bc93b-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc93b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc93b-110">See also</span></span>

- [<span data-ttu-id="bc93b-111">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="bc93b-111">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="bc93b-112">Metodo OpenMethod</span><span class="sxs-lookup"><span data-stu-id="bc93b-112">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)
