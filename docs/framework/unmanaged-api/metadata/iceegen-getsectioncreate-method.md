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
ms.openlocfilehash: 0cf7b15392c90694db659f6faff6feecbef65466
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008330"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="578c0-102">Metodo ICeeGen::GetSectionCreate</span><span class="sxs-lookup"><span data-stu-id="578c0-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="578c0-103">Genera e ottiene una sezione di codice utilizzando il nome e i valori del flag specificati.</span><span class="sxs-lookup"><span data-stu-id="578c0-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="578c0-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="578c0-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="578c0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="578c0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="578c0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="578c0-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="578c0-107">in Puntatore a una stringa che specifica il nome della sezione da creare.</span><span class="sxs-lookup"><span data-stu-id="578c0-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="578c0-108">in Flag che specificano le opzioni.</span><span class="sxs-lookup"><span data-stu-id="578c0-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="578c0-109">out Puntatore alla sezione di codice appena creata.</span><span class="sxs-lookup"><span data-stu-id="578c0-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="578c0-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="578c0-110">Remarks</span></span>  
 <span data-ttu-id="578c0-111">Chiamare `GetSectionCreate` solo se si dispone di requisiti speciali per la sezione che non sono gestiti da altri metodi.</span><span class="sxs-lookup"><span data-stu-id="578c0-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="578c0-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="578c0-112">Requirements</span></span>  
 <span data-ttu-id="578c0-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="578c0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="578c0-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="578c0-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="578c0-115">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="578c0-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="578c0-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="578c0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="578c0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="578c0-117">See also</span></span>

- [<span data-ttu-id="578c0-118">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="578c0-118">ICeeGen Interface</span></span>](iceegen-interface.md)
