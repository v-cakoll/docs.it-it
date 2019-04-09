---
title: Metodo ISymUnmanagedWriter5::CloseMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b3dea6b9710f1ee5ccf8c51261f59b2de026f5e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127777"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="7e1c0-102">Metodo ISymUnmanagedWriter5::CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="7e1c0-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="7e1c0-103">Chiudere la sezione di dati personalizzati speciali per l'intervallo di origine-token-per informazioni sul mapping.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="7e1c0-104">Dopo la chiusura, è possibile aggiungere alcuna informazione sul mapping di più.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e1c0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e1c0-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7e1c0-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7e1c0-106">Return Value</span></span>  
 <span data-ttu-id="7e1c0-107">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="7e1c0-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e1c0-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7e1c0-108">Requirements</span></span>  
 <span data-ttu-id="7e1c0-109">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7e1c0-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e1c0-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e1c0-110">See also</span></span>

- [<span data-ttu-id="7e1c0-111">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="7e1c0-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
