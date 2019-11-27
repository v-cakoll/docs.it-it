---
title: Metodo ISymUnmanagedWriter::Initialize
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type:
- apiref
ms.openlocfilehash: 6e9ab623d5fe9fcfda2305df078e988a561afdc5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427971"
---
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="0459e-102">Metodo ISymUnmanagedWriter::Initialize</span><span class="sxs-lookup"><span data-stu-id="0459e-102">ISymUnmanagedWriter::Initialize Method</span></span>
<span data-ttu-id="0459e-103">Imposta l'interfaccia di emissione dei metadati a cui questo writer verrà associato e imposta il nome del file di output in cui verranno scritti i simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="0459e-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="0459e-104">Questo metodo può essere chiamato una sola volta e deve essere chiamato prima di qualsiasi altro metodo del writer.</span><span class="sxs-lookup"><span data-stu-id="0459e-104">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="0459e-105">Alcuni writer possono richiedere un nome file.</span><span class="sxs-lookup"><span data-stu-id="0459e-105">Some writers may require a file name.</span></span> <span data-ttu-id="0459e-106">Tuttavia, è sempre possibile passare un nome file a questo metodo senza alcun effetto negativo sui writer che non utilizzano il nome file.</span><span class="sxs-lookup"><span data-stu-id="0459e-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0459e-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0459e-107">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0459e-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="0459e-108">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="0459e-109">in Puntatore all'interfaccia di emissione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="0459e-109">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="0459e-110">in Nome file in cui vengono scritti i simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="0459e-110">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="0459e-111">Se specificato per un writer che non usa i nomi file, il parametro sarà ignorato.</span><span class="sxs-lookup"><span data-stu-id="0459e-111">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="0459e-112">in Se specificato, il writer di simboli emetterà i simboli nella <xref:System.Runtime.InteropServices.ComTypes.IStream> specificata anziché nel file specificato nel parametro `filename`.</span><span class="sxs-lookup"><span data-stu-id="0459e-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="0459e-113">Il parametro `pIStream` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0459e-113">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="0459e-114">[in] `true` se si tratta di una ricompilazione completa; `false` se si tratta di una compilazione incrementale.</span><span class="sxs-lookup"><span data-stu-id="0459e-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0459e-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0459e-115">Return Value</span></span>  
 <span data-ttu-id="0459e-116">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="0459e-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0459e-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0459e-117">Requirements</span></span>  
 <span data-ttu-id="0459e-118">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0459e-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0459e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0459e-119">See also</span></span>

- [<span data-ttu-id="0459e-120">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="0459e-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="0459e-121">Metodo Initialize2</span><span class="sxs-lookup"><span data-stu-id="0459e-121">Initialize2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
