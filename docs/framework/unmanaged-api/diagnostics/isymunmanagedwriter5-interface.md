---
title: Interfaccia ISymUnmanagedWriter5
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5fd7c2bd4fae94d1ef5021b558a04b734803b68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430557"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="b858f-102">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="b858f-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="b858f-103">Interfaccia ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="b858f-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b858f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b858f-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="b858f-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="b858f-105">Methods</span></span>  
 <span data-ttu-id="b858f-106">Per l'interfaccia sono disponibili i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="b858f-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="b858f-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="b858f-107">Method</span></span>|<span data-ttu-id="b858f-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b858f-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b858f-109">Metodo CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="b858f-109">CloseMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="b858f-110">Chiudere la sezione di dati personalizzati speciali per le informazioni di mapping span di token all'origine.</span><span class="sxs-lookup"><span data-stu-id="b858f-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="b858f-111">Dopo che è stato chiuso, è possibile aggiungere alcun altre informazioni di mapping.</span><span class="sxs-lookup"><span data-stu-id="b858f-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="b858f-112">Metodo MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="b858f-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="b858f-113">Le mappe sono estese al token di metadati specificato alla riga di origine specificato nel file di origine specificato.</span><span class="sxs-lookup"><span data-stu-id="b858f-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="b858f-114">Deve essere chiamato tra le chiamate a [metodo OpenMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) e [metodo CloseMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="b858f-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="b858f-115">Metodo OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="b858f-115">OpenMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="b858f-116">Aprire una sezione di dati personalizzati speciali per generare informazioni di mapping span token all'origine in.</span><span class="sxs-lookup"><span data-stu-id="b858f-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="b858f-117">Apertura di questa sezione quando un metodo è già aperto, o viceversa, è un errore.</span><span class="sxs-lookup"><span data-stu-id="b858f-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b858f-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b858f-118">Requirements</span></span>  
 <span data-ttu-id="b858f-119">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b858f-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b858f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b858f-120">See Also</span></span>  
 [<span data-ttu-id="b858f-121">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="b858f-121">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="b858f-122">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="b858f-122">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
