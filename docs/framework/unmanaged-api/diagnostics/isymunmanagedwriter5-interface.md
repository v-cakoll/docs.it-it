---
title: Interfaccia ISymUnmanagedWriter5
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 701b8de977d49a7d93f393b320bcb9d0d780c7bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="fd148-102">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="fd148-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="fd148-103">Interfaccia ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="fd148-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd148-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd148-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="fd148-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="fd148-105">Methods</span></span>  
 <span data-ttu-id="fd148-106">Per l'interfaccia sono disponibili i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="fd148-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="fd148-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="fd148-107">Method</span></span>|<span data-ttu-id="fd148-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd148-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fd148-109">Metodo CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="fd148-109">CloseMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="fd148-110">Chiudere la sezione di dati personalizzati speciali per le informazioni di mapping span di token all'origine.</span><span class="sxs-lookup"><span data-stu-id="fd148-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="fd148-111">Dopo che è stato chiuso, è possibile aggiungere alcun altre informazioni di mapping.</span><span class="sxs-lookup"><span data-stu-id="fd148-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="fd148-112">Metodo MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="fd148-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="fd148-113">Le mappe sono estese al token di metadati specificato alla riga di origine specificato nel file di origine specificato.</span><span class="sxs-lookup"><span data-stu-id="fd148-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="fd148-114">Deve essere chiamato tra le chiamate a [metodo OpenMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) e [metodo CloseMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="fd148-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="fd148-115">Metodo OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="fd148-115">OpenMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="fd148-116">Aprire una sezione di dati personalizzati speciali per generare informazioni di mapping span token all'origine in.</span><span class="sxs-lookup"><span data-stu-id="fd148-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="fd148-117">Apertura di questa sezione quando un metodo è già aperto, o viceversa, è un errore.</span><span class="sxs-lookup"><span data-stu-id="fd148-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fd148-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fd148-118">Requirements</span></span>  
 <span data-ttu-id="fd148-119">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fd148-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd148-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd148-120">See Also</span></span>  
 [<span data-ttu-id="fd148-121">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="fd148-121">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="fd148-122">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="fd148-122">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
