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
ms.openlocfilehash: db2137146ded5200e05bbf88e23ae599f3eb7dec
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615449"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="60a42-102">Metodo ISymUnmanagedReader::ReplaceSymbolStore</span><span class="sxs-lookup"><span data-stu-id="60a42-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="60a42-103">Sostituisce l'archivio dei simboli esistente con un archivio dei simboli delta.</span><span class="sxs-lookup"><span data-stu-id="60a42-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="60a42-104">Questo metodo è simile al metodo [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) , ad eccezione del fatto che il delta specificato funge da sostituzione completa anziché da un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="60a42-104">This method is similar to the [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="60a42-105">È necessario specificare solo uno dei `filename` parametri o `pIStream` , non entrambi.</span><span class="sxs-lookup"><span data-stu-id="60a42-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="60a42-106">Se `filename` si specifica, l'archivio dei simboli verrà aggiornato con i simboli presenti in tale file.</span><span class="sxs-lookup"><span data-stu-id="60a42-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="60a42-107">Se `pIStream` si specifica, l'archivio verrà aggiornato con i dati del <xref:System.Runtime.InteropServices.ComTypes.IStream> .</span><span class="sxs-lookup"><span data-stu-id="60a42-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60a42-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60a42-108">Syntax</span></span>  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60a42-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="60a42-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="60a42-110">in Nome del file contenente l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="60a42-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="60a42-111">in Flusso di file, usato come alternativa al `filename` parametro.</span><span class="sxs-lookup"><span data-stu-id="60a42-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60a42-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="60a42-112">Return Value</span></span>  
 <span data-ttu-id="60a42-113">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="60a42-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60a42-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="60a42-114">Requirements</span></span>  
 <span data-ttu-id="60a42-115">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="60a42-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60a42-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60a42-116">See also</span></span>

- [<span data-ttu-id="60a42-117">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="60a42-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
