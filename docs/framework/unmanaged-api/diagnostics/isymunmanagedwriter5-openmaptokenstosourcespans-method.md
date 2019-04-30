---
title: Metodo ISymUnmanagedWriter5::OpenMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82dc2ced988f7277c994eb9449e7c26efa5450b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61968584"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="3bd0a-102">Metodo ISymUnmanagedWriter5::OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="3bd0a-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="3bd0a-103">Aprire una sezione di dati personalizzati speciali per generare informazioni sul mapping dell'intervallo token-to-source in.</span><span class="sxs-lookup"><span data-stu-id="3bd0a-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="3bd0a-104">Apertura di questa sezione quando un metodo è già aperto, o viceversa, è un errore.</span><span class="sxs-lookup"><span data-stu-id="3bd0a-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bd0a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3bd0a-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3bd0a-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3bd0a-106">Return Value</span></span>  
 <span data-ttu-id="3bd0a-107">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="3bd0a-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bd0a-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3bd0a-108">Requirements</span></span>  
 <span data-ttu-id="3bd0a-109">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3bd0a-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bd0a-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bd0a-110">See also</span></span>

- [<span data-ttu-id="3bd0a-111">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="3bd0a-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
