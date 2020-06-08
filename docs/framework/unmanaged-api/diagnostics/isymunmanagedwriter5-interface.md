---
title: Interfaccia ISymUnmanagedWriter5
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
ms.openlocfilehash: d9204457b71b670e1c96ed228ad11116bdf41fe6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493578"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="890bf-102">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="890bf-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="890bf-103">Interfaccia Metodo ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="890bf-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="890bf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="890bf-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="890bf-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="890bf-105">Methods</span></span>  
 <span data-ttu-id="890bf-106">Per l'interfaccia sono disponibili i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="890bf-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="890bf-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="890bf-107">Method</span></span>|<span data-ttu-id="890bf-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="890bf-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="890bf-109">Metodo CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="890bf-109">CloseMapTokensToSourceSpans Method</span></span>](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="890bf-110">Chiudere la sezione relativa ai dati personalizzati speciali per informazioni sul mapping di intervalli da token a origine.</span><span class="sxs-lookup"><span data-stu-id="890bf-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="890bf-111">Al termine della chiusura, non è possibile aggiungere altre informazioni sul mapping.</span><span class="sxs-lookup"><span data-stu-id="890bf-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="890bf-112">Metodo MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="890bf-112">MapTokenToSourceSpan Method</span></span>](isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="890bf-113">Esegue il mapping del token di metadati specificato all'intervallo di righe di origine specificato nel file di origine specificato.</span><span class="sxs-lookup"><span data-stu-id="890bf-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="890bf-114">Deve essere chiamato tra le chiamate al [Metodo OpenMapTokensToSourceSpans](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) e al [Metodo CloseMapTokensToSourceSpans](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="890bf-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="890bf-115">Metodo OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="890bf-115">OpenMapTokensToSourceSpans Method</span></span>](isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="890bf-116">Aprire una sezione di dati personalizzata speciale per creare informazioni sul mapping di intervalli da token a origine in.</span><span class="sxs-lookup"><span data-stu-id="890bf-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="890bf-117">L'apertura di questa sezione quando un metodo è già aperto o viceversa è un errore.</span><span class="sxs-lookup"><span data-stu-id="890bf-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="890bf-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="890bf-118">Requirements</span></span>  
 <span data-ttu-id="890bf-119">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="890bf-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="890bf-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="890bf-120">See also</span></span>

- [<span data-ttu-id="890bf-121">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="890bf-121">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="890bf-122">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="890bf-122">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)
