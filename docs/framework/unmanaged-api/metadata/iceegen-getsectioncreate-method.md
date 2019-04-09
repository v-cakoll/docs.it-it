---
title: Metodo ICeeGen::GetSectionCreate
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionCreate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9768dfd43b6b60df1660c48cb6d6f498b049e256
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103311"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="21d60-102">Metodo ICeeGen::GetSectionCreate</span><span class="sxs-lookup"><span data-stu-id="21d60-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="21d60-103">Genera l'errore e ottiene una sezione di codice usando il nome specificato e i valori di flag.</span><span class="sxs-lookup"><span data-stu-id="21d60-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="21d60-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="21d60-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21d60-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="21d60-105">Syntax</span></span>  
  
```  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21d60-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="21d60-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="21d60-107">[in] Un puntatore a una stringa che specifica il nome della sezione da creare.</span><span class="sxs-lookup"><span data-stu-id="21d60-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="21d60-108">[in] Flag che specificano le opzioni.</span><span class="sxs-lookup"><span data-stu-id="21d60-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="21d60-109">[out] Puntatore alla sezione di codice appena creato.</span><span class="sxs-lookup"><span data-stu-id="21d60-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21d60-110">Note</span><span class="sxs-lookup"><span data-stu-id="21d60-110">Remarks</span></span>  
 <span data-ttu-id="21d60-111">Chiamare `GetSectionCreate` solo se si hanno requisiti di sezione speciale che non sono gestiti tramite altri metodi.</span><span class="sxs-lookup"><span data-stu-id="21d60-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21d60-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="21d60-112">Requirements</span></span>  
 <span data-ttu-id="21d60-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21d60-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21d60-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="21d60-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="21d60-115">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="21d60-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="21d60-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="21d60-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="21d60-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21d60-117">See also</span></span>

- [<span data-ttu-id="21d60-118">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="21d60-118">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
