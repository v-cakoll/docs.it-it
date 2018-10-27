---
title: CustomBindingElement
ms.date: 03/30/2017
ms.assetid: df959dc5-1aef-4338-a123-6ff3e7bc37af
ms.openlocfilehash: ff0d7d8d6c6cb180043a834a60ca58159ca84c58
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183152"
---
# <a name="custombindingelement"></a>CustomBindingElement
CustomBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class CustomBindingElement : BindingElement  
{  
  string Name;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe CustomBindingElement non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe CustomBindingElement dispone della proprietà seguente:  
  
### <a name="name"></a>Nome  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Stringa che contiene il nome della configurazione dell'associazione. Questo valore è una stringa definita dall'utente che deve essere univoca in quanto funge da stringa di identificazione dell'associazione personalizzata.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.CustomBinding>
