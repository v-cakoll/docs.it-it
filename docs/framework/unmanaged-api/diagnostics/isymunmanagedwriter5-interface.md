---
title: Interfaccia ISymUnmanagedWriter5
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
ms.openlocfilehash: bdc630c3c94c7d03b736efa0a95665f10aac7c6e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609430"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="7db00-102">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="7db00-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="7db00-103">Interfaccia Metodo ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="7db00-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7db00-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7db00-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="7db00-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="7db00-105">Methods</span></span>  
 <span data-ttu-id="7db00-106">Per l'interfaccia sono disponibili i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="7db00-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="7db00-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="7db00-107">Method</span></span>|<span data-ttu-id="7db00-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7db00-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7db00-109">Metodo CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="7db00-109">CloseMapTokensToSourceSpans Method</span></span>](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="7db00-110">Chiudere la sezione relativa ai dati personalizzati speciali per informazioni sul mapping di intervalli da token a origine.</span><span class="sxs-lookup"><span data-stu-id="7db00-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="7db00-111">Al termine della chiusura, non è possibile aggiungere altre informazioni sul mapping.</span><span class="sxs-lookup"><span data-stu-id="7db00-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="7db00-112">Metodo MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="7db00-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="7db00-113">Esegue il mapping del token di metadati specificato all'intervallo di righe di origine specificato nel file di origine specificato.</span><span class="sxs-lookup"><span data-stu-id="7db00-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="7db00-114">Deve essere chiamato tra le chiamate al [Metodo OpenMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) e al [Metodo CloseMapTokensToSourceSpans](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="7db00-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="7db00-115">Metodo OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="7db00-115">OpenMapTokensToSourceSpans Method</span></span>](isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="7db00-116">Aprire una sezione di dati personalizzata speciale per creare informazioni sul mapping di intervalli da token a origine in.</span><span class="sxs-lookup"><span data-stu-id="7db00-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="7db00-117">L'apertura di questa sezione quando un metodo è già aperto o viceversa è un errore.</span><span class="sxs-lookup"><span data-stu-id="7db00-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7db00-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7db00-118">Requirements</span></span>  
 <span data-ttu-id="7db00-119">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="7db00-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7db00-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7db00-120">See also</span></span>

- [<span data-ttu-id="7db00-121">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="7db00-121">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="7db00-122">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="7db00-122">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)
