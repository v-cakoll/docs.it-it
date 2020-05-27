---
title: Metodo ICeeGen::GetString
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
ms.openlocfilehash: b7b15261d825c1bd5f217c4cecd82ed36a716d0e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008261"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="6676a-102">Metodo ICeeGen::GetString</span><span class="sxs-lookup"><span data-stu-id="6676a-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="6676a-103">Ottiene la stringa archiviata nell'indirizzo virtuale relativo specificato.</span><span class="sxs-lookup"><span data-stu-id="6676a-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="6676a-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="6676a-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6676a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6676a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in]  ULONG      RVA,
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6676a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="6676a-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="6676a-107">in Indirizzo virtuale relativo della stringa da restituire.</span><span class="sxs-lookup"><span data-stu-id="6676a-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="6676a-108">out Stringa restituita.</span><span class="sxs-lookup"><span data-stu-id="6676a-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6676a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6676a-109">Requirements</span></span>  
 <span data-ttu-id="6676a-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6676a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6676a-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6676a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6676a-112">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6676a-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6676a-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6676a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6676a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6676a-114">See also</span></span>

- [<span data-ttu-id="6676a-115">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="6676a-115">ICeeGen Interface</span></span>](iceegen-interface.md)
