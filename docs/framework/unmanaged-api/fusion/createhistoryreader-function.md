---
title: Funzione CreateHistoryReader
ms.date: 03/30/2017
api_name:
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e9c9866ee5ee3076d144dc732286ee008cd78c4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487251"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="d6905-102">Funzione CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="d6905-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="d6905-103">Crea un lettore di cronologia per il file specificato.</span><span class="sxs-lookup"><span data-stu-id="d6905-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6905-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6905-104">Syntax</span></span>  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6905-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d6905-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="d6905-106">[in] Il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="d6905-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="d6905-107">[out] Al termine dell'esecuzione, contiene un puntatore per il Visualizzatore della cronologia.</span><span class="sxs-lookup"><span data-stu-id="d6905-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6905-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d6905-108">Return Value</span></span>  
 <span data-ttu-id="d6905-109">Questo metodo restituisce i codici di errore COM standard, come definito nel file Winerror. H, oltre a quelli descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d6905-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="d6905-110">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="d6905-110">Return code</span></span>|<span data-ttu-id="d6905-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6905-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d6905-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d6905-112">S_OK</span></span>|<span data-ttu-id="d6905-113">Indica che il metodo è stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="d6905-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="d6905-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d6905-114">E_INVALIDARG</span></span>|<span data-ttu-id="d6905-115">Indica che `wzFilePath` o `ppHistoryReader` sono impostate su un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="d6905-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d6905-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d6905-116">Requirements</span></span>  
 <span data-ttu-id="d6905-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6905-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6905-118">**Libreria:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="d6905-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="d6905-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6905-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6905-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6905-120">See also</span></span>
- [<span data-ttu-id="d6905-121">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="d6905-121">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
