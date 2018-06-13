---
title: GetRawInputDevices
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: acaa3a2ff0f08f60956caedba60c996e01a6eff3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546787"
---
# <a name="getrawinputdevices"></a><span data-ttu-id="dccda-102">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="dccda-102">GetRawInputDevices</span></span>
<span data-ttu-id="dccda-103">Consente a PresentationHost.exe di individuare i dispositivi di input non elaborato (HID, Human Interface Devices) che interessano l'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="dccda-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dccda-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dccda-104">Syntax</span></span>  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dccda-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dccda-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="dccda-106">[out] Un puntatore a un [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) per enumerare i dispositivi di input non elaborati.</span><span class="sxs-lookup"><span data-stu-id="dccda-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="dccda-107">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dccda-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="dccda-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="dccda-108">HRESULT:</span></span>  
  
 <span data-ttu-id="dccda-109">S_OK - [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) verrà utilizzato da PresentationHost.exe solo se viene restituito S_OK.</span><span class="sxs-lookup"><span data-stu-id="dccda-109">S_OK - [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="dccda-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="dccda-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dccda-111">Note</span><span class="sxs-lookup"><span data-stu-id="dccda-111">Remarks</span></span>  
 <span data-ttu-id="dccda-112">I dispositivi di input non elaborato comprendono una serie di dispositivi tra cui tastiere, mouse e dispositivi meno tradizionali quali i telecomandi.</span><span class="sxs-lookup"><span data-stu-id="dccda-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="dccda-113">Dopo avere recuperato l'elenco di dispositivi di input non elaborato, PresentationHost.exe viene registrato per i dispositivi per ricevere messaggi di notifica WM_INPUT.</span><span class="sxs-lookup"><span data-stu-id="dccda-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dccda-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dccda-114">See Also</span></span>  
 [http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp)  
 [<span data-ttu-id="dccda-115">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="dccda-115">FilterInputMessage</span></span>](../../../../docs/framework/wpf/app-development/filterinputmessage.md)
