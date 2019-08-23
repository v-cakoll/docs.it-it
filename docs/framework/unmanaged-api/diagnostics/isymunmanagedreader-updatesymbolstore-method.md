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
ms.openlocfilehash: d84d4fccb2cb4e500f07f6bfbfb93b8c7b81f5d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938999"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="ee999-102">Metodo ISymUnmanagedReader::UpdateSymbolStore</span><span class="sxs-lookup"><span data-stu-id="ee999-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="ee999-103">Aggiorna l'archivio dei simboli esistente con un archivio dei simboli delta.</span><span class="sxs-lookup"><span data-stu-id="ee999-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="ee999-104">Questo metodo viene usato negli scenari di modifica e continuazione per aggiornare l'archivio simboli in modo che corrisponda ai Delta al file eseguibile portabile originale (PE).</span><span class="sxs-lookup"><span data-stu-id="ee999-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee999-105">È necessario specificare solo uno dei `filename` parametri o `pIStream` , non entrambi.</span><span class="sxs-lookup"><span data-stu-id="ee999-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="ee999-106">Se `filename` si specifica, l'archivio dei simboli verrà aggiornato con i simboli presenti in tale file.</span><span class="sxs-lookup"><span data-stu-id="ee999-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="ee999-107">Se `pIStream` si specifica, l'archivio verrà aggiornato con i dati <xref:System.Runtime.InteropServices.ComTypes.IStream>del.</span><span class="sxs-lookup"><span data-stu-id="ee999-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee999-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee999-108">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee999-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="ee999-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="ee999-110">in Nome del file che contiene l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="ee999-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="ee999-111">in Flusso di file, usato come alternativa al `filename` parametro.</span><span class="sxs-lookup"><span data-stu-id="ee999-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee999-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ee999-112">Return Value</span></span>  
 <span data-ttu-id="ee999-113">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="ee999-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee999-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ee999-114">Requirements</span></span>  
 <span data-ttu-id="ee999-115">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ee999-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee999-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee999-116">See also</span></span>

- [<span data-ttu-id="ee999-117">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="ee999-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
