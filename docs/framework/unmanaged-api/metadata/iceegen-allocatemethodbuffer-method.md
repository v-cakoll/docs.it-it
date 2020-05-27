---
title: Metodo ICeeGen::AllocateMethodBuffer
ms.date: 03/30/2017
api_name:
- ICeeGen.AllocateMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AllocateMethodBuffer
helpviewer_keywords:
- AllocateMethodBuffer method [.NET Framework metadata]
- ICeeGen::AllocateMethodBuffer method [.NET Framework metadata]
ms.assetid: 845ab77e-9639-47f5-99fb-f3b619e3e779
topic_type:
- apiref
ms.openlocfilehash: 8dc7f439cac56c2d55916ff8631ec3095c67680d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008885"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="b6b9a-102">Metodo ICeeGen::AllocateMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="b6b9a-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="b6b9a-103">Crea un buffer con la dimensione specificata per un metodo e ottiene l'indirizzo virtuale relativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="b6b9a-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="b6b9a-104">Questo metodo è obsoleto e non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="b6b9a-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6b9a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6b9a-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (
    [in]  ULONG    cchBuffer,
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6b9a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b6b9a-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="b6b9a-107">in Lunghezza del buffer da creare.</span><span class="sxs-lookup"><span data-stu-id="b6b9a-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="b6b9a-108">out Buffer restituito.</span><span class="sxs-lookup"><span data-stu-id="b6b9a-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="b6b9a-109">out Indirizzo virtuale relativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="b6b9a-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6b9a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6b9a-110">Requirements</span></span>  
 <span data-ttu-id="b6b9a-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6b9a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6b9a-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b6b9a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b6b9a-113">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b6b9a-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b6b9a-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6b9a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6b9a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6b9a-115">See also</span></span>

- [<span data-ttu-id="b6b9a-116">Interfaccia ICeeGen</span><span class="sxs-lookup"><span data-stu-id="b6b9a-116">ICeeGen Interface</span></span>](iceegen-interface.md)
