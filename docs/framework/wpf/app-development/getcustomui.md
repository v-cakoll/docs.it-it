---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: a9c4c9d597f5cc1b172213d49a3dd5b8f1c1f671
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991370"
---
# <a name="getcustomui"></a>GetCustomUI
Chiamato da PresentationHost. exe per ottenere i messaggi di errore e di stato personalizzati dall'host, se implementati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzProgressAssemblyName`  
  
 out Puntatore all'assembly che contiene l'interfaccia utente di avanzamento fornita dall'host.  
  
 `pwzProgressClassName`  
  
 out Il nome della classe che rappresenta l'interfaccia utente di avanzamento fornita dall'host, preferibilmente un [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file con <xref:System.Windows.Controls.Page> è il relativo elemento di livello principale. Questa classe risiede nell'assembly specificato da `pwzProgressAssemblyName`.  
  
 `pwzErrorAssemblyName`  
  
 out Puntatore all'assembly che contiene l'interfaccia utente degli errori fornita dall'host.  
  
 `pwzErrorClassName`  
  
 out Nome della classe che rappresenta l'interfaccia utente degli errori fornita dall'host, preferibilmente un file XAML con <xref:System.Windows.Controls.Page> è il relativo elemento di livello principale. Questa classe risiede nell'assembly specificato da `pwzErrorAssemblyName`.  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 HRESULT: Ignorato.  
  
## <a name="remarks"></a>Note  
 Un'applicazione host può presentare un tema specifico a cui le interfacce utente predefinite di PresentationHost. exe potrebbero non essere conformi. In tal caso, l'applicazione host può implementare [GetCustomUI](getcustomui.md) per restituire le interfacce utente di stato e di errore in PresentationHost. exe. PresentationHost. exe chiamerà sempre [GetCustomUI](getcustomui.md) prima di usare le interfacce utente predefinite.  
  
 Questa funzione viene chiamata una sola volta durante l'inizializzazione di PresentationHost.  
  
## <a name="see-also"></a>Vedere anche

- [IWpfHostSupport](iwpfhostsupport.md)
