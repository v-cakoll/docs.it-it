---
title: Metodo ISymUnmanagedReader::ReplaceSymbolStore
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.ReplaceSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8721f7c30061fbfd4a761bed090b761762c3c13c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939029"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="22088-102">Metodo ISymUnmanagedReader::ReplaceSymbolStore</span><span class="sxs-lookup"><span data-stu-id="22088-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="22088-103">Sostituisce l'archivio dei simboli esistente con un archivio dei simboli delta.</span><span class="sxs-lookup"><span data-stu-id="22088-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="22088-104">Questo metodo è simile al metodo [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) , ad eccezione del fatto che il delta specificato funge da sostituzione completa anziché da un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="22088-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22088-105">È necessario specificare solo uno dei `filename` parametri o `pIStream` , non entrambi.</span><span class="sxs-lookup"><span data-stu-id="22088-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="22088-106">Se `filename` si specifica, l'archivio dei simboli verrà aggiornato con i simboli presenti in tale file.</span><span class="sxs-lookup"><span data-stu-id="22088-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="22088-107">Se `pIStream` si specifica, l'archivio verrà aggiornato con i dati <xref:System.Runtime.InteropServices.ComTypes.IStream>del.</span><span class="sxs-lookup"><span data-stu-id="22088-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22088-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22088-108">Syntax</span></span>  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22088-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="22088-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="22088-110">in Nome del file contenente l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="22088-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="22088-111">in Flusso di file, usato come alternativa al `filename` parametro.</span><span class="sxs-lookup"><span data-stu-id="22088-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22088-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="22088-112">Return Value</span></span>  
 <span data-ttu-id="22088-113">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="22088-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22088-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="22088-114">Requirements</span></span>  
 <span data-ttu-id="22088-115">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="22088-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22088-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22088-116">See also</span></span>

- [<span data-ttu-id="22088-117">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="22088-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
