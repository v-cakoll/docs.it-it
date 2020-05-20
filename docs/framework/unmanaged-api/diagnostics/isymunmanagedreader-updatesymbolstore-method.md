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
ms.openlocfilehash: ccc787aa1c820a486d9a513055c9c9834b90bd1a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615436"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="bd388-102">Metodo ISymUnmanagedReader::UpdateSymbolStore</span><span class="sxs-lookup"><span data-stu-id="bd388-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="bd388-103">Aggiorna l'archivio dei simboli esistente con un archivio dei simboli delta.</span><span class="sxs-lookup"><span data-stu-id="bd388-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="bd388-104">Questo metodo viene usato negli scenari di modifica e continuazione per aggiornare l'archivio simboli in modo che corrisponda ai Delta al file eseguibile portabile originale (PE).</span><span class="sxs-lookup"><span data-stu-id="bd388-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bd388-105">È necessario specificare solo uno dei `filename` parametri o `pIStream` , non entrambi.</span><span class="sxs-lookup"><span data-stu-id="bd388-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="bd388-106">Se `filename` si specifica, l'archivio dei simboli verrà aggiornato con i simboli presenti in tale file.</span><span class="sxs-lookup"><span data-stu-id="bd388-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="bd388-107">Se `pIStream` si specifica, l'archivio verrà aggiornato con i dati del <xref:System.Runtime.InteropServices.ComTypes.IStream> .</span><span class="sxs-lookup"><span data-stu-id="bd388-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd388-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bd388-108">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd388-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="bd388-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="bd388-110">in Nome del file che contiene l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="bd388-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="bd388-111">in Flusso di file, usato come alternativa al `filename` parametro.</span><span class="sxs-lookup"><span data-stu-id="bd388-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd388-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bd388-112">Return Value</span></span>  
 <span data-ttu-id="bd388-113">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="bd388-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd388-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bd388-114">Requirements</span></span>  
 <span data-ttu-id="bd388-115">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="bd388-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd388-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd388-116">See also</span></span>

- [<span data-ttu-id="bd388-117">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="bd388-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
