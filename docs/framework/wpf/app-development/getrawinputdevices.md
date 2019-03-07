---
title: GetRawInputDevices
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 763767514f5f157c676f2e5c86ff9b1e4e64f233
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495247"
---
# <a name="getrawinputdevices"></a><span data-ttu-id="2f2fb-102">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="2f2fb-102">GetRawInputDevices</span></span>
<span data-ttu-id="2f2fb-103">Consente a PresentationHost.exe di individuare i dispositivi di input non elaborato (HID, Human Interface Devices) che interessano l'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="2f2fb-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f2fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f2fb-104">Syntax</span></span>  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f2fb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2f2fb-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="2f2fb-106">[out] Un puntatore a un [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) per enumerare i dispositivi di input non elaborati.</span><span class="sxs-lookup"><span data-stu-id="2f2fb-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="2f2fb-107">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2f2fb-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="2f2fb-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="2f2fb-108">HRESULT:</span></span>  
  
 <span data-ttu-id="2f2fb-109">S_OK - [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) verrà utilizzato da PresentationHost.exe solo se viene restituito S_OK.</span><span class="sxs-lookup"><span data-stu-id="2f2fb-109">S_OK - [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="2f2fb-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="2f2fb-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f2fb-111">Note</span><span class="sxs-lookup"><span data-stu-id="2f2fb-111">Remarks</span></span>  
 <span data-ttu-id="2f2fb-112">I dispositivi di input non elaborato comprendono una serie di dispositivi tra cui tastiere, mouse e dispositivi meno tradizionali quali i telecomandi.</span><span class="sxs-lookup"><span data-stu-id="2f2fb-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="2f2fb-113">Dopo avere recuperato l'elenco di dispositivi di input non elaborato, PresentationHost.exe viene registrato per i dispositivi per ricevere messaggi di notifica WM_INPUT.</span><span class="sxs-lookup"><span data-stu-id="2f2fb-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f2fb-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f2fb-114">See also</span></span>
- [<span data-ttu-id="2f2fb-115">GetRawInputDeviceList</span><span class="sxs-lookup"><span data-stu-id="2f2fb-115">GetRawInputDeviceList</span></span>](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [<span data-ttu-id="2f2fb-116">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="2f2fb-116">FilterInputMessage</span></span>](filterinputmessage.md)
