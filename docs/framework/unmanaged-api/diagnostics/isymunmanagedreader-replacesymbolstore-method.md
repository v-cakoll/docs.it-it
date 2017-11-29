---
title: Metodo ISymUnmanagedReader::ReplaceSymbolStore
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.ReplaceSymbolStore
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09bcad4898cf4d3310a96164bdc82006e185006f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="b2c7f-102">Metodo ISymUnmanagedReader::ReplaceSymbolStore</span><span class="sxs-lookup"><span data-stu-id="b2c7f-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="b2c7f-103">Sostituisce l'archivio dei simboli esistente con un archivio dei simboli delta.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="b2c7f-104">Questo metodo è simile al [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) metodo, ad eccezione del fatto che il delta fornito funziona come una sostituzione completa anziché un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2c7f-105">È necessario specificare solo uno del `filename` o `pIStream` parametri, non entrambi.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="b2c7f-106">Se `filename` viene specificato, l'archivio dei simboli verrà aggiornato con i simboli in tale file.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="b2c7f-107">Se `pIStream` è specificato, l'archivio verrà aggiornato con i dati di <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2c7f-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2c7f-108">Syntax</span></span>  
  
```  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2c7f-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="b2c7f-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="b2c7f-110">[in] Il nome del file contenente l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="b2c7f-111">[in] Il flusso di file, utilizzato come alternativa per il `filename` parametro.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2c7f-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b2c7f-112">Return Value</span></span>  
 <span data-ttu-id="b2c7f-113">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="b2c7f-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2c7f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b2c7f-114">Requirements</span></span>  
 <span data-ttu-id="b2c7f-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b2c7f-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2c7f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2c7f-116">See Also</span></span>  
 [<span data-ttu-id="b2c7f-117">ISymUnmanagedReader (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="b2c7f-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
