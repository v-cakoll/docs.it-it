---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: ff68c30c4e58cebb70c59352593d7b084413dce8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="getcustomui"></a>GetCustomUI
Chiamato da PresentationHost.exe per ottenere lo stato personalizzato e messaggi di errore dall'host, se implementata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a>Parametri  
 `pwzProgressAssemblyName`  
  
 [out] Un puntatore all'assembly che contiene l'interfaccia utente di stato fornita dall'host.  
  
 `pwzProgressClassName`  
  
 [out] Il nome della classe che è l'interfaccia utente di stato fornita dall'host, preferibilmente una [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file con <xref:System.Windows.Controls.Page> elemento di primo livello. Questa classe si trova nell'assembly specificato da `pwzProgressAssemblyName`.  
  
 `pwzErrorAssemblyName`  
  
 [out] Un puntatore all'assembly che contiene l'interfaccia utente di errore fornita dall'host.  
  
 `pwzErrorClassName`  
  
 [out] Il nome della classe che corrisponde all'utente di errore fornita dall'host dell'interfaccia, preferibilmente un file XAML con <xref:System.Windows.Controls.Page> elemento di primo livello. Questa classe si trova nell'assembly specificato da `pwzErrorAssemblyName`.  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 HRESULT: ignorato.  
  
## <a name="remarks"></a>Note  
 Un'applicazione host potrebbe essere un tema interfacce utente predefinite di PresentationHost.exe potrebbero non essere conforme alle specifico. In questo caso, è possibile implementare l'applicazione host [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) per restituire lo stato di avanzamento e di errore interfacce utente per PresentationHost.exe. Chiama sempre PresentationHost.exe [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) prima di utilizzare le interfacce utente predefinite.  
  
 Questa funzione viene chiamata una volta durante l'inizializzazione di PresentationHost.  
  
## <a name="see-also"></a>Vedere anche  
 [IWpfHostSupport](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)
