---
title: Metodo ICeeGen::GetSectionDataLen
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionDataLen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionDataLen
helpviewer_keywords:
- ICeeGen::GetSectionDataLen method [.NET Framework metadata]
- GetSectionDataLen method [.NET Framework metadata]
ms.assetid: e2a06ee4-b8ee-49c7-935a-c1031a29eef2
topic_type:
- apiref
ms.openlocfilehash: 1855c73849c35bf709b0af261a88e6cd7a40abfb
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008300"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="94e84-102">Metodo ICeeGen::GetSectionDataLen</span><span class="sxs-lookup"><span data-stu-id="94e84-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="94e84-103">Ottiene la lunghezza della sezione specificata.</span><span class="sxs-lookup"><span data-stu-id="94e84-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="94e84-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="94e84-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94e84-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94e84-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94e84-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="94e84-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="94e84-107">in Sezione di dati di cui verrà recuperata la lunghezza.</span><span class="sxs-lookup"><span data-stu-id="94e84-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="94e84-108">out Lunghezza restituita della sezione specificata.</span><span class="sxs-lookup"><span data-stu-id="94e84-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94e84-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="94e84-109">Remarks</span></span>  
 <span data-ttu-id="94e84-110">Chiamare `GetSectionDataLen` solo se si dispone di requisiti speciali per la sezione che non sono gestiti da altri metodi.</span><span class="sxs-lookup"><span data-stu-id="94e84-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94e84-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="94e84-111">Requirements</span></span>  
 <span data-ttu-id="94e84-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94e84-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94e84-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="94e84-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="94e84-114">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="94e84-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="94e84-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94e84-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94e84-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94e84-116">See also</span></span>

- [<span data-ttu-id="94e84-117">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="94e84-117">ICeeGen Interface</span></span>](iceegen-interface.md)
