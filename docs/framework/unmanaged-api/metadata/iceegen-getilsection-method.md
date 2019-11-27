---
title: Metodo ICeeGen::GetIlSection
ms.date: 03/30/2017
api_name:
- ICeeGen.GetIlSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetIlSection
helpviewer_keywords:
- GetIlSection method [.NET Framework metadata]
- ICeeGen::GetIlSection method [.NET Framework metadata]
ms.assetid: 6f2db2ca-203f-4ac3-9530-208642ca385e
topic_type:
- apiref
ms.openlocfilehash: 7ef944fd06d07dc8c4e49061a5e72d8acc4d0465
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436341"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="b0c18-102">Metodo ICeeGen::GetIlSection</span><span class="sxs-lookup"><span data-stu-id="b0c18-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="b0c18-103">Ottiene la sezione della base di codice del linguaggio intermedio a cui fa riferimento l'handle specificato.</span><span class="sxs-lookup"><span data-stu-id="b0c18-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="b0c18-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="b0c18-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0c18-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0c18-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0c18-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b0c18-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="b0c18-107">in Handle per la sezione da ottenere.</span><span class="sxs-lookup"><span data-stu-id="b0c18-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0c18-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b0c18-108">Requirements</span></span>  
 <span data-ttu-id="b0c18-109">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0c18-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0c18-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b0c18-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b0c18-111">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b0c18-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b0c18-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0c18-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0c18-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0c18-113">See also</span></span>

- [<span data-ttu-id="b0c18-114">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="b0c18-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
