---
title: Metodo ISymUnmanagedReader::UpdateSymbolStore
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.UpdateSymbolStore
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cfea77814069f6689f7492608548836fdafa591b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="cf81c-102">Metodo ISymUnmanagedReader::UpdateSymbolStore</span><span class="sxs-lookup"><span data-stu-id="cf81c-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="cf81c-103">Aggiorna l'archivio dei simboli esistente con un archivio dei simboli delta.</span><span class="sxs-lookup"><span data-stu-id="cf81c-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="cf81c-104">Questo metodo viene utilizzato in scenari di modifica e continuazione per aggiornare l'archivio dei simboli in modo che corrisponda ai file eseguibile (PE) originale delta.</span><span class="sxs-lookup"><span data-stu-id="cf81c-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf81c-105">È necessario specificare solo uno del `filename` o `pIStream` parametri, non entrambi.</span><span class="sxs-lookup"><span data-stu-id="cf81c-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="cf81c-106">Se `filename` viene specificato, l'archivio dei simboli verrà aggiornato con i simboli in tale file.</span><span class="sxs-lookup"><span data-stu-id="cf81c-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="cf81c-107">Se `pIStream` è specificato, l'archivio verrà aggiornato con i dati di <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span><span class="sxs-lookup"><span data-stu-id="cf81c-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf81c-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cf81c-108">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf81c-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="cf81c-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="cf81c-110">[in] Il nome del file che contiene l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="cf81c-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="cf81c-111">[in] Il flusso di file, utilizzato come alternativa per il `filename` parametro.</span><span class="sxs-lookup"><span data-stu-id="cf81c-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf81c-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cf81c-112">Return Value</span></span>  
 <span data-ttu-id="cf81c-113">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="cf81c-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf81c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cf81c-114">Requirements</span></span>  
 <span data-ttu-id="cf81c-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cf81c-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf81c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf81c-116">See Also</span></span>  
 [<span data-ttu-id="cf81c-117">ISymUnmanagedReader (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="cf81c-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
