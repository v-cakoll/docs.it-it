---
title: Istanze
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: a95acf8e775e0802dc0ed781c562fa6373995a70
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473042"
---
# <a name="instances"></a>Istanze
Nome contatore: istanze.  
  
## <a name="description"></a>Descrizione  
 Numero di contesti di istanza attualmente contenuti dal servizio.  
  
 In genere, il numero di contesti di istanza è identico al numero di istanze. Tuttavia, gli scenari seguenti rappresenta un'eccezione a questa regola.  
  
-   Un metodo di servizio chiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> in modo esplicito.  
  
-   Viene applicata un'enumerazione <xref:System.ServiceModel.ReleaseInstanceMode> a un'istanza di <xref:System.ServiceModel.OperationBehaviorAttribute>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
