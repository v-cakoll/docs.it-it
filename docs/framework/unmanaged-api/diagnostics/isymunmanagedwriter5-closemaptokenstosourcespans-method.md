---
title: Metodo ISymUnmanagedWriter5::CloseMapTokensToSourceSpans
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f5f23c3fe39adcebcfdfadb9e9c2b639f16330d1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="97574-102">Metodo ISymUnmanagedWriter5::CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="97574-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="97574-103">Chiudere la sezione di dati personalizzati speciali per le informazioni di mapping span di token all'origine.</span><span class="sxs-lookup"><span data-stu-id="97574-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="97574-104">Dopo che è stato chiuso, è possibile aggiungere alcun altre informazioni di mapping.</span><span class="sxs-lookup"><span data-stu-id="97574-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97574-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97574-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="97574-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="97574-106">Return Value</span></span>  
 <span data-ttu-id="97574-107">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="97574-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97574-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97574-108">Requirements</span></span>  
 <span data-ttu-id="97574-109">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="97574-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97574-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97574-110">See Also</span></span>  
 [<span data-ttu-id="97574-111">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="97574-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
