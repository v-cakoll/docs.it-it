---
title: Metodo ISymUnmanagedReader::UpdateSymbolStore
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.UpdateSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cfc4507557102e19d95f1b746b3a76a231882d7b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736735"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="0adeb-102">Metodo ISymUnmanagedReader::UpdateSymbolStore</span><span class="sxs-lookup"><span data-stu-id="0adeb-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="0adeb-103">Aggiorna l'archivio dei simboli esistente con un archivio dei simboli delta.</span><span class="sxs-lookup"><span data-stu-id="0adeb-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="0adeb-104">Questo metodo viene utilizzato in scenari di modifica e continuazione per aggiornare l'archivio dei simboli in modo da corrispondere i delta per l'originale file eseguibile portabile (PE).</span><span class="sxs-lookup"><span data-stu-id="0adeb-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0adeb-105">È necessario specificare solo una delle `filename` o `pIStream` parametri, non entrambi.</span><span class="sxs-lookup"><span data-stu-id="0adeb-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="0adeb-106">Se `filename` viene specificato, l'archivio dei simboli verrà aggiornato con i simboli in tale file.</span><span class="sxs-lookup"><span data-stu-id="0adeb-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="0adeb-107">Se `pIStream` viene specificato, l'archivio verrà aggiornato con i dati di <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span><span class="sxs-lookup"><span data-stu-id="0adeb-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0adeb-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0adeb-108">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0adeb-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="0adeb-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="0adeb-110">[in] Il nome del file che contiene l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="0adeb-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="0adeb-111">[in] Il flusso di file, usato come alternativa per il `filename` parametro.</span><span class="sxs-lookup"><span data-stu-id="0adeb-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0adeb-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0adeb-112">Return Value</span></span>  
 <span data-ttu-id="0adeb-113">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="0adeb-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0adeb-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0adeb-114">Requirements</span></span>  
 <span data-ttu-id="0adeb-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0adeb-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0adeb-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0adeb-116">See also</span></span>

- [<span data-ttu-id="0adeb-117">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="0adeb-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
