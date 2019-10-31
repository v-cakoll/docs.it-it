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
ms.openlocfilehash: 80979f0424469bb1d4771ad6507bb8c9d5364ab4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108600"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="7424a-102">Funzione CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="7424a-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="7424a-103">Crea un lettore della cronologia per il file specificato.</span><span class="sxs-lookup"><span data-stu-id="7424a-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7424a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7424a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="7424a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7424a-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="7424a-106">in Percorso del file.</span><span class="sxs-lookup"><span data-stu-id="7424a-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="7424a-107">out Al termine dell'operazione, contiene un puntatore al lettore della cronologia.</span><span class="sxs-lookup"><span data-stu-id="7424a-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7424a-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7424a-108">Return Value</span></span>  
 <span data-ttu-id="7424a-109">Questo metodo restituisce i codici di errore COM standard come definito in WinError. h, oltre ai valori descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7424a-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="7424a-110">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="7424a-110">Return code</span></span>|<span data-ttu-id="7424a-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7424a-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="7424a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7424a-112">S_OK</span></span>|<span data-ttu-id="7424a-113">Indica che il metodo è stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="7424a-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="7424a-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7424a-114">E_INVALIDARG</span></span>|<span data-ttu-id="7424a-115">Indica che `wzFilePath` o `ppHistoryReader` sono impostati su un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="7424a-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7424a-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7424a-116">Requirements</span></span>  
 <span data-ttu-id="7424a-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7424a-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7424a-118">**Libreria:** Fusion. dll</span><span class="sxs-lookup"><span data-stu-id="7424a-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="7424a-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7424a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7424a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7424a-120">See also</span></span>

- [<span data-ttu-id="7424a-121">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="7424a-121">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
