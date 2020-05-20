---
title: Metodo ISymUnmanagedWriter::Initialize2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize2
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize2 method [.NET Framework debugging]
- Initialize2 method [.NET Framework debugging]
ms.assetid: 93de56b6-4ae8-4cca-acdc-25a434623509
topic_type:
- apiref
ms.openlocfilehash: 869d7d36ac24bfeee5b2361dd569945ad77eaf7f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610067"
---
# <a name="isymunmanagedwriterinitialize2-method"></a><span data-ttu-id="2a7b3-102">Metodo ISymUnmanagedWriter::Initialize2</span><span class="sxs-lookup"><span data-stu-id="2a7b3-102">ISymUnmanagedWriter::Initialize2 Method</span></span>
<span data-ttu-id="2a7b3-103">Imposta l'interfaccia di emissione dei metadati a cui questo writer verrà associato e imposta il nome del file di output in cui verranno scritti i simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="2a7b3-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span> <span data-ttu-id="2a7b3-104">Questo metodo consente inoltre di impostare il percorso finale del file del database di programma (PDB).</span><span class="sxs-lookup"><span data-stu-id="2a7b3-104">This method also lets you set the final location of the program database (PDB) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a7b3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a7b3-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a7b3-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2a7b3-106">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="2a7b3-107">in Puntatore all'interfaccia di emissione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="2a7b3-107">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `tempfilename`  
 <span data-ttu-id="2a7b3-108">in Puntatore a un oggetto `WCHAR` che contiene il nome file in cui vengono scritti i simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="2a7b3-108">[in] A pointer to a `WCHAR` that contains the file name to which the debugging symbols are written.</span></span> <span data-ttu-id="2a7b3-109">Se specificato per un writer che non usa i nomi file, il parametro sarà ignorato.</span><span class="sxs-lookup"><span data-stu-id="2a7b3-109">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="2a7b3-110">in Se specificato, il writer di simboli emette i simboli nell'oggetto specificato <xref:System.Runtime.InteropServices.ComTypes.IStream> anziché nel file specificato nel `filename` parametro.</span><span class="sxs-lookup"><span data-stu-id="2a7b3-110">[in] If specified, the symbol writer emits the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="2a7b3-111">`pIStream` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2a7b3-111">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="2a7b3-112">[in] `true` Se si tratta di una ricompilazione completa; `false`se si tratta di una compilazione incrementale.</span><span class="sxs-lookup"><span data-stu-id="2a7b3-112">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
 `finalfilename`  
 <span data-ttu-id="2a7b3-113">in Puntatore a un oggetto `WCHAR` che rappresenta la stringa di percorso della posizione finale del file PDB.</span><span class="sxs-lookup"><span data-stu-id="2a7b3-113">[in] A pointer to a `WCHAR` that is the path string to the final location of the PDB file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a7b3-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2a7b3-114">Return Value</span></span>  
 <span data-ttu-id="2a7b3-115">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="2a7b3-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a7b3-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2a7b3-116">Requirements</span></span>  
 <span data-ttu-id="2a7b3-117">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="2a7b3-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a7b3-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a7b3-118">See also</span></span>

- [<span data-ttu-id="2a7b3-119">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="2a7b3-119">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="2a7b3-120">Metodo Initialize</span><span class="sxs-lookup"><span data-stu-id="2a7b3-120">Initialize Method</span></span>](isymunmanagedwriter-initialize-method.md)
