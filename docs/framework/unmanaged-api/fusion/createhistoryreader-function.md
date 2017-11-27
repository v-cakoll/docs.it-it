---
title: Funzione CreateHistoryReader
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateHistoryReader
api_location: fusion.dll
api_type: DLLExport
f1_keywords: CreateHistoryReader
helpviewer_keywords: CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4f4b09f592a27b7d3d25b2dbe13be7e261023bf5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="c3374-102">Funzione CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="c3374-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="c3374-103">Crea un lettore di cronologia per il file specificato.</span><span class="sxs-lookup"><span data-stu-id="c3374-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3374-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3374-104">Syntax</span></span>  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c3374-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c3374-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="c3374-106">[in] Il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="c3374-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="c3374-107">[out] Al termine, contiene un puntatore al reader della cronologia.</span><span class="sxs-lookup"><span data-stu-id="c3374-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3374-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c3374-108">Return Value</span></span>  
 <span data-ttu-id="c3374-109">Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. H, oltre a quelli descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c3374-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="c3374-110">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="c3374-110">Return code</span></span>|<span data-ttu-id="c3374-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3374-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="c3374-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3374-112">S_OK</span></span>|<span data-ttu-id="c3374-113">Indica che il metodo viene completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="c3374-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="c3374-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c3374-114">E_INVALIDARG</span></span>|<span data-ttu-id="c3374-115">Indica che `wzFilePath` o `ppHistoryReader` sono impostate su un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="c3374-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c3374-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c3374-116">Requirements</span></span>  
 <span data-ttu-id="c3374-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3374-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3374-118">**Libreria:** Fusion</span><span class="sxs-lookup"><span data-stu-id="c3374-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="c3374-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3374-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3374-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3374-120">See Also</span></span>  
 [<span data-ttu-id="c3374-121">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="c3374-121">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
