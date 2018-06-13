---
title: Metodo ISymUnmanagedWriter5::OpenMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d3bc8b00b568f96cd55b7811f310d34c1ff700d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428648"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="aacdd-102">Metodo ISymUnmanagedWriter5::OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="aacdd-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="aacdd-103">Aprire una sezione di dati personalizzati speciali per generare informazioni di mapping span token all'origine in.</span><span class="sxs-lookup"><span data-stu-id="aacdd-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="aacdd-104">Apertura di questa sezione quando un metodo è già aperto, o viceversa, è un errore.</span><span class="sxs-lookup"><span data-stu-id="aacdd-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aacdd-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aacdd-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="aacdd-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="aacdd-106">Return Value</span></span>  
 <span data-ttu-id="aacdd-107">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="aacdd-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aacdd-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aacdd-108">Requirements</span></span>  
 <span data-ttu-id="aacdd-109">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="aacdd-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aacdd-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aacdd-110">See Also</span></span>  
 [<span data-ttu-id="aacdd-111">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="aacdd-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
