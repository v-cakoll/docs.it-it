---
title: GetRawInputDevices
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 3531ff9f42289a3ad3b029f090f2dd4987e5886c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199404"
---
# <a name="getrawinputdevices"></a>GetRawInputDevices
Consente a PresentationHost.exe di individuare i dispositivi di input non elaborato (HID, Human Interface Devices) che interessano l'applicazione host.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
## <a name="parameters"></a>Parametri  
 `ppEnum`  
  
 [out] Un puntatore a un [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) per enumerare i dispositivi di input non elaborati.  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 HRESULT:  
  
 S_OK - [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) verrà utilizzato da PresentationHost.exe solo se viene restituito S_OK.  
  
 E_NOTIMPL  
  
## <a name="remarks"></a>Note  
 I dispositivi di input non elaborato comprendono una serie di dispositivi tra cui tastiere, mouse e dispositivi meno tradizionali quali i telecomandi.  
  
 Dopo avere recuperato l'elenco di dispositivi di input non elaborato, PresentationHost.exe viene registrato per i dispositivi per ricevere messaggi di notifica WM_INPUT.  
  
## <a name="see-also"></a>Vedere anche

- [GetRawInputDeviceList](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [FilterInputMessage](filterinputmessage.md)
