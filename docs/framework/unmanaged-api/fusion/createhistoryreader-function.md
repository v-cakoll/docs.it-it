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
ms.openlocfilehash: 8beb5e64b05f50ba61ced72fcdb7700d4b9f30e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505042"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="4db84-102">Funzione CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="4db84-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="4db84-103">Crea un lettore di cronologia per il file specificato.</span><span class="sxs-lookup"><span data-stu-id="4db84-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4db84-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4db84-104">Syntax</span></span>  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4db84-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4db84-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="4db84-106">[in] Il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="4db84-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="4db84-107">[out] Al termine dell'esecuzione, contiene un puntatore per il Visualizzatore della cronologia.</span><span class="sxs-lookup"><span data-stu-id="4db84-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4db84-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4db84-108">Return Value</span></span>  
 <span data-ttu-id="4db84-109">Questo metodo restituisce i codici di errore COM standard, come definito nel file Winerror. H, oltre a quelli descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4db84-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="4db84-110">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="4db84-110">Return code</span></span>|<span data-ttu-id="4db84-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4db84-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="4db84-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4db84-112">S_OK</span></span>|<span data-ttu-id="4db84-113">Indica che il metodo è stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="4db84-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="4db84-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4db84-114">E_INVALIDARG</span></span>|<span data-ttu-id="4db84-115">Indica che `wzFilePath` o `ppHistoryReader` sono impostate su un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="4db84-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4db84-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4db84-116">Requirements</span></span>  
 <span data-ttu-id="4db84-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4db84-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4db84-118">**Libreria:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="4db84-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="4db84-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4db84-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4db84-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4db84-120">See also</span></span>
- [<span data-ttu-id="4db84-121">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="4db84-121">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
