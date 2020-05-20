---
title: Metodo ISymUnmanagedWriter5::OpenMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
ms.openlocfilehash: 82b46ea315009b65254735d44e355154b83b22e2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609495"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="d4313-102">Metodo ISymUnmanagedWriter5::OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="d4313-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="d4313-103">Aprire una sezione di dati personalizzata speciale per creare informazioni sul mapping di intervalli da token a origine in.</span><span class="sxs-lookup"><span data-stu-id="d4313-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="d4313-104">L'apertura di questa sezione quando un metodo è già aperto o viceversa è un errore.</span><span class="sxs-lookup"><span data-stu-id="d4313-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4313-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4313-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d4313-106">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d4313-106">Return Value</span></span>  
 <span data-ttu-id="d4313-107">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="d4313-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4313-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d4313-108">Requirements</span></span>  
 <span data-ttu-id="d4313-109">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d4313-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4313-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4313-110">See also</span></span>

- [<span data-ttu-id="d4313-111">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="d4313-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
