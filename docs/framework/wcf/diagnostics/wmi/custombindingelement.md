---
title: CustomBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df959dc5-1aef-4338-a123-6ff3e7bc37af
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bffffc5876d368d4b7956f61fcb81f87371a6d71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="custombindingelement"></a>CustomBindingElement
CustomBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
