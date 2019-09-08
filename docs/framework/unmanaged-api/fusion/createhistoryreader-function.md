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
ms.openlocfilehash: 2710d14d6e73879fd17a6b58659463ea205f2384
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795374"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="0dee5-102">Funzione CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="0dee5-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="0dee5-103">Crea un lettore della cronologia per il file specificato.</span><span class="sxs-lookup"><span data-stu-id="0dee5-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dee5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0dee5-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dee5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0dee5-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="0dee5-106">in Percorso del file.</span><span class="sxs-lookup"><span data-stu-id="0dee5-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="0dee5-107">out Al termine dell'operazione, contiene un puntatore al lettore della cronologia.</span><span class="sxs-lookup"><span data-stu-id="0dee5-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0dee5-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0dee5-108">Return Value</span></span>  
 <span data-ttu-id="0dee5-109">Questo metodo restituisce i codici di errore COM standard come definito in WinError. h, oltre ai valori descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0dee5-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="0dee5-110">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="0dee5-110">Return code</span></span>|<span data-ttu-id="0dee5-111">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="0dee5-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="0dee5-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0dee5-112">S_OK</span></span>|<span data-ttu-id="0dee5-113">Indica che il metodo è stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="0dee5-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="0dee5-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0dee5-114">E_INVALIDARG</span></span>|<span data-ttu-id="0dee5-115">Indica che `wzFilePath` o `ppHistoryReader` sono impostati su un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="0dee5-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0dee5-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0dee5-116">Requirements</span></span>  
 <span data-ttu-id="0dee5-117">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0dee5-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dee5-118">**Libreria** Fusion. dll</span><span class="sxs-lookup"><span data-stu-id="0dee5-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="0dee5-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dee5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dee5-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0dee5-120">See also</span></span>

- [<span data-ttu-id="0dee5-121">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="0dee5-121">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
