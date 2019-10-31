---
title: Interfaccia ISymUnmanagedWriter5
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
ms.openlocfilehash: 18371b6aefb002f5adf27d43f85194c6c35f6ef5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121636"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="e41d4-102">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="e41d4-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="e41d4-103">Interfaccia Metodo ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="e41d4-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e41d4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e41d4-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="e41d4-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="e41d4-105">Methods</span></span>  
 <span data-ttu-id="e41d4-106">Per l'interfaccia sono disponibili i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="e41d4-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="e41d4-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="e41d4-107">Method</span></span>|<span data-ttu-id="e41d4-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e41d4-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e41d4-109">Metodo CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="e41d4-109">CloseMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="e41d4-110">Chiudere la sezione relativa ai dati personalizzati speciali per informazioni sul mapping di intervalli da token a origine.</span><span class="sxs-lookup"><span data-stu-id="e41d4-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="e41d4-111">Al termine della chiusura, non è possibile aggiungere altre informazioni sul mapping.</span><span class="sxs-lookup"><span data-stu-id="e41d4-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="e41d4-112">Metodo MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="e41d4-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="e41d4-113">Esegue il mapping del token di metadati specificato all'intervallo di righe di origine specificato nel file di origine specificato.</span><span class="sxs-lookup"><span data-stu-id="e41d4-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="e41d4-114">Deve essere chiamato tra le chiamate al [Metodo OpenMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) e al [Metodo CloseMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="e41d4-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="e41d4-115">Metodo OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="e41d4-115">OpenMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="e41d4-116">Aprire una sezione di dati personalizzata speciale per creare informazioni sul mapping di intervalli da token a origine in.</span><span class="sxs-lookup"><span data-stu-id="e41d4-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="e41d4-117">L'apertura di questa sezione quando un metodo è già aperto o viceversa è un errore.</span><span class="sxs-lookup"><span data-stu-id="e41d4-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e41d4-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e41d4-118">Requirements</span></span>  
 <span data-ttu-id="e41d4-119">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e41d4-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e41d4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e41d4-120">See also</span></span>

- [<span data-ttu-id="e41d4-121">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="e41d4-121">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="e41d4-122">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="e41d4-122">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
