---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: 5249d7ea359db5d5c58ae87600f61048b465b4c1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964771"
---
# <a name="ienumrawinputdevice"></a><span data-ttu-id="bfa8a-102">IEnumRAWINPUTDEVICE</span><span class="sxs-lookup"><span data-stu-id="bfa8a-102">IEnumRAWINPUTDEVICE</span></span>
<span data-ttu-id="bfa8a-103">Questa interfaccia enumera i dispositivi di input non elaborati e viene usata solo da PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="bfa8a-103">This interface enumerates the raw input devices, and is only used by PresentationHost.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bfa8a-104">Questa API è solo intesa e supportata per l'uso sul computer client locale</span><span class="sxs-lookup"><span data-stu-id="bfa8a-104">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="bfa8a-105">Members</span><span class="sxs-lookup"><span data-stu-id="bfa8a-105">Members</span></span>  
  
|<span data-ttu-id="bfa8a-106">Member</span><span class="sxs-lookup"><span data-stu-id="bfa8a-106">Member</span></span>|<span data-ttu-id="bfa8a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfa8a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bfa8a-108">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="bfa8a-108">IEnumRAWINPUTDEVIC:Next</span></span>](ienumrawinputdevic-next.md)|<span data-ttu-id="bfa8a-109">Vengono enumerati i successivi elementi `celt` successivi (ovvero le strutture RAWINPUTDEVICE) nell'elenco dell'enumeratore, che vengono restituiti in `rgelt` insieme al numero effettivo di elementi enumerati in `pceltFetched`.</span><span class="sxs-lookup"><span data-stu-id="bfa8a-109">Enumerates the next `celt` elements (that is, RAWINPUTDEVICE structures) in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>|  
|[<span data-ttu-id="bfa8a-110">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="bfa8a-110">IEnumRAWINPUTDEVIC:Skip</span></span>](ienumrawinputdevic-skip.md)|<span data-ttu-id="bfa8a-111">Indica all'enumeratore di ignorare gli elementi `celt` successivi nell'enumerazione, in modo che la chiamata successiva a [IEnumRAWINPUTDEVIC: Next](ienumrawinputdevic-next.md) non restituisca tali elementi.</span><span class="sxs-lookup"><span data-stu-id="bfa8a-111">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>|  
|[<span data-ttu-id="bfa8a-112">IEnumRAWINPUTDEVIC:Reset</span><span class="sxs-lookup"><span data-stu-id="bfa8a-112">IEnumRAWINPUTDEVIC:Reset</span></span>](ienumrawinputdevic-reset.md)|<span data-ttu-id="bfa8a-113">Riporta all'inizio la sequenza di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bfa8a-113">Resets the enumeration sequence to the beginning.</span></span>|  
|[<span data-ttu-id="bfa8a-114">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="bfa8a-114">IEnumRAWINPUTDEVIC:Clone</span></span>](ienumrawinputdevic-clone.md)|<span data-ttu-id="bfa8a-115">Crea un altro enumeratore del dispositivo di input non elaborato con lo stesso stato dell'enumeratore corrente per eseguire l'iterazione dello stesso elenco.</span><span class="sxs-lookup"><span data-stu-id="bfa8a-115">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bfa8a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfa8a-116">See also</span></span>

- [<span data-ttu-id="bfa8a-117">Informazioni sull'input non elaborato</span><span class="sxs-lookup"><span data-stu-id="bfa8a-117">About Raw Input</span></span>](/windows/desktop/inputdev/about-raw-input)
